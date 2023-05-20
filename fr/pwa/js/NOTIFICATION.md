* [Accueil de la documentation](https://github.com/PwaBunga/documentation/blob/main/fr/)
* [Documentation du module PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md)
* [Documentation du module PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md)
* [Documentation du module PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/fr/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[English version](https://github.com/PwaBunga/documentation/blob/main/pwa/js/NOTIFICATION.md)

[Retour à la documentation de PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md)


# `pwaNotifications()` : Demande d'autorisation des notifications

La fonction `pwaNotifications()` permet de proposer à l'utilisateur un bouton pour autoriser l'envoi de notifications.

* Affiche un bouton indiquant l'état de l'autorisation de l'envoi des notifications
* Si l'utilisateur n'a ni accepté, ni refusé l'envoi des notifications, affiche la demande d'autorisation
* Si l'utilisateur a accepté, le bouton affiche un encart d'explications pour révoquer l'autorisation

&nbsp;

## HTML

Afin que la fonction soit fonctionnelle, il faut ajouter ces éléments au DOM :

* `pwa-permission-notifications-btn` : bouton de demande d'autorisation des notifications de la PWA
* `pwa-permission-remove` : Encart d'explications de révocation de l'autorisation des notifications de la PWA

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

On cache les éléments

```css
.pwa-permission-notifications-btn,
.pwa-permission-remove {
    display: none;
}
```

Si les éléments ont la classe `is-visible`, on les affichent

```css
.pwa-permission-notifications-btn.is-visible,
.pwa-permission-remove.is-visible {
    display: block;
}
```

&nbsp;

## La fonction

```js
const pwaNotifications = async () => {
    ...
}
```

### Sélection des éléments du DOM

Nous mettons en variable les éléments du DOM à manipuler

```js
const pwaPermissionNotificationsBtn = document.querySelector('.pwa-permission-notifications-btn')
const pwaPermissionRemove = document.querySelector('.pwa-permission-remove')
```

### Affichage de l'état de l'autorisation

Si l'utilisateur a accepté l'envoi des notifications, on ajoute la classe is-active au bouton

```js
if (Notification.permission === 'granted') { 
    pwaPermissionNotificationsBtn.classList.add('is-active')
}
```

Sinon on enlève la classe `is-active` au bouton

```js
else {
    pwaPermissionNotificationsBtn.classList.remove('is-active')
}
```

### Demande d'autorisation de l'envoi des notifications

```js
const pwaNotificationsPermission = async () => {
```

Si l'utilisateur n'a pas refusé l'envoi des notifications

```js
if (Notification.permission !== 'denied') { 
```

On demande l'autorisation à l'utilisateur

```js
const permission = await Notification.requestPermission()
```

Si l'utilisateur accepte

```js
if(permission == "granted"){ 
```

On ajoute la classe `is-active` au bouton

```js
pwaPermissionNotificationsBtn.classList.add('is-active')
```

### Bouton de demande d'autorisation

```js
pwaPermissionNotificationsBtn.addEventListener('click', async () => {
```

Si l'utilisateur a déjà accepté l'envoi des notifications

```js
if(pwaPermissionNotificationsBtn.classList.contains('is-active')) {
```

On affiche l'encart d'explications de révocation de l'autorisation

```js
pwaPermissionRemove.classList.add('is-visible')
```

Sinon, on demande l'autorisation

```js
pwaNotificationsPermission()
```

### Fermeture de l'encart d'explications de révocation de l'autorisation

Si on clique sur l'encart

```js
pwaPermissionRemove.addEventListener('click', async () => {
```

On cache l'encart d'explications de révocation de l'autorisation

```js
pwaPermissionRemove.classList.remove('is-visible')
```

&nbsp;

## Appel de la fonction

```js
pwaNotifications()
```

Sur pwabunga.js, la fonction `pwaNotifications()` est appelé dans la `fonction pwaParams()`

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
