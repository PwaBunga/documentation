* [Documentation homepage](https://github.com/PwaBunga/documentation/)
* [Documentation of the PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)
* [Documentation of the PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/CSS.md)
* [Documentation of the PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/SHARE.md)

[Back to the documentation of PWA Bunga! PWA JS](https://github.com/PwaBunga/documentation/blob/main/pwa/JS.md)


# `pwaShare()`: Using native device sharing

In order to offer an immersive experience like native applications do, the PWA is displayed in `fullscreen` or `standalone`.

The problem with these 2 display modes is that we no longer have the share button offered by the device (it remains present by defining the display of the application with the `minimal-ui` value).

In order to improve the user experience and sharing of the applciation on social networks, PWA Bunga! offers the `pwaShare()` function which uses the Web Share API.

&nbsp;

## HTML

In order for the function to be functional, these elements must be added to the DOM:

* `pwa-share-btn`: share button

```html
<button class="pwa-share-btn">Share</button>
```

&nbsp;

## CSS

We hide the element

```css
.pwa-share-btn {
    display: none;
}
```

If the element has class `is-visible`, we display it

```css
.pwa-share-btn.is-visible {
    display: block;
}
```

&nbsp;

## Function

```js
const pwaShare = async(options={}) => {
     ...
}
```

### Function Options

This function takes an optional options object that allows customization of the shared title, text, and URL.

```js
pwaShare({
     title: 'My custom title',
     text: 'My custom text',
     url: 'https://www.example.com'
});
```

### DOM element selection

We set the DOM element to handle as a variable

```js
const pwaBtnShare = document.querySelector('.pwa-share-btn')
```

### Retrieving data from webmanifest file

We make a request on the webmanifest file and we store the response in a variable

```js
const webmanifestResponse = await fetch(new Request(document.querySelector('link[rel="manifest"]').href))
```

Convert the response from JSON to a JavaScript object and store it in a variable

```js
const webmanifest = await webmanifestResponse.json()
```

### Data attribution for the Share API

We define the share title with the optional parameter of the function, or with the `name` property of the Webmanifest file, or with the meta tag `title` of the document

```js
const title = options. title || webmanifest.name || document.title
```

We define the share text with the optional parameter of the function, or with the description property of the Webmanifest file, or empty

```js
const text = options.text || webmanifest.description || ''
```

The share URL with the function's optional parameter, or with the page URL

```js
onst url = options.url || location. origin + location. pathname;
```

### Showing share button

We check if the PWA works in standalone mode

```js
const isStandalone = window.matchMedia('(display-mode: standalone)').matches
```

We check if the PWA works in fullscreen mode

```js
const isFullscreen = window.matchMedia('(display-mode: fullscreen)').matches
```

We check if the PWA works in standalone mode on iOS

```js
const isStandaloneIOS = window.navigator.standalone
```

If the PWA is in sandalone or fullscreen mode, the share button is displayed

```js
if (isStandalone || isFullscreen || isStandaloneIOS) {
     pwaShareBtn.classList.add('is-visible')
}
```

### Link sharing

When you click on the share button

```js
pwaBtnShare.addEventListener('click', async () => {
```

If the browser supports the Web Share API

```js
if ('share' in browser) {
```

We define an object called data which contains the title, the text and the url of the page to share

```js
let data = { title, text, url }
```

We open the native sharing module of the device with the data to be shared

```js
await navigator.share(data)
```

If the browser does not support the Share API

```js
else {
     location.href = 'https://api.whatsapp.com/send?text=' + encodeURIComponent(text + ' - ') + url
}
```

&nbsp;

## Function call

Here is the function call used on pwabunga.js

```js
pwaShare()
```

&nbsp;

## Complete code of the `pwaShare()` function

Here is the function call used on pwabunga.js

```js
const pwaShare = async (options = {}) => {

    try {
    
        const pwaShareBtn = document.querySelector('.pwa-share-btn')
    
        const webmanifestResponse = await fetch(new Request(document.querySelector('link[rel="manifest"]').href))
        const webmanifest = await webmanifestResponse.json()
    
        const title = options.title || webmanifest.name || document.title
        const text  = options.text || webmanifest.description || ''
        const url   = options.url || location.origin + location.pathname;
    
        const isStandalone = window.matchMedia('(display-mode: standalone)').matches
        const isFullscreen = window.matchMedia('(display-mode: fullscreen)').matches
        const isStandaloneIOS = window.navigator.standalone
    
        if (isStandalone || isFullscreen || isStandaloneIOS) {
            pwaShareBtn.classList.add('is-visible')
        }
    
        pwaShareBtn.addEventListener('click', async () => {
            if ('share' in navigator) {
                let data = { title, text, url }
                try {
                    await navigator.share(data)
                } catch (error) {
                    console.error('Error sharing:', error)
                }
            } else {
                console.warn('Share API not supported')
                location.href = 'https://api.whatsapp.com/send?text=' + encodeURIComponent(text + ' - ') + url
            }
        })
    
    } catch (error) {
        console.error('Error initializing pwaShare:', error)
    }
    
}   
```

&nbsp;
