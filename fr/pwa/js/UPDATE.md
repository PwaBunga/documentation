* [Accueil de la documentation](https://github.com/PwaBunga/documentation/blob/main/fr/)
* [Documentation du module PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md)
* [Documentation du module PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md)
* [Documentation du module PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/fr/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[English version](https://github.com/PwaBunga/documentation/blob/main/pwa/js/UPDATE.md)

[Retour à la documentation de PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md)


# `pwaUpdate()` : Mise à jour de l'application

Un des avantages des PWA sur les applications natives est sans aucun doute la mise à jour de l'application.

Sur les applications natives, sur android par exemple, il faut aller dans Google Play Store, aller sur l'icône du profil, aller sur "Gérer les applications de l'appareil" puis enfin appuyer sur "Mettre à jour".

Ce processus n'est pas idéal en terme d'expérience utilisateur et on retarde souvent cette action.

Avec les PWA, même si ça n'est pas forcément une bonne idée, on peut mettre à jour l'application de manière transparente et asynchrone.

&nbsp;

## Le problème des mises à jour des PWA

Le service worker est un fichier javascript qui va servir de proxy unique pour toutes les instances de l'application. Si un onglet reste ouvert, la mise à jour ne se fera pas, même si le navigateur a détecté l'a détecté.

De plus, rafraichir l'onglet de l'application ne suffira pas à enclencher la mise à jour. Pendant un certain temps, la nouvelle instance de l'application existe simultanément dans la mémoire à coté du précédent.

On peut forcer la mise à jour côté serviceworker, mais cela peut générer des soucis d'expérience utilisateur, comme dans le cas où la mise à jour s'effectuerait pendant que l'utilisateur saisi sa carte bancaire dans le tunnel de conversion de l'application.

&nbsp;

## Solution proposée par PWA Bunga!

Afin de pallier ces problèmes, la fonction `pwaUpdate()` va permettre :

* d'afficher un encart dans l'application informant l'utilisateur qu'une mise à jour est disponible
* d'afficher dans cet encart un bouton permettant de faire la mise à jour
* d'envoyer au service worker l'information que la mise à jour à été demandé par l'utilisateur
* de mettre à jour l'application en rafraichissant toutes les instances de l'application

&nbsp;

## HTML

Afin que la fonction soit fonctionnelle, il faut ajouter ces éléments au DOM :

* `pwa-update` : contenant de l'encart d'information de la disponibilité d'une mise à jour
* `pwa-update-btn` : bouton de mise à jour
* `pwa-update-close` : bouton de fermeture de l'encart
* `pwa-loader` : le loader

### Encart et boutton de mise à jour

```html
<div class="pwa-update">
    <button class="pwa-update-close">Close</button>
    {{ content }}
    <button class="pwa-update-btn">Install</button>
</div>
```

### Loader

```html
<div class="pwa-loader">
    {{ loader }}
</div>
```

&nbsp;

## CSS

On cache les éléments utiles à la fonction

```css
.pwa-update,
.pwa-loader {
    display: none;
}
```

Si l'élément a la classe `is-visible`, on l'affiche

```css
.pwa-update.is-visible,
.pwa-loader.is-visible {
    display: block;
}
```

&nbsp;

## La fonction

```js
const pwaUpdate = async () => {
    ...
}
```

### Sélection des éléments du DOM

On met en variable les éléments du DOM à manipuler

```js
const pwaUpdateBar    = document.querySelector('.pwa-update')
const pwaUpdateBtn    = document.querySelector('.pwa-update-btn')
const pwaUpdateClose  = document.querySelector('.pwa-update-close')
const pwaUpdateLoader = document.querySelector('.pwa-loader')
```

### Service worker

On met en variable l'instance du service worker de l'application, qui va nous servir à détecter une mise à jour et un changement de statut

```js
const registration = await navigator.serviceWorker.getRegistration()
```

### Détection d'une mise à jour

On détecte si un nouveau serviceworker est disponible

```js
registration.addEventListener("updatefound", async () => {
    if (registration.installing) {
```

On détecte s'il est prêt à prendre le relais

```js
registration.installing.addEventListener('statechange', async () => {
    if (registration.waiting) {
```

S'il existe déjà un service worker (sinon il s'agit de la première installation de l'application), on affiche l'encart de mise à jour

```js
if (navigator.serviceWorker.controller) {
    pwaUpdateBar.classList.add('is-visible')
}
```

### Bouton de mise à jour

Au clic sur le bouton de mise à jour

```js
pwaUpdateBtn.addEventListener('click', async () => {
```

On cache l'encart de mise à jour

```js
pwaUpdateBar.classList.remove('is-visible')
```

On affiche le loader qui va permettre de combler le laps de temps entre le moment où on envoi au service worker l'indication de se mettre à jour et le moment où il est mis à jour.

```js
pwaUpdateLoader.classList.add('is-visible')
```

On indique au service worker que l'utilisateur a demandé la mise à jour en envoyant un message avec l'API `postMessage`

```js
registration.waiting.postMessage('SKIP_WAITING')
```

### Exécution de la mise à jour

Quand le service worker à reçu le message précèdent, il se met à jour (voir la partie PWA Bunga! PWA service worker pour plus de détails sur ce traitement). On intercepte ce moment avec l'événement `controllerchange` et nous rafraichissons toutes les instances de l'application ouvertes

```js
navigator.serviceWorker.addEventListener('controllerchange', async () => {
    window.location.reload()
})
```

### Cas particulier

Dans le cas où pour une raison diverse, l'utilisateur ne fait pas la mise à jour, que la mise à jour ne se fait pas car d'autres instances de l'application sont ouvertes, on affiche l'encart de mise à jour.

```js
if (registration.waiting) {
    pwaUpdateBar.classList.add('is-visible')
}
```

### Bouton de fermeture de l'encart de mise à jour

On cache l'encart de mise à jour au clic du bouton `pwaUpdateClose`

```js
pwaUpdateClose.addEventListener('click', async () => {
    pwaUpdateBar.classList.remove('is-visible')
})
```

&nbsp;

## Appel de la fonction

Voici l'appel de la fonction utilisé sur pwabunga.js

```js
pwaUpdate()
```

&nbsp;

## Code complet de la fonction `pwaUpdate()`

Voici l'appel de la fonction utilisé sur pwabunga.js

```js
const pwaUpdate = async () => {

    const pwaUpdateBar    = document.querySelector('.pwa-update')
    const pwaUpdateBtn    = document.querySelector('.pwa-update-btn')
    const pwaUpdateClose  = document.querySelector('.pwa-update-close')
    const pwaUpdateLoader = document.querySelector('.pwa-loader')

    const registration = await navigator.serviceWorker.getRegistration()

    registration.addEventListener("updatefound", async () => {
        if (registration.installing) {
            registration.installing.addEventListener('statechange', async () => {
                if (registration.waiting) {
                    if (navigator.serviceWorker.controller) {
                        pwaUpdateBar.classList.add('is-visible')
                    }
                }
            })
        }
    })

    pwaUpdateBtn.addEventListener('click', async () => {
        pwaUpdateBar.classList.remove('is-visible')
        pwaUpdateLoader.classList.add('is-visible')t
        registration.waiting.postMessage('SKIP_WAITING')
    })

    navigator.serviceWorker.addEventListener('controllerchange', async () => {
        window.location.reload()
    })

    if (registration.waiting) {
        pwaUpdateBar.classList.add('is-visible')
    }

    pwaUpdateClose.addEventListener('click', async () => {
        pwaUpdateBar.classList.remove('is-visible')
    })

}
```

&nbsp;
