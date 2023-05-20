* [Accueil de la documentation](https://github.com/PwaBunga/documentation/blob/main/fr/)
* [Documentation du module PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md)
* [Documentation du module PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md)
* [Documentation du module PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/fr/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[English version](https://github.com/PwaBunga/documentation/blob/main/pwa/js/INSTALL.md)

[Retour à la documentation de PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md)

# `pwaInstall()` : Promotion et bouton d'installation de la PWA

Si la PWA répond aux critères d'installation, le navigateur déclenche un événement pour inviter l'utilisateur à l'installer.

Par exemple, sur Chrome Android, le navigateur affiche un bandeau proposant l'installation.

Il se peut que l'utilisateur ne connaisse pas le processus d'installation d'une PWA, et nous allons pouvoir améliorer cette expérience en le personnalisant.

À cet effet, la fonction `pwaInstall()` va :

* Afficher un encart de promotion de l'installation
* Afficher un bouton d'installation
* Afficher un loader qui simulera le temps d'installation
* Afficher un message de confirmation d'installation

&nbsp;

## HTML

Afin que la fonction soit fonctionnelle, il faut ajouter ces éléments au DOM :

* `pwa-install-promotion` : contenant de l'encart de promotion de l'installation
* `pwa-install-promotion-close` : bouton de fermeture de l'encart de promotion de l'installation
* `pwa-install-btn` : bouton d'installation
* `pwa-install-confirm` : contenant de l'encart de confirmation de l'installation
* `pwa-install-confirm-close` : bouton de fermeture de l'encart de confirmation de l'installation
* `pwa-loader` : Loader

### Encart de promotion de l'installation et bouton d'installation

```html
<div class="pwa-install-promotion">
    <button class="pwa-install-promotion-close">Close</button>
    {{ content }}
    <button class="pwa-install-btn">Install</button>
</div>
```

### Encart de confirmation de l'installation

```html
<div class="pwa-install-confirm">
    <button class="pwa-install-confirm-close">Close</button>
    {{ content }}
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

Si vous n'utilisez pas pwabunga-ui.css, voici le CSS à utiliser :

On cache les éléments utiles à la fonction

```css
.pwa-install-promotion,
.pwa-install-confirm,
.pwa-install-btn,
.pwa-loader {
    display: none;
}
```

Si l'élément a la classe `is-visible`, on l'affiche

```css
.pwa-install-promotion.is-visible,
.pwa-install-confirm.is-visible,
.pwa-install-btn.is-visible,
.pwa-loader.is-visible {
    display: block;
}
```

&nbsp;

## La fonction

```js
const pwaInstall = async () => {
    ...
}
```

### Sélection des éléments du DOM

Nous mettons en variable les éléments du DOM à manipuler

```js
const pwaInstallPromotion      = document.querySelector('.pwa-install-promotion')
const pwaInstallPromotionClose = document.querySelector('.pwa-install-promotion-close')
const pwaInstallBtn            = document.querySelector('.pwa-install-btn')
const pwaInstallConfirm        = document.querySelector('.pwa-install-confirm')
const pwaInstallConfirmClose   = document.querySelector('.pwa-install-confirm-close')
const pwaInstallLoader         = document.querySelector('.pwa-loader')
```

### Affichage de l'encart de promotion et du bouton d'installation

On initialise `deferredPrompt` que l'on utilisera par la suite pour afficher l'écran d'installation

```js
let deferredPrompt
```

Pour afficher les éléments, on utilise l'événement `beforeinstallprompt`

```js
window.addEventListener('beforeinstallprompt', (e) => {
```

On empêche l'apparition du bandeau affiché par défaut par le navigateur proposant l'installation

```js
e.preventDefault()
```

On stock l'événement qu'on utilisera plus tard

```js
deferredPrompt = e
```

On affiche l'encart de promotion de l'installation et le bouton d'installation.

```js
pwaInstallPromotion.classList.add('is-visible')
pwaInstallBtn.classList.add('is-visible')
```

### Bouton d'installation

Maintenant que le bouton d'installation est affiché si l'installation n'a pas été encore effectuée, on rend fonctionnel ce bouton.

Au clic sur le bouton d'installation

```js
pwaInstallBtn.addEventListener('click', () => {
```

On affiche la demande d'installation

```js
deferredPrompt.prompt()
```

On détecte si l'utilisateur a confirmé l'installation ou non

```js
const { outcome } = await deferredPrompt.userChoice;
```

`deferredPrompt` ayant été utilisé, il ne peut plus l'être

```js
deferredPrompt = null
```

Si l'utilisateur a accepté l'installation, on cache le bouton d'installation

```js
if (outcome === 'accepted') {
    pwaInstallBtn.classList.remove('is-visible')
}
```

### Affichage du loader et confirmation de l'installation

On utilise l'événement appinstalled pour afficher l'encart de confirmation. Cet évènement est déclenché au moment où le processus d'installation est engagé et non au moment où l'installation est terminée

```js
window.addEventListener("appinstalled", async () => {
```

On cache le l'encart de promotion de l'installation et on affiche le loader

```js
pwaInstallPromotion.classList.remove('is-visible')
pwaInstallLoader.classList.add('is-visible')
```

L'événement étant déclenché au début de l'installation, on ne peut pas savoir à quel moment cette installation est terminée. On simule donc le temps de chargement en affichant le loader 2,5 secondes puis on affiche l'encart de confirmation de l'installation.

```js
setTimeout(() => {
    pwaInstallConfirm.classList.add('is-visible')
    pwaInstallLoader.classList.remove('is-visible')
}, "2500");
```

### Bouton de fermeture de l'encart de promotion de l'installation

On cache l'encart de promotion au clic du bouton `pwaPromotionClose`

```js
pwaInstallPromotionClose.addEventListener('click', async (e) => {
    pwaInstallPromotion.classList.remove('is-visible')
})
```

### Bouton de fermeture de l'encart de confirmation de l'installation

On cache l'encart de confirmation de l'installation au clic du bouton `pwaInstallConfirmClose`

```js
pwaInstallConfirmClose.addEventListener('click', async (e) => {
    pwaInstallConfirm.classList.remove('is-visible')
})
```

&nbsp;

## Appel de la fonction

Voici l'appel de la fonction utilisé sur pwabunga.js

```js
pwaInstall()
```

&nbsp;

## Code complet de la fonction `pwaInstall()`

```js
const pwaInstall = async () => {
    
    const pwaInstallPromotion      = document.querySelector('.pwa-install-promotion')
    const pwaInstallPromotionClose = document.querySelector('.pwa-install-promotion-close')
    const pwaInstallBtn            = document.querySelector('.pwa-install-btn')
    const pwaInstallConfirm        = document.querySelector('.pwa-install-confirm')
    const pwaInstallConfirmClose   = document.querySelector('.pwa-install-confirm-close')
    const pwaInstallLoader         = document.querySelector('.pwa-loader')
    
    let deferredPrompt
    
    window.addEventListener('beforeinstallprompt', (e) => {
        e.preventDefault()
        deferredPrompt = e
        pwaInstallPromotion.classList.add('is-visible')
        pwaInstallBtn.classList.add('is-visible')
    })

    pwaInstallBtn.addEventListener('click', async () => {
        deferredPrompt.prompt()
        const { outcome } = await deferredPrompt.userChoice;
        deferredPrompt = null
        if (outcome === 'accepted') {
            pwaInstallBtn.classList.remove('is-visible')
        }
    })

    window.addEventListener("appinstalled", async () => {
        pwaInstallPromotion.classList.remove('is-visible')
        pwaInstallLoader.classList.add('is-visible')
        setTimeout(() => {
            pwaInstallConfirm.classList.add('is-visible')
            pwaInstallLoader.classList.remove('is-visible')
        }, "2500");
    })

    pwaInstallPromotionClose.addEventListener('click', async () => {
        pwaInstallPromotion.classList.remove('is-visible')
    })
    
    pwaInstallConfirmClose.addEventListener('click', async () => {
        pwaInstallConfirm.classList.remove('is-visible')
    })
    
}
```

&nbsp;
