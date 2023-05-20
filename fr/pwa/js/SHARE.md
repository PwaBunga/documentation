* [Accueil de la documentation](https://github.com/PwaBunga/documentation/blob/main/fr/)
* [Documentation du module PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md)
* [Documentation du module PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md)
* [Documentation du module PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/fr/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[English version](https://github.com/PwaBunga/documentation/blob/main/pwa/js/SHARE.md)

[Retour à la documentation de PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md)


# `pwaShare()` : Utilisation du partage natif de l'appareil

Afin d'offrir une expérience immersive comme le font les applications natives, on affiche la PWA en `fullscreen` ou `standalone`.

Le problème avec ces 2 modes d'affichage est que l'on n'as plus le bouton de partage que propose l'appareil (il reste présent en définissant l'affichage de l'application avec la valeur `minimal-ui`).

Afin d'améliorer l'expérience utilisateur et le partage de l'applciation sur les réseaux sociaux, PWA Bunga! propose la fonction `pwaShare()` qui utilise l'API Web Share.

&nbsp;

## HTML

Afin que la fonction soit fonctionnelle, il faut ajouter ces éléments au DOM :

* `pwa-share-btn` : bouton de partage

```html
<button class="pwa-share-btn">Share</button>
```

&nbsp;

## CSS

On cache l élément

```css
.pwa-share-btn {
    display: none;
}
```

Si l'élément a la classe `is-visible`, on l'affiche

```css
.pwa-share-btn.is-visible {
    display: block;
}
```

&nbsp;

## La fonction

```js
const pwaShare = async (options = {}) => {
    ...
}
```

### Options de la fonction

Cette fonction prend un objet d'options facultatif qui permet de personnaliser le titre, le texte et l'URL partagés.

```js
pwaShare({
    title: 'Mon titre personnalisé',
    text: 'Mon texte personnalisé',
    url: 'https://www.example.com'
});
```

### Sélection de l'élément du DOM

Nous mettons en variable l'élément du DOM à manipuler

```js
const pwaBtnShare = document.querySelector('.pwa-share-btn')
```

### Récupération des données du fichier webmanifest

On fait une requête sur le fichier webmanifest et on stocke la réponse dans une variable

```js
const webmanifestResponse = await fetch(new Request(document.querySelector('link[rel="manifest"]').href))
```

On Convertit la réponse de JSON en un objet JavaScript et la stocke dans une variable

```js
const webmanifest = await webmanifestResponse.json()
```

### Attribution des données pour l'API Share

On définit le titre de partage avec le paramètre en option de la fonction, ou avec la propriété `name` du fichier Webmanifest, ou avec la balise meta `title` du document

```js
const title = options.title || webmanifest.name || document.title
```

On définit le texte de partage avec le paramètre en option de la fonction, ou avec la propriété de description du fichier Webmanifest, ou vide

```js
const text = options.text || webmanifest.description || ''
```

L'URL de partage avec le paramètre en option de la fonction, ou avec l'URL de la page

```js
onst url = options.url || location.origin + location.pathname;
```

### Affichage du bouton de partage

On vérifie si la PWA fonctionne en mode standalone

```js
const isStandalone = window.matchMedia('(display-mode: standalone)').matches
```

On vérifie si la PWA fonctionne en mode fullscreen

```js
const isFullscreen = window.matchMedia('(display-mode: fullscreen)').matches
```

On vérifie si la PWA fonctionne en mode standalone sur iOS

```js
const isStandaloneIOS = window.navigator.standalone
```

Si la PWA est en mode sandalone ou fullscreen, on affiche le bouton de partage

```js
if (isStandalone || isFullscreen || isStandaloneIOS) {
    pwaShareBtn.classList.add('is-visible')
}
```

### Partage du lien

Au clic sur le bouton de partage

```js
pwaBtnShare.addEventListener('click', async () => {
```

Si le navigateur supporte l'API Web Share

```js
if ('share' in navigator) {
```

On définit un objet appelé data qui contient le titre, le texte et l'url de la page à partager

```js
let data = { title, text, url }
```

On ouvre le module de partage natif de l'appareil avec les données à partager

```js
await navigator.share(data)
```

Si le navigateur ne supporte pas l'api Share

```js
else {  
    location.href = 'https://api.whatsapp.com/send?text=' + encodeURIComponent(text + ' - ') + url
}
```

&nbsp;

## Appel de la fonction

Voici l'appel de la fonction utilisé sur pwabunga.js

```js
pwaShare()
```

&nbsp;

## Code complet de la fonction `pwaShare()`

Voici l'appel de la fonction utilisé sur pwabunga.js

```js
const pwaShare = async (options = {}) => {

    try {
    
        const pwaShareBtn = document.querySelector('.pwa-share-btn')
    
        const webmanifestResponse = await fetch(new Request(document.querySelector('link[rel="manifest"]').href))
        const webmanifest = await webmanifestResponse.json()
    
        const title = options.title || webmanifest.name || document.title
        const text  = options.text || webmanifest.description || ''
        const url   = options.url || location.origin + location.pathname;
    
        const isStandalone = window.matchMedia('(display-mode: standalone)').matches
        const isFullscreen = window.matchMedia('(display-mode: fullscreen)').matches
        const isStandaloneIOS = window.navigator.standalone
    
        if (isStandalone || isFullscreen || isStandaloneIOS) {
            pwaShareBtn.classList.add('is-visible')
        }
    
        pwaShareBtn.addEventListener('click', async () => {
            if ('share' in navigator) {
                let data = { title, text, url }
                try {
                    await navigator.share(data)
                } catch (error) {
                    console.error('Error sharing:', error)
                }
            } else {
                console.warn('Share API not supported')
                location.href = 'https://api.whatsapp.com/send?text=' + encodeURIComponent(text + ' - ') + url
            }
        })
    
    } catch (error) {
        console.error('Error initializing pwaShare:', error)
    }
    
}   
```

&nbsp;
