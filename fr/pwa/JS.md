* [Accueil de la documentation](https://github.com/PwaBunga/documentation/blob/main/fr/)
* [Documentation du module PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md)
* [Documentation du module PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md)
* [Documentation du module PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/fr/PWA.md)
  - [Webmanifest](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md)
  - [Icônes](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md)
  - [Service worker](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md)
  - [pwabunga.js](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md)
  - [pwabunga-ui.css](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[English version](https://github.com/PwaBunga/documentation/blob/main/pwa/JS.md)

# PWA Bunga! PWA JS

Ce fichier contient des fonctions qui vont permettre à votre application web d'avoir une expérience utilisateur améliorée, similaire à celle d'une application native installée sur un appareil mobile ou un ordinateur.

Le fichier `pwabunga.js` de PWA Bunga! va permettre :

* D'**enregistrer du service worker**
* D'**améliorer le processus d'installation**, de **mise à jour** et de **partage** de la PWA.
* De **demander à l'utilisateur l'autorisation** pour les **notifications** et la **géolocalisation**.

&nbsp;

* **`pwabunga.js`**

&nbsp;

## Enregistrement du Service worker

### `pwaRegister()` : Enregistrement du Service worker

La fonction `pwaRegister()` permet l'enregistrement du service worker, à savoir le créer ou le mettre à jour.

[Voir la documentation de la fonction `pwaRegister()`](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/REGISTER.md)

&nbsp;

## Amélioration de l'expérience utilisateur

### `pwaInstall()` : Promotion et bouton d'installation de la PWA

La fonction `pwaInstall()` permet d'améliorer l'expérience utilisateur en personnalisant tout le processus d'installation de la PWA.

[Voir la documentation de la fonction `pwaInstall()`](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/INSTALL.md)

### `pwaUpdate()` : Mise à jour de l'application

La fonction `pwaUpdate()` permet d'améliorer l'expérience lors des mises à jour de la PWA.

[Voir la documentation de la fonction `pwaUpdate()`](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/UPDATE.md)

### `pwaShare()` : Utilisation du partage natif de l'appareil

La fonction `pwaShare()` permet d'améliorer l'expérience utilisateur du partage de l'application sur les réseaux sociaux.

[Voir la documentation de la fonction `pwaShare()`](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/SHARE.md)

### `pwaParams()` : Encart des paramètres de la PWA

La fonction `pwaParams()` propose un encart de paramètres avec l'affichage de la version de la PWA et la gestion des autorisations.

[Voir la documentation de la fonction `pwaParams()`](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/PARAMS.md)

&nbsp;

## Autorisations

### `pwaNotification()` : Demande d'autorisation de l'envoi des notifications

La fonction `pwaNotification()` permet de proposer à l'utilisateur un bouton pour autoriser l'envoi des notifications.

[Voir la documentation de la fonction `pwaNotification()`](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/NOTIFICATION.md)

### `pwaGeolocation()` : Demande d'autorisation de la géolocalisation

La fonction `pwaGeolocation()` permet de proposer à l'utilisateur un bouton pour autoriser la géolocalisation.

[Voir la documentation de la fonction `pwaGeolocation()`](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/GEOLOCATION.md)

&nbsp;
