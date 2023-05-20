* [Documentation homepage](https://github.com/PwaBunga/documentation/)
* [Documentation of the PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)
* [Documentation of the PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/CSS.md)
* [Documentation of the PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/INSTALL.md)

[Back to the documentation of PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/pwa/JS.md)

# `pwaInstall()`: Promotion and PWA install button

If the PWA meets the installation criteria, the browser triggers an event to prompt the user to install it.

For example, on Chrome Android, the browser displays a banner offering the installation.

The user may not be familiar with the process of installing a PWA, and we will be able to improve this experience by customizing it.

For this purpose, the `pwaInstall()` function will:

* Display an insert promoting the installation
* Show an install button
* Show a loader that will simulate the installation time
* Show installation confirmation message

&nbsp;

## HTML

In order for the function to be functional, these elements must be added to the DOM:

* `pwa-install-promotion`: containing installation promotion insert
* `pwa-install-promotion-close`: installation promotion insert close button
* `pwa-install-btn`: install button
* `pwa-install-confirm`: containing the installation confirmation insert
* `pwa-install-confirm-close`: button to close the installation confirmation box
* `pwa-loader`: Loader

### Installation promotion insert and installation button

```html
<div class="pwa-install-promotion">
     <button class="pwa-install-promotion-close">Close</button>
     {{ thrilled }}
     <button class="pwa-install-btn">Install</button>
</div>
```

### Installation Confirmation Insert

```html
<div class="pwa-install-confirm">
     <button class="pwa-install-confirm-close">Close</button>
     {{ thrilled }}
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

If you are not using pwabunga-ui.css, here is the CSS to use:

We hide the elements useful to the function

```css
.pwa-install-promotion,
.pwa-install-confirm,
.pwa-install-btn,
.pwa-loader {
     display: none;
}
```

If the element has class `is-visible`, we display it

```css
.pwa-install-promotion.is-visible,
.pwa-install-confirm.is-visible,
.pwa-install-btn.is-visible,
.pwa-loader.is-visible {
     display: block;
}
```

&nbsp;

## Function

```js
const pwaInstall = async () => {
     ...
}
```

### Selecting DOM elements

We set the DOM elements to be manipulated as variables

```js
const pwaInstallPromotion = document.querySelector('.pwa-install-promotion')
const pwaInstallPromotionClose = document.querySelector('.pwa-install-promotion-close')
const pwaInstallBtn = document.querySelector('.pwa-install-btn')
const pwaInstallConfirm = document.querySelector('.pwa-install-confirm')
const pwaInstallConfirmClose = document.querySelector('.pwa-install-confirm-close')
const pwaInstallLoader = document.querySelector('.pwa-loader')
```

### Display of the promotion insert and the install button

We initialize `deferredPrompt` which we will use later to display the installation screen

```js
let deferredPrompt
```

To display the elements, we use the `beforeinstallprompt` event

```js
window.addEventListener('beforeinstallprompt', (e) => {
```

The appearance of the banner displayed by default by the browser offering the installation is prevented

```js
e.preventDefault()
```

We store the event that we will use later

```js
deferredPrompt=e
```

The installation promotion insert and the installation button are displayed.

```js
pwaInstallPromotion.classList.add('is-visible')
pwaInstallBtn.classList.add('is-visible')
```

### Install button

Now that the installation button is displayed if the installation has not yet been performed, we make this button functional.

On click on the install button

```js
pwaInstallBtn.addEventListener('click', () => {
```

We display the installation request

```js
deferredPrompt.prompt()
```

We detect if the user has confirmed the installation or not

```js
const { outcome } = await deferredPrompt. userChoice;
```

`deferredPrompt` having been used, it can no longer be used

```js
deferredPrompt = null
```

If the user has accepted the installation, we hide the installation button

```js
if (outcome === 'accepted') {
     pwaInstallBtn.classList.remove('is-visible')
}
```

### Loader display and installation confirmation

We use the appinstalled event to display the confirmation insert. This event is triggered when the installation process is initiated and not when the installation is finished

```js
window. addEventListener("appinstalled", async () => {
```

We hide the installation promotion insert and we display the loader

```js
pwaInstallPromotion.classList.remove('is-visible')
pwaInstallLoader.classList.add('is-visible')
```

Since the event is triggered at the start of the installation, we cannot know when this installation is finished. We therefore simulate the loading time by displaying the loader for 2.5 seconds and then we display the installation confirmation insert.

```js
setTimeout(() => {
     pwaInstallConfirm.classList.add('is-visible')
     pwaInstallLoader.classList.remove('is-visible')
}, "2500");
```

### Installation promotion insert close button

We hide the promotion insert when you click on the `pwaPromotionClose` button

```js
pwaInstallPromotionClose.addEventListener('click', async (e) => {
     pwaInstallPromotion.classList.remove('is-visible')
})
```

### Installation confirmation box close button

We hide the installation confirmation insert when you click the `pwaInstallConfirmClose` button

```js
pwaInstallConfirmClose.addEventListener('click', async (e) => {
     pwaInstallConfirm.classList.remove('is-visible')
})
```

&nbsp;

## Function call

Here is the function call used on pwabunga.js

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
