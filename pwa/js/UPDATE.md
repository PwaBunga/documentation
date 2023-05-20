* [Documentation homepage](https://github.com/PwaBunga/documentation/)
* [Documentation of the PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)
* [Documentation of the PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/CSS.md)
* [Documentation of the PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/UPDATE.md)

[Back to the documentation of PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/pwa/JS.md)


# `pwaUpdate()`: Application update

One of the advantages of PWAs over native applications is undoubtedly the updating of the application.

On native applications, on android for example, you have to go to Google Play Store, go to the profile icon, go to "Manage device applications" and then finally press "Update".

This process is not ideal in terms of user experience and this action is often delayed.

With PWAs, even if it's not necessarily a good idea, you can update the application transparently and asynchronously.

&nbsp;

## The problem with PWA updates

The service worker is a javascript file that will serve as a single proxy for all instances of the application. If a tab remains open, the update will not occur, even if the browser has detected it.

In addition, refreshing the application tab will not be enough to trigger the update. For some time, the new instance of the application exists simultaneously in memory alongside the previous one.

You can force the update on the serviceworker side, but this can generate user experience issues, such as in the case where the update is carried out while the user enters his credit card in the conversion tunnel of the application.

&nbsp;

## Solution offered by PWA Bunga!

In order to overcome these problems, the `pwaUpdate()` function will allow:

* to display an insert in the application informing the user that an update is available
* to display in this insert a button allowing to make the update
* to send to the service worker the information that the update has been requested by the user
* update the application by refreshing all instances of the application

&nbsp;

## HTML

In order for the function to be functional, these elements must be added to the DOM:

* `pwa-update`: containing information about the availability of an update
* `pwa-update-btn`: update button
* `pwa-update-close`: inset close button
* `pwa-loader`: the loader

### Inset and update button

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

We hide the elements useful to the function

```css
.pwa-update,
.pwa-loader {
    display: none;
}
```

If the element has class `is-visible`, we display it

```css
.pwa-update.is-visible,
.pwa-loader.is-visible {
    display: block;
}
```

&nbsp;

## Function

```js
const pwaUpdate = async() => {
     ...
}
```

### Selecting DOM elements

We set the DOM elements to be manipulated as variables

```js
const pwaUpdateBar = document.querySelector('.pwa-update')
const pwaUpdateBtn = document.querySelector('.pwa-update-btn')
const pwaUpdateClose = document.querySelector('.pwa-update-close')
const pwaUpdateLoader = document.querySelector('.pwa-loader')
```

### Serviceworker

We set the service worker instance of the application as a variable, which will be used to detect an update and a change of status

```js
const registration = await navigator.serviceWorker.getRegistration()
```

### Detection of an update

We detect if a new serviceworker is available

```js
registration. addEventListener("updatefound", async () => {
     if (registration. installing) {
```

We detect if he is ready to take over

```js
registration. installing. addEventListener('statechange', async () => {
     if (registration. waiting) {
```

If a service worker already exists (otherwise it is the first installation of the application), the update box is displayed

```js
if (navigator. serviceWorker. controller) {
     pwaUpdateBar.classList.add('is-visible')
}
```

### Update button

On click on the update button

```js
pwaUpdateBtn.addEventListener('click', async () => {
```

We hide the update insert

```js
pwaUpdateBar.classList.remove('is-visible')
```

We display the loader that will fill the time gap between when we send the service worker the indication to update and when it is updated.

```js
pwaUpdateLoader.classList.add('is-visible')
```

We tell the service worker that the user has requested the update by sending a message with the `postMessage` API

```js
registration.waiting.postMessage('SKIP_WAITING')
```

### Running the update

When the service worker has received the above message, it updates itself (see the PWA section Bunga! PWA service worker for more details on this treatment). We intercept this moment with the `controllerchange` event and we refresh all the open instances of the application

```js
navigator. serviceWorker. addEventListener('controllerchange', async () => {
     window.location.reload()
})
```

### Particular case

In the event that for some reason, the user does not perform the update, the update does not occur because other instances of the application are open, the update box is displayed .

```js
if (registration. waiting) {
     pwaUpdateBar.classList.add('is-visible')
}
```

### Update inset close button

We hide the update insert when you click on the `pwaUpdateClose` button

```js
pwaUpdateClose. addEventListener('click', async () => {
     pwaUpdateBar.classList.remove('is-visible')
})
```

&nbsp;

## Function call

Here is the function call used on pwabunga.js

```js
pwaUpdate()
```

&nbsp;

## Complete code of the `pwaUpdate()` function

Here is the function call used on pwabunga.js

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
