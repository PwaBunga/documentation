* [Documentation homepage](https://github.com/PwaBunga/documentation/)
* [Documentation of the PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)
* [Documentation of the PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/CSS.md)
* [Documentation of the PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/REGISTER.md)

[Back to the documentation of PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/pwa/JS.md)

# `pwaRegister()`: Service worker registration

The `pwaRegister()` function will allow the registration of the service worker, namely to create or update it.

&nbsp;

## Function Parameter

This function takes the url of the service worker as a parameter (relative or absolute)

```js
pwaRegister(file)
```

### Default value

By default the value of `file` is `serviceworker.js`

&nbsp;

## Function

We test if the browser supports service workers

```js
if ("serviceWorker" in navigator) {
    ...
}
```

We try to register the service worker

```js
try {
    const registration = await navigator.serviceWorker.register(file);
    ...
}
```

If the service worker registration is successful, its status is returned to the console

```js
if (registration. installing) {
    console.log("Service worker installing")
} else if (registration.waiting) {
    console.log("Service worker installed")
} else if (registration.active) {
    console.log("Service worker active")
}
```

Otherwise, we return the error in the console

```js
catch (error) {
     console.error(`Registration failed with ${error}`)
}
```

### Complete function

```js
const pwaRegister = async(file = 'serviceworker.js') => {
    if ("serviceWorker" in navigator) {
        try {
            const registration = await navigator.serviceWorker.register(file);
            if (registration. installing) {
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

## Function call

Here is the function call used on pwabunga.js calling the `serviceworker.js` file present at the root of the PWA

```js
pwaRegister()
```

&nbsp;
