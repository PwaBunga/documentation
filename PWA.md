* [Documentation homepage](https://github.com/PwaBunga/documentation/)
* [Documentation of the PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)
* [Documentation of the PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/CSS.md)
* [Documentation of the PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/PWA.md)

# PWA Bunga! PWA

A PWA (Progressive Web App) is a web application that uses the latest web technologies to provide a similar user experience to that of a native application. Unlike native apps, PWAs do not require download from a store applications and can be used directly from a web browser.

They are designed to be reliable, fast and engaging, allowing users to access an offline version of the application, to receive push notifications, to adapt to different screen sizes and to integrate with other system features, such as camera or microphone.

PWAs have a wider reach than native applications because they can be used on different types of devices (smartphones, tablets, desktops) and on different web browsers (Chrome, Firefox, Safari, etc.). This means that we can create a single PWA that will work for all users, instead of having to create multiple versions for each platform or operating system.

They also have other advantages such as the fact that they are web applications, which means that they are accessible via a browser and therefore easily indexable by search engines.

PWAs are growing in popularity as they offer a cheaper and more accessible alternative to native apps. while providing a similar quality user experience.

&nbsp;

## Content of PWA Bunga! PWA

In order to set up your PWA, you will find in PWA Bunga! PWAs:

* **The icon files**: It is important to have icons of different sizes for the application, so that it can adapt to different screens and be installed on the screen device home.
* **The app.webmanifest file**: This file contains app metadata, such as its name, description, icon, and theme color. It also allows the app to be installed on the home screen of the device.
* **The serviceworker.js file**: This is a JavaScript script that runs in the background and allows the application to be available offline. The service worker can cache resources for later use, which improves application loading speed.
* **The pwabunga.js file**: This file will register the Service worker and provide functions to improve the user experience of PWA events.
* **The  pwabunga-ui.css file**: An optional CSS file for styling UI elements used by pwabunga.js.

&nbsp;

## Summary of PWA documentation Bunga! PWAs

### [Webmanifest](https://github.com/PwaBunga/documentation/blob/main/pwa/WEBMANIFEST.md)

* [General PWA Information](https://github.com/PwaBunga/documentation/blob/main/pwa/WEBMANIFEST.md#general-information-about-the-pwa)
* [Navigating the PWA](https://github.com/PwaBunga/documentation/blob/main/pwa/WEBMANIFEST.md#navigating-the-pwa)
* [PWA Theme](https://github.com/PwaBunga/documentation/blob/main/pwa/WEBMANIFEST.md#pwa-theme)

### [Icons](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONS.md)

* [Icons and Touch icons for application environments and older versions of Android](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#icons-and-touch-icons-for-application-environments-and-older-versions-of-android)
  - [Icon display](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#icon-display)
  - [Icon dimensions](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#icon-dimensions)
  - [Call icons](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#call-icons)
* [Maskable icons: adaptive icons for the Android environment](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#maskable-icons-adaptive-icons-for-the-android-environment)
  - [Safe area and adaptive icon shapes](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#safe-area-and-adaptive-icon-shapes)
  - [Display of adaptive icons](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#display-of-adaptive-icons)
  - [Call for adaptive icons](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#call-for-adaptive-icons)
* [Touch icon for iOS environment](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#touch-icon-for-ios-environment)
  - [Formats and dimensions of apple-touch-icon.png](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#formats-and-dimensions-of-apple-touch-iconpng)

### [Service worker](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md)

* [Configuring cache and request processing](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#configuring-cache-and-request-processing)
  - [Cache name and version](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#cache-name-and-version)
  - [Cached Resources](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#cached-resources)
  - [Choice of request processing strategy](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#choice-of-request-processing-strategy)
  - [Declaration of a dynamic folder](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#declaration-of-a-dynamic-folder)
* [Cache manipulation](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#cache-manipulation)
  - [Add resources to cache](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#add-resources-to-cache)
  - [Update cache resources](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#update-cache-resources)
  - [Deleting a cache instance](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#deleting-a-cache-instance)
  - [Removing older versions from cache](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#removing-older-versions-from-cache)
* [Query Processing Strategies](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#query-processing-strategies)
  - [Cache only](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#cache-only)
  - [Network only](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#network-only)
  - [Cache first](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#cache-first)
  - [Network first](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#network-first)
  - [Stale While Revalidate](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#stale-while-revalidate)
* [Service worker events](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#service-worker-events)
  - [Install event](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#install-event)
  - [Activate event](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#activate-event)
  - [Message event](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#message-event)
  - [Fetch event](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#fetch-event)

### [pwabunga.js](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md)

* [Service worker registration](https://github.com/PwaBunga/documentation/blob/main/en/pwa/JS.md#service-worker-registration)
   - [pwaRegister function](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/REGISTER.md)
* [Improved user experience](https://github.com/PwaBunga/documentation/blob/main/en/pwa/JS.md#am%C3%A9lioration-de-lexp%C3%A9rience-USER)
   - [pwaInstall function](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/INSTALL.md)
   - [pwaUpdate function](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/UPDATE.md)
   - [pwaShare function](https://github.com/PwaBunga/documentation/blob/main/en/pwa/js/SHARE.md)
   - [pwaParams function](https://github.com/PwaBunga/documentation/blob/main/en/pwa/js/PARAMS.md)
* [Permissions](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md#permissions)
   - [pwaNotification function](https://github.com/PwaBunga/documentation/blob/main/en/pwa/js/NOTIFICATION.md)
   - [pwaGeolocation function](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/GEOLOCATION.md)

### [pwabunga-ui.css](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md)

* [Variables](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#variables)
* [PWA UI components](https://github.com/PwaBunga/documentation/blob/main/en/pwa/CSS_UI.md#pwa-user-interface-components)
   - [Buttons](https://github.com/PwaBunga/documentation/blob/main/en/pwa/CSS_UI.md#buttons)
   - [PWA Banner](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#pwa-banner)
   - [PWA Modal](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#pwa-modal)
   - [PWA Switch](https://github.com/PwaBunga/documentation/blob/main/en/pwa/CSS_UI.md#pwa-switch)
   - [PWA Alert](https://github.com/PwaBunga/documentation/blob/main/en/pwa/CSS_UI.md#pwa-alert)
   - [PWA Loader](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#pwa-loader)
* [Additional Styles](https://github.com/PwaBunga/documentation/blob/main/en/pwa/CSS_UI.md#additional-styles)
   - [PWA action bar](https://github.com/PwaBunga/documentation/blob/main/en/pwa/CSS_UI.md#pwa-action-bar)
   - [Element version of the pwaParams() function](https://github.com/PwaBunga/documentation/blob/main/en/pwa/CSS_UI.md#element-version-of-the-function-pwaparams)
   - [Listing of authorizations](https://github.com/PwaBunga/documentation/blob/main/en/pwa/CSS_UI.md#listing-of-authorizations)
* [States of elements useful for pwabunga.js functions](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#etats-des-objets-utiles-aux-fonctions- de-pwabungajs)
   - [PwaInstall() function installation button](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#bouton-dinstallation-de-la-fonction-pwainstall)
   - [PwaShare() function share button](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#bouton-de-partage-de-la-fonction-pwashare )
   - [Elements of the pwaParams() function](https://github.com/PwaBunga/documentation/blob/main/en/pwa/CSS_UI.md#elements-of-the-pwaparams-function)

&nbsp;

## Contribute

To contribute, you can use the issue trackers of the PWA Bunga! Starter module repository.

* [https://github.com/PwaBunga/pwa/issues](https://github.com/PwaBunga/pwa/issues)

The modifications made on this repository will then be made on the main repository of the project.

The issue tracker is the preferred channel for bug reports, features requests and submitting pull requests, but please respect the following restrictions:

* Please **do not** use the issue tracker for personal support requests.
* Please **do not** derail or troll issues. Keep the discussion on topic and= respect the opinions of others.

&nbsp;