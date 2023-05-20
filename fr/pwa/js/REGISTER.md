* [Accueil de la documentation](https://github.com/PwaBunga/documentation/blob/main/fr/)
* [Documentation du module PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md)
* [Documentation du module PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md)
* [Documentation du module PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/fr/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[English version](https://github.com/PwaBunga/documentation/blob/main/pwa/js/REGISTER.md)

[Retour à la documentation de PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md)

# `pwaRegister()` : Enregistrement du Service worker

La fonction `pwaRegister()` va permettre l'enregistrement du service worker, à savoir le créer ou le mettre à jour.

&nbsp;

## Paramètre de la fonction

Cette fonction prend en paramètre l'url du service worker (relative ou absolue)

```js
pwaRegister(file)
```

### Valeur par défaut

Par défaut la valeur de `file` est `serviceworker.js`

&nbsp;

## La fonction

On teste si le navigateur prend en charge les service workers

```js
if ("serviceWorker" in navigator) {
    ...
}
```

On essaie d'enregistrer le service worker

```js
try {
    const registration = await navigator.serviceWorker.register(file);
    ...
} 
```

Si l'enregistrement du service worker s'effectue, on renvoi son état dans la console

```js
if (registration.installing) {
    console.log("Service worker installing")
} else if (registration.waiting) {
    console.log("Service worker installed")
} else if (registration.active) {
    console.log("Service worker active")
}
```

Sinon, on renvoi l'erreur dans la console

```js
catch (error) {
    console.error(`Registration failed with ${error}`)
}
```

### Fonction complète

```js
const pwaRegister = async (file = 'serviceworker.js') => {
    if ("serviceWorker" in navigator) {
        try {
            const registration = await navigator.serviceWorker.register(file);
            if (registration.installing) {
                console.log("Service worker installing")
            } else if (registration.waiting) {
                console.log("Service worker installed")
            } else if (registration.active) {
                console.log("Service worker active")
            }
        } 
        catch (error) {
            console.error(`Registration failed with ${error}`)
        }
    }
}
```

&nbsp;

## Appel de la fonction

Voici l'appel de la fonction utilisé sur pwabunga.js appelant le fichier `serviceworker.js` présent à la racine de la PWA

```js
pwaRegister()
```

&nbsp;
