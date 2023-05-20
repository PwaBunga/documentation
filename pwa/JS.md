* [Documentation homepage](https://github.com/PwaBunga/documentation/)
* [Documentation of the PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)
* [Documentation of the PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/CSS.md)
* [Documentation of the PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/PWA.md)
  - [Webmanifest](https://github.com/PwaBunga/documentation/blob/main/pwa/WEBMANIFEST.md)
  - [Icons](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONS.md)
  - [Service worker](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md)
  - [pwabunga.js](https://github.com/PwaBunga/documentation/blob/main/pwa/JS.md)
  - [pwabunga-ui.css](https://github.com/PwaBunga/documentation/blob/main/pwa/CSS_UI.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md)

# PWA Bunga! PWA JS

This file contains functions that will allow your web application to have an improved user experience, similar to that of a native application installed on a mobile device or a computer.

The `pwabunga.js` file of PWA Bunga! will allow :

* To **record service worker**
* To **improve the process of installing**, **updating** and **sharing** of the PWA.
* To **ask user for permission** for **notifications** and **geolocation**.

&nbsp;

* **`pwabunga.js`**

&nbsp;

## Service worker registration

### `pwaRegister()`: Service worker registration

The `pwaRegister()` function allows the registration of the service worker, namely creating or updating it.

[See the documentation for the `pwaRegister()` function](https://github.com/PwaBunga/documentation/blob/main/pwa/js/REGISTER.md)

&nbsp;

## Improved user experience

### `pwaInstall()`: Promotion and PWA install button

The `pwaInstall()` function improves the user experience by customizing the entire PWA installation process.

[See the documentation for the `pwaInstall()` function](https://github.com/PwaBunga/documentation/blob/main/pwa/js/INSTALL.md)

### `pwaUpdate()`: Application update

The `pwaUpdate()` function improves the experience when updating the PWA.

[See the documentation for the `pwaUpdate()` function](https://github.com/PwaBunga/documentation/blob/main/pwa/js/UPDATE.md)

### `pwaShare()`: Using native device sharing

The `pwaShare()` function improves the user experience of sharing the application on social networks.

[See the documentation for the `pwaShare()` function](https://github.com/PwaBunga/documentation/blob/main/pwa/js/SHARE.md)

### `pwaParams()`: PWA parameters insert

The `pwaParams()` function offers a parameter insert with the display of the PWA version and the management of authorizations.

[See the documentation for the `pwaParams()` function](https://github.com/PwaBunga/documentation/blob/main/pwa/js/PARAMS.md)

&nbsp;

## Permissions

### `pwaNotification()`: Request authorization to send notifications

The `pwaNotification()` function offers the user a button to authorize the sending of notifications.

[See the documentation for the `pwaNotification()` function](https://github.com/PwaBunga/documentation/blob/main/pwa/js/NOTIFICATION.md)

### `pwaGeolocation()`: Geolocation authorization request

The `pwaGeolocation()` function offers the user a button to authorize geolocation.

[See the documentation for the `pwaGeolocation()` function](https://github.com/PwaBunga/documentation/blob/main/pwa/js/GEOLOCATION.md)

&nbsp;