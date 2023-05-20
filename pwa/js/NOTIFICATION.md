* [Documentation homepage](https://github.com/PwaBunga/documentation/)
* [Documentation of the PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)
* [Documentation of the PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/CSS.md)
* [Documentation of the PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/NOTIFICATION.md)

[Back to the documentation of PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/pwa/JS.md)


# `pwaNotifications()`: Notification authorization request

The `pwaNotifications()` function offers the user a button to authorize the sending of notifications.

* Shows a button indicating the status of permission to send notifications
* If the user has neither accepted nor refused the sending of notifications, displays the authorization request
* If the user has accepted, the button displays an explanation insert to revoke the authorization

&nbsp;

## HTML

In order for the function to be functional, these elements must be added to the DOM:

* `pwa-permission-notifications-btn`: PWA notifications permission request button
* `pwa-permission-remove`: PWA notifications permission revocation explanation insert

```html
<button class="pwa-permission-notifications-btn">
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
.pwa-permission-notifications-btn,
.pwa-permission-remove {
    display: none;
}
```

If the elements have the class `is-visible`, we display them

```css
.pwa-permission-notifications-btn.is-visible,
.pwa-permission-remove.is-visible {
    display: block;
}
```

&nbsp;

## Function

```js
const pwaNotifications = async() => {
     ...
}
```

### Selecting DOM elements

We set the DOM elements to be manipulated as variables

```js
const pwaPermissionNotificationsBtn = document.querySelector('.pwa-permission-notifications-btn')
const pwaPermissionRemove = document.querySelector('.pwa-permission-remove')
```

### Display authorization status

If the user has accepted the sending of notifications, we add the is-active class to the button

```js
if (Notification. permission === 'granted') {
     pwaPermissionNotificationsBtn.classList.add('is-active')
}
```

Otherwise we remove the `is-active` class from the button

```js
else {
     pwaPermissionNotificationsBtn.classList.remove('is-active')
}
```

### Request for authorization to send notifications

```js
const pwaNotificationsPermission = async () => {
```

If the user has not opted out of sending notifications

```js
if (Notification. permission !== 'denied') {
```

User permission is requested

```js
const permission = await Notification.requestPermission()
```

If the user accepts

```js
if(permission == "granted"){
```

We add the `is-active` class to the button

```js
pwaPermissionNotificationsBtn.classList.add('is-active')
```

### Permission request button

```js
pwaPermissionNotificationsBtn.addEventListener('click', async () => {
```

If the user has already accepted the sending of notifications

```js
if(pwaPermissionNotificationsBtn.classList.contains('is-active')) {
```

The authorization revocation explanation insert is displayed

```js
pwaPermissionRemove.classList.add('is-visible')
```

Otherwise, permission is requested.

```js
pwaNotificationsPermission()
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
pwaNotifications()
```

On pwabunga.js, the `pwaNotifications()` function is called in the `pwaParams()` function

&nbsp;

## Code complet de la fonction `pwaNotifications()`

```js
const pwaNotifications = async () => {
    
    const pwaPermissionNotificationsBtn = document.querySelector('.pwa-permission-notifications-btn')
    const pwaPermissionRemove           = document.querySelector('.pwa-permission-remove')
    
    if (Notification.permission === 'granted') { 
        pwaPermissionNotificationsBtn.classList.add('is-active')
    } else {
        pwaPermissionNotificationsBtn.classList.remove('is-active')
    }

    const pwaNotificationsPermission = async () => {
        if (Notification.permission !== 'denied') { 
            const permission = await Notification.requestPermission()
            if(permission == "granted"){ 
                pwaPermissionNotificationsBtn.classList.add('is-active')
            } 
        } 
    }
    
    pwaPermissionNotificationsBtn.addEventListener('click', async () => {
        if(pwaPermissionNotificationsBtn.classList.contains('is-active')) {
            pwaPermissionRemove.classList.add('is-visible')
        } else {
            pwaNotificationsPermission()
        }
    })

    pwaPermissionRemove.addEventListener('click', async () => {
        pwaPermissionRemove.classList.remove('is-visible')
    })
    
}  
```

&nbsp;
