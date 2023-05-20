* [Documentation homepage](https://github.com/PwaBunga/documentation/)
* [Documentation of the PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)
* [Documentation of the PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/CSS.md)
* [Documentation of the PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/GEOLOCATION.md)

[Back to the documentation of PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/pwa/JS.md)

# `pwaGeolocation()`: Geolocation authorization request

The `pwaGeolocation()` function offers the user a button to authorize geolocation.

* Shows a button indicating the status of the geolocation authorization
* If the user has neither accepted nor refused the geolocation, displays the authorization request
* If the user has accepted, the button displays an explanation insert to revoke the authorization

&nbsp;

## HTML

In order for the function to be functional, these elements must be added to the DOM:

* `pwa-permission-geolocation-btn`: PWA geolocation permission request button
* `pwa-permission-remove`: Insert explaining the revocation of the authorization of the geolocation of the PWA

```html
<button class="pwa-permission-geolocation-btn">
     {...}
</button>

<div class="pwa-permission-remove">
     To remove permission, please go to your device or browser settings
</div>
```

&nbsp;

## CSS

We hide the elements

```css
.pwa-permission-geolocation-btn,
.pwa-permission-remove {
     display: none;
}
```

If the elements have the class `is-visible`, we display them

```css
.pwa-permission-geolocation-btn.is-visible,
.pwa-permission-remove.is-visible {
     display: block;
}
```

&nbsp;

## Function

```js
const pwaGeolocation = async() => {
     ...
}
```

### Selecting DOM elements

We set the DOM elements to be manipulated as variables

```js
const pwaPermissionGeolocationBtn = document.querySelector('.pwa-permission-geolocation-btn')
const pwaPermissionRemove = document.querySelector('.pwa-permission-remove')
```

### Display authorization status

If the user has accepted geolocation

```js
   const permissionStatus = await navigator.permissions.query({ name: 'geolocation' });
   if (permissionStatus.state === "granted") {
```

We add the `is-active` class to the button

```js
pwaPermissionGeolocationBtn.classList.add('is-active')
```

### Request for authorization of geolocation and recovery of the user's position

```js
const pwaGeolocationCurrentPosition = async () => {
```

To display the geolocation authorization request prompt, we retrieve the user's position

```js
navigator.geolocation.getCurrentPosition(function(position) {
     console.log('Latitude:' + position.coords.latitude);
     console.log('Longitude:' + position.coords.longitude);
```

We add the `is-active` class to the button

```js
pwaPermissionGeolocationBtn.classList.add('is-active')
```

### Permission request button

```js
pwaPermissionGeolocationBtn.addEventListener('click', async () => {
```

If the user has already accepted geolocation

```js
if(pwaPermissionGeolocationBtn.classList.contains('is-active')) {
```

The authorization revocation explanation insert is displayed

```js
pwaPermissionRemove.classList.add('is-visible')
```

Otherwise, authorization is requested by retrieving the position of the user

```js
pwaGeolocationCurrentPosition()
```

### Closing the permission revocation explanation box

If you click on the insert

```js
pwaPermissionRemove.addEventListener('click', async () => {
```

We hide the permission revocation explanation insert

```js
pwaPermissionRemove.classList.remove('is-visible')
```

&nbsp;

## Function call

```js
pwaGeolocation()
```

On pwabunga.js, the `pwaGeolocation()` function is called in the `pwaParams()` function

&nbsp;

## Complete code of the `pwaGeolocation()` function

```js
const pwaGeolocation = async () => {

    const pwaPermissionGeolocationBtn = document.querySelector('.pwa-permission-geolocation-btn')
    const pwaPermissionRemove         = document.querySelector('.pwa-permission-remove')

    const permissionStatus = await navigator.permissions.query({ name: 'geolocation' });
    if (permissionStatus.state === "granted") {
        pwaPermissionGeolocationBtn.classList.add('is-active')
    }

    const pwaGeolocationCurrentPosition = async () => {
        navigator.geolocation.getCurrentPosition(function(position) {
            console.log('Latitude:' + position.coords.latitude);
            console.log('Longitude:' + position.coords.longitude);
            pwaPermissionGeolocationBtn.classList.add('is-active')
        })
    }

    pwaPermissionGeolocationBtn.addEventListener('click', async () => {
        if(pwaPermissionGeolocationBtn.classList.contains('is-active')) {
            pwaPermissionRemove.classList.add('is-visible')
        } else {
            pwaGeolocationCurrentPosition()
        }
    })

    pwaPermissionRemove.addEventListener('click', async () => {
        pwaPermissionRemove.classList.remove('is-visible')
    })

}
```

&nbsp;
