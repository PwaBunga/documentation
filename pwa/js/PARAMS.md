* [Documentation homepage](https://github.com/PwaBunga/documentation/)
* [Documentation of the PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)
* [Documentation of the PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/CSS.md)
* [Documentation of the PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/PARAMS.md)

[Back to the documentation of PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/pwa/JS.md)


# `pwaParams()`: PWA parameters insert

Always with the aim of offering a user experience as close as possible to native applications, the `pwaParams()` function will allow the user to be offered a configuration insert allowing the version of the PWA to be displayed, as well as authorization management.

This function requires the presence of the `pwaNotifications()` and `pwaGeolocation()` functions, which will make it possible to manage the authorization buttons of the parameters insert.

&nbsp;

## Function Parameters

This function takes 3 parameters:

* `version`: Show/Hide the PWA version in the settings box (Boolean, default value: true)
* `notifications`: Show/Hide the notification authorization button in the settings box (Boolean, default value: true)
* `geolocation`: Show/Hide the geolocation authorization button in the settings box (Boolean, default value: true)

```js
const pwaParams = async(version=true, notifications=true, geolocation=true)
```

&nbsp;

## HTML

In order for the function to be functional, these elements must be added to the DOM:

* `pwa-params`: container of the PWA parameters insert
* `pwa-params-btn`: button to open the PWA parameters box
* `pwa-params-close-btn`: button to close the PWA parameters box
* `pwa-params-version`: PWA version block container
* `pwa-params-permission`: PWA permissions block container
* `pwa-params-permission-notification`: notification permission container
* `pwa-params-permission-geolocation`: geolocation permission container
* `pwa-name`: PWA name container
* `pwa-version`: PWA version container
* `pwa-permission-notifications-btn`: notifications permission button
* `pwa-permission-geolocation-btn`: geolocation permission button
* `pwa-permission-remove`: permission revocation container

```html
<button class="pwa-params-btn">
    Params
</button>

<div class="pwa-params">

    <div class="pwa-params-version">
        <p>Version</p>
        <p>
            <span class="pwa-name"></span> 
            <span class="pwa-version"></span>
        </p>
    </div>

    <div class="pwa-params-permission">
        <p>Permissions</p>
        <ul>
            <li class="pwa-params-permission-notification">
                <button class="pwa-permission-notifications-btn">
                </button>
                <span>I authorize to receive notifications</span>
            </li>
            <li class="pwa-params-permission-geolocation">
                <button class="pwa-permission-geolocation-btn">
                </button>
                <span>I authorize geolocation</span>
            </li>
        </ul>
        <div class="pwa-permission-remove">
            To remove permission, please go to your device or browser settings
        </div>
    </div>

    <button class="pwa-params-close-btn">
        Close
     </button>

</div>	
```

&nbsp;

## CSS

We hide the elements

```css
.pwa-params,
.pwa-params-btn,
.pwa-params-version,
.pwa-params-permission,
.pwa-params-permission-notification,
.pwa-params-permission-geolocation,
.pwa-permission-remove {
    display: none;
}
```

If the elements have the class `is-visible`, we display them

```css
.pwa-params.is-visible,
.pwa-params-btn.is-visible,
.pwa-params-version.is-visible,
.pwa-params-permission.is-visible,
.pwa-params-permission-notification.is-visible,
.pwa-params-permission-geolocation.is-visible,
.pwa-permission-remove.is-visible {
    display: block;
}
```

&nbsp;

## Function

```js
const pwaParams = async(
     release=true,
     notification=true,
     geolocation = true
) => {
     ...
}
```

### Selecting DOM elements

We set the DOM elements to be manipulated as variables

```js
const pwaParams = document.querySelector('.pwa-params')
const pwaParamsButton = document.querySelector('.pwa-params-btn')
const pwaParamsButtonClose = document.querySelector('.pwa-params-close-btn')
const pwaParamsVersion = document.querySelector('.pwa-params-version')
const pwaParamsPermission = document.querySelector('.pwa-params-permission')
const pwaParamsPermissionNotification = document.querySelector('.pwa-params-permission-notification')
const pwaParamsPermissionGeolocation = document.querySelector('.pwa-params-permission-geolocation')
const pwaAddName = document.querySelector('.pwa-name')
const pwaAddVersion = document.querySelector('.pwa-version')
```

### Serviceworker

We set the instance of the service worker of the application as a variable, which will be used to retrieve the version of the PWA

```js
const registration = await navigator.serviceWorker.getRegistration()
```

We make a request on the webmanifest file and we store the response in a variable

```js
const webmanifestResponse = await fetch(new Request(document.querySelector('link[rel="manifest"]').href))
```

We convert the response from JSON to a JavaScript object and store it in a variable

```js
const webmanifest = await webmanifestResponse.json()
```

### Settings button display

We retrieve the value of the 'utm_source' parameter from the URL string of the current page

```js
const utm_source = new URLSearchParams(window.location.search).get('utm_source')
```

If the utm_source parameter in the URL is equal to 'homescreen', the button is displayed

```js
if(utm_source == 'homescreen') {
     pwaParamsButton.classList.add('is-visible')
}
```

### PWA version retrieval

```js
const pwaVersion = async () => {
```

We send a message to the active Service Worker requesting the PWA version

```js
registration.active.postMessage('GET_VERSION')
```

When the Service Worker receives a message

```js
navigator.serviceWorker.addEventListener('message', function(event) {
```

If the message contains data, the value received is injected into the dom

```js
if (event. data) {
     pwaAddVersion.innerText = event.data
}
```

### PWA version display

If the 'version' parameter of the function is true

```js
if(version) {
```

We display the container of the version

```js
pwaParamsVersion.classList.add('is-visible')
```

We define the name of the PWA with the data of the Webmanifest file

```js
pwaAddName.innerText = webmanifest.name
```

We define the version of the PWA with the data of the Service Worker

```js
pwaVersion()
```

### Permission container display

If the 'notifications' and 'geolocation' parameters are both false, we hide the permissions container

```js
if (!(notifications) && !(geolocation)) {
     pwaParamsPermission.classList.remove('is-visible')
```

Otherwise, we display it

```js
} else {
     pwaParamsPermission.classList.add('is-visible')
}
```

### Viewing the notification permission container

If the 'notifications' parameter is true

```js
if (notifications) {
```

We display the container and the notification authorization

```js
pwaParamsPermissionNotification.classList.add('is-visible')
```

And we call the notification authorization request function

```js
pwaNotifications()
```

### View geolocation authorization container

If the 'notifications' parameter is true

```js
if (geolocation) {
```

We display the geolocation authorization container

```js
pwaParamsPermissionGeolocation.classList.add('is-visible')
```

And we call the geolocation authorization request function

```js
pwaGeolocation()
```

### PWA settings button

On click on the PWA settings button

```js
pwaParamsButton. addEventListener('click', async () => {
```

We display the PWA settings container

```js
pwaParams.classList.add('is-visible')
```

&nbsp;

### PWA settings container close button

On click on the close button of the PWA settings container

```js
pwaParamsButtonClose.addEventListener('click', async () => {
```

We hide the PWA settings container

```js
pwaParams.classList.remove('is-visible')
```

&nbsp;

## Function call

Here is the function call used on pwabunga.js

```js
pwaParams()
```

&nbsp;

## Complete code of the `pwaParams()` function

Here is the function call used on pwabunga.js

```js
const pwaParams = async (
    version = true, 
    notifications = true, 
    geolocation = true
) => {
    
    const pwaParams = document.querySelector('.pwa-params')
    const pwaParamsButton = document.querySelector('.pwa-params-btn')
    const pwaParamsButtonClose = document.querySelector('.pwa-params-close-btn')
    const pwaParamsVersion = document.querySelector('.pwa-params-version')
    const pwaParamsPermission = document.querySelector('.pwa-params-permission')
    const pwaParamsPermissionNotification = document.querySelector('.pwa-params-permission-notification')
    const pwaParamsPermissionGeolocation = document.querySelector('.pwa-params-permission-geolocation')
    const pwaAddName = document.querySelector('.pwa-name')
    const pwaAddVersion = document.querySelector('.pwa-version')
    
    const registration = await navigator.serviceWorker.getRegistration()
    
    const webmanifestResponse = await fetch(new Request(document.querySelector('link[rel="manifest"]').href))
    const webmanifest = await webmanifestResponse.json()
    
    const utm_source = new URLSearchParams(window.location.search).get('utm_source')
    
    if(utm_source == 'homescreen') {
        pwaParamsButton.classList.add('is-visible')
    }
    
    const pwaVersion = async () => {
        registration.active.postMessage('GET_VERSION')
        navigator.serviceWorker.addEventListener('message', function(event) {
            if (event.data) {
                pwaAddVersion.innerText = event.data
            }
        })
    }
    
    if(version) {
        pwaParamsVersion.classList.add('is-visible')
        pwaAddName.innerText = webmanifest.name
        pwaVersion()
    } 
    
    if (!(notifications) && !(geolocation)) {
        pwaParamsPermission.classList.remove('is-visible')
    } else {
        pwaParamsPermission.classList.add('is-visible')
    }
    
    if (notifications) {
        pwaParamsPermissionNotification.classList.add('is-visible')
        pwaNotifications()
    }
    
    if (geolocation) {
        pwaParamsPermissionGeolocation.classList.add('is-visible')
        pwaGeolocation()
    }
    
    pwaParamsButton.addEventListener('click', async () => {
        pwaParams.classList.add('is-visible')
    })
    
    pwaParamsButtonClose.addEventListener('click', async () => {
        pwaParams.classList.remove('is-visible')
    })
    
}
```

&nbsp;
