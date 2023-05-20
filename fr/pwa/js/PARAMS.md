* [Accueil de la documentation](https://github.com/PwaBunga/documentation/blob/main/fr/)
* [Documentation du module PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md)
* [Documentation du module PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md)
* [Documentation du module PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/fr/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[English version](https://github.com/PwaBunga/documentation/blob/main/pwa/js/PARAMS.md)

[Retour à la documentation de PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md)


# `pwaParams()` : Encart des paramètres de la PWA

Toujours dans l'optique d'offrir une expérience utilisateur la plus proche possible des applications natives, la fonction `pwaParams()` va permettre de proposer à l'utilisateur un encart de configuration permettant d'afficher la version de la PWA, ainsi qu'une gestion des autorisations.

Cette fonction nécessite la présence des fonctions `pwaNotifications()` et `pwaGeolocation()`, qui vont permettre de gérer les boutons d'autorisations de l'encart paramètres.

&nbsp;

## Paramètres de la fonction

Cette fonction prend 3 paramètres :

* `version` : Affiche / Cache la version de la PWA dans l'encart de paramètres (Booléen, valeur par défaut : true)
* `notifications` : Affiche / Cache le bouton d'autorisation des notifications dans l'encart de paramètres (Booléen, valeur par défaut : true)
* `geolocation` : Affiche / Cache le bouton d'autorisation de la géolocalisation dans l'encart de paramètres (Booléen, valeur par défaut : true)

```js
const pwaParams = async (version = true, notifications = true, geolocation = true) 
```

&nbsp;

## HTML

Afin que la fonction soit fonctionnelle, il faut ajouter ces éléments au DOM :

* `pwa-params` : conteneur de l'encart des paramètres de la PWA
* `pwa-params-btn` : bouton d'ouverture de l'encart des paramètres de la PWA
* `pwa-params-close-btn` : bouton de fermeture de l'encart des paramètres de la PWA
* `pwa-params-version` : conteneur du bloc de la version de la PWA
* `pwa-params-permission` : conteneur du bloc des permissions de la PWA
* `pwa-params-permission-notification` : conteneur de la permission de notifications
* `pwa-params-permission-geolocation` : conteneur de la permission de géolocalisation
* `pwa-name` : conteneur du nom de la PWA
* `pwa-version` : conteneur du la version de la PWA
* `pwa-permission-notifications-btn` : bouton de permission des notifications
* `pwa-permission-geolocation-btn` : bouton de permission de la géolocalisation
* `pwa-permission-remove` : conteneur de la révocation des permissions

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

On cache les éléments

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

Si les éléments ont la classe `is-visible`, on  les affichent

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

## La fonction

```js
const pwaParams = async (
    version = true, 
    notifications = true, 
    geolocation = true
) => {
    ...
}
```

### Sélection des éléments du DOM

Nous mettons en variable les éléments du DOM à manipuler

```js
const pwaParams                       = document.querySelector('.pwa-params')
const pwaParamsButton                 = document.querySelector('.pwa-params-btn')
const pwaParamsButtonClose            = document.querySelector('.pwa-params-close-btn')
const pwaParamsVersion                = document.querySelector('.pwa-params-version')
const pwaParamsPermission             = document.querySelector('.pwa-params-permission')
const pwaParamsPermissionNotification = document.querySelector('.pwa-params-permission-notification')
const pwaParamsPermissionGeolocation  = document.querySelector('.pwa-params-permission-geolocation')
const pwaAddName                      = document.querySelector('.pwa-name')
const pwaAddVersion                   = document.querySelector('.pwa-version')
```

### Serviceworker

On met en variable l'instance du service worker de l'application, qui va nous servir à récupérer la version de la PWA

```js
const registration = await navigator.serviceWorker.getRegistration()
```

On fait une requête sur le fichier webmanifest et on stocke la réponse dans une variable

```js
const webmanifestResponse = await fetch(new Request(document.querySelector('link[rel="manifest"]').href))
```

On convertit la réponse de JSON en un objet JavaScript et la stocke dans une variable

```js
const webmanifest = await webmanifestResponse.json()
```

### Affichage du bouton des paramètres

On récupère la valeur du paramètre 'utm_source' de la chaîne de l'URL de la page en cours

```js
const utm_source = new URLSearchParams(window.location.search).get('utm_source')
```

Si le paramètre utm_source dans l'URL est égal à 'homescreen', on affiche le bouton

```js
if(utm_source == 'homescreen') {
    pwaParamsButton.classList.add('is-visible')
}
```

### Récupération de la version de la PWA

```js
const pwaVersion = async () => {
```

On envoie un message au Service Worker actif demandant la version PWA

```js
registration.active.postMessage('GET_VERSION')
```

Lorsque le Service Worker reçoit un message

```js
navigator.serviceWorker.addEventListener('message', function(event) {
```

Si le message contient des données, on injecte dans le dom la valeur reçue

```js
if (event.data) {
    pwaAddVersion.innerText = event.data
}
```

### Affichage de la version de la PWA

Si le paramètre 'version' de la fonction a la valeur true

```js
if(version) {
```

On affiche le conteneur de la version

```js
pwaParamsVersion.classList.add('is-visible')
```

On définit le nom de la PWA avec les données du fichier Webmanifest

```js
pwaAddName.innerText = webmanifest.name
```

On définit la version de la PWA avec les données du Service Worker

```js
pwaVersion()
```

### Affichage du conteneur des autorisations

Si les paramètres 'notifications' et 'géolocalisation' sont tous les deux à false, on cache le conteneur des autorisations

```js
if (!(notifications) && !(geolocation)) { 
    pwaParamsPermission.classList.remove('is-visible')
```

Sinon, on l'affiche

```js
} else {
    pwaParamsPermission.classList.add('is-visible')
}
```

### Affichage du conteneur de l'autorisation des notifications

Si le paramètre 'notifications' est à true

```js
if (notifications) {
```

On affiche le conteneur e l'autorisation des notifications

```js
pwaParamsPermissionNotification.classList.add('is-visible')
```

Et on appelle la fonction de demande de d'autorisation des notifications

```js
pwaNotifications()
```

### Affichage du conteneur de l'autorisation de la géolocalisation

Si le paramètre 'notifications' est à true

```js
if (geolocation) {
```

On affiche le conteneur de l'autorisation de la géolocalisation

```js
pwaParamsPermissionGeolocation.classList.add('is-visible')
```

Et on appelle la fonction de demande de d'autorisation de la géolocalisation

```js
pwaGeolocation()
```

### Bouton des paramètres de la PWA

Au clic sur le bouton des paramètres de la PWA

```js
pwaParamsButton.addEventListener('click', async () => {
```

On affiche le conteneur des paramètres de la PWA

```js
pwaParams.classList.add('is-visible')
```

&nbsp;

### Bouton de fermeture du conteneur des paramètres de la PWA

Au clic sur le bouton de fermeture du conteneur des paramètres de la PWA

```js
pwaParamsButtonClose.addEventListener('click', async () => {
```

On cache le conteneur des paramètres de la PWA

```js
pwaParams.classList.remove('is-visible')
```

&nbsp;

## Appel de la fonction

Voici l'appel de la fonction utilisé sur pwabunga.js

```js
pwaParams()
```

&nbsp;

## Code complet de la fonction `pwaParams()`

Voici l'appel de la fonction utilisé sur pwabunga.js

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
