* [Accueil de la documentation](https://github.com/PwaBunga/documentation/blob/main/fr/)
* [Documentation du module PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md)
* [Documentation du module PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md)
* [Documentation du module PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/fr/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[English version](https://github.com/PwaBunga/documentation/blob/main/pwa/js/GEOLOCATION.md)

[Retour à la documentation de PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md)


# `pwaGeolocation()` : Demande d'autorisation de la géolocalisation

La fonction `pwaGeolocation()` permet de proposer à l'utilisateur un bouton pour autoriser la géolocalisation.

* Affiche un bouton indiquant l'état de l'autorisation de la géolocalisation
* Si l'utilisateur n'a ni accepté, ni refusé la géolocalisation, affiche la demande d'autorisation
* Si l'utilisateur a accepté, le bouton affiche un encart d'explications pour révoquer l'autorisation

&nbsp;

## HTML

Afin que la fonction soit fonctionnelle, il faut ajouter ces éléments au DOM :

* `pwa-permission-geolocation-btn` : bouton de demande d'autorisation de la géolocalisation de la PWA
* `pwa-permission-remove` : Encart d'explications de révocation de l'autorisation de la géolocalisation de la PWA

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

On cache les éléments

```css
.pwa-permission-geolocation-btn,
.pwa-permission-remove {
    display: none;
}
```

Si les éléments ont la classe `is-visible`, on les affichent

```css
.pwa-permission-geolocation-btn.is-visible,
.pwa-permission-remove.is-visible {
    display: block;
}
```

&nbsp;

## La fonction

```js
const pwaGeolocation = async () => {
    ...
}
```

### Sélection des éléments du DOM

Nous mettons en variable les éléments du DOM à manipuler

```js
const pwaPermissionGeolocationBtn = document.querySelector('.pwa-permission-geolocation-btn')
const pwaPermissionRemove         = document.querySelector('.pwa-permission-remove')
```

### Affichage de l'état de l'autorisation

Si l'utilisateur a accepté la géolocalisation

```js
  const permissionStatus = await navigator.permissions.query({ name: 'geolocation' });
  if (permissionStatus.state === "granted") {
```

On ajoute la classe `is-active` au bouton

```js
pwaPermissionGeolocationBtn.classList.add('is-active')
```

### Demande d'autorisation de la géolocalisation et récupération de la position de l'utilisateur

```js
const pwaGeolocationCurrentPosition = async () => {
```

Pour faire apparaitre le prompt de demande d'autorisation de la géolocalisation, on récupère la position de l'utilisateur

```js
navigator.geolocation.getCurrentPosition(function(position) {
    console.log('Latitude:' + position.coords.latitude);
    console.log('Longitude:' + position.coords.longitude);
```

On ajoute la classe `is-active` au bouton

```js
pwaPermissionGeolocationBtn.classList.add('is-active')
```

### Bouton de demande d'autorisation

```js
pwaPermissionGeolocationBtn.addEventListener('click', async () => {
```

Si l'utilisateur a déjà accepté la géolocalisation

```js
if(pwaPermissionGeolocationBtn.classList.contains('is-active')) {
```

On affiche l'encart d'explications de révocation de l'autorisation

```js
pwaPermissionRemove.classList.add('is-visible')
```

Sinon, on demande l'autorisation en récupérant la position de l'utilisateur

```js
pwaGeolocationCurrentPosition()
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
pwaGeolocation()
```

Sur pwabunga.js, la fonction `pwaGeolocation()` est appelé dans la `fonction pwaParams()`

&nbsp;

## Code complet de la fonction `pwaGeolocation()`

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
