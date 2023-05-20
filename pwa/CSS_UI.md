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

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md)

# PWA Bunga! PWA CSS UI

`pwabunga-ui.css` is an optional CSS file designed for formatting various elements used by functions in the `pwabunga.js` file.

&nbsp;

* **`pwabunga-ui.css`**

&nbsp;

## Variables

The following variables will allow to configure the colors, the box-shadow of the user interface elements of the PWA

```css
:root {
    /* Couleur principale */
    --pwa-color-primary: #5d00d8;
    --pwa-color-primary-opacity: rgba(93, 0, 216, 0.9);
    /* Couleur secondaire */
    --pwa-color-secondary: #dfcdf7;
    --pwa-color-secondary-opacity: rgba(223, 205, 247, 0.9);
    /* Couleur commune du thème */
    --pwa-color-light: #fff;
    --pwa-color-dark: #000;
    --pwa-color-gray: #ccc;
    /* Ombre */
    --pwa-box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    /* z-index des composants */
    --z-index: 1;
}
```

&nbsp;

## PWA UI Components

### Buttons

PWA Bunga! CSS UI provides 4 buttons.

#### HTML

```html
<button class="pwa-btn">Button</button>
<button class="pwa-btn pwa-btn-primary">Primary Button</button>
<button class="pwa-btn pwa-btn-secondary">Secondary Button</button>
<button class="pwa-btn pwa-btn-dark">Dark Button</button>
```

#### CSS

```css
/* ----------------------------------------------------------------------------
 ## PWA UI Button
---------------------------------------------------------------------------- */

.pwa-btn {
    background: var(--pwa-color-light);
    border: none;
    border-radius: 20px;
    color: var(--pwa-color-primary);
    display: inline-block;
    padding: 8px 20px;
    text-decoration: none;
    font-weight: bold;
    margin-bottom: 15px;
}

.pwa-btn:active, 
.pwa-btn:hover {
    background: var(--pwa-color-secondary);
    color: var(--pwa-color-primary);
}

/* 
 # PWA UI Button primary
------------------------ */

.pwa-btn.pwa-btn-primary {
    background: var(--pwa-color-primary);
    color: var(--pwa-color-light);
}

.pwa-btn.pwa-btn-primary:active, 
.pwa-btn.pwa-btn-primary:hover {
    background: var(--pwa-color-secondary);
    color: var(--pwa-color-primary);
}

/* 
 # PWA UI Button secondary
-------------------------- */

.pwa-btn.pwa-btn-secondary {
    background: var(--pwa-color-secondary);
    color: var(--pwa-color-primary);
}

.pwa-btn.pwa-btn-secondary:active, 
.pwa-btn.pwa-btn-secondary:hover {
    background: var(--pwa-color-primary);
    color: var(--pwa-color-light);
}

/* 
 # PWA UI Button dark
--------------------- */

.pwa-btn.pwa-btn-dark {
    background: var(--pwa-color-dark);
    color: var(--pwa-color-light);
}

.pwa-btn.pwa-btn-dark:active, 
.pwa-btn.pwa-btn-dark:hover {
    background: var(--pwa-color-primary);
    color: var(--pwa-color-light);
}
```

### PWA Banner

The `pwa-banner` component is used by the `pwaInstall()` function to display a banner promoting and confirming the installation of the PWA, and by the `pwaUpdate()` function to notify the user that a PWA update is available.

The `pwa-banner` component is initially hidden and only shows when activated by the PWA application. When visible, the banner appears at the top of the page with a close button, title, and description text. When the user clicks the close button, the banner closes and will no longer be displayed.

#### PWA Banner component html elements

* `pwa-banner`: banner container
* `pwa-banner-close-btn`: close banner button
* `pwa-banner-content`: banner content container
* `pwa-banner-title`: banner title

```html
<div class="pwa-banner">
     <button class="pwa-banner-close-btn">PWA Banner close</button>
     <div class="pwa-banner-content">
         <h2>PWA Banner Title</h2>
         PWA Banner content
     <div>
</div>
```

#### Option: alternative theme

By default, the `pwa-banner` component uses the color defined by the CSS variable `--pwa-color-primary` as the background color.

By having a background color corresponding to the secondary color (`--pwa-color-secondary`), you can use the class `pwa-banner-secondary`

```html
<div class="pwa-banner pwa-banner-secondary">
     { ... }
</div>
```

#### Option: Option: Desktop Snackbar

Depending on the design of your application, the banner may not provide the best desktop user experience. So you can use the `to-pwa-snackbar` class so that the banner appears in the snackbar when the user is on desktop.

In order to determine where on the page to display the snackbar, you can use these classes:

* `top-left`: display at the top left of the page
* `top-right`: display at the top right of the page
* `bottom-left`: display at the bottom left of the page
* `bottom-right`: display at the bottom right of the page

```html
&lt;div class="pwa-banner to-pwa-snackbar top-left"&gt;
    { ... }
&lt;/div&gt;

&lt;div class="pwa-banner to-pwa-snackbar top-right"&gt;
    { ... }
&lt;/div&gt;

&lt;div class="pwa-banner to-pwa-snackbar bottom-left"&gt;
    { ... }
&lt;/div&gt;

&lt;div class="pwa-banner to-pwa-snackbar bottom-right"&gt;
    { ... }
&lt;/div&gt;
```

#### CSS

```css
/* ----------------------------------------------------------------------------
 ## PWA UI Banner
---------------------------------------------------------------------------- */

.pwa-banner {
    align-items: center;
    background: var(--pwa-color-primary);
    color: var(--pwa-color-light);
    display: flex;
    justify-content: space-between;
    left: 0;
    opacity: 0;
    padding: 10px;
    position: fixed;
    right: 0;
    top: 0;
    transform: translate(0, -100%);
    transition: all 0.2s ease-in-out;
    width: 100%;
    z-index: var(--z-index);
}

/* 
 # PWA UI Banner secondary theme
-------------------------------- */

.pwa-banner.pwa-banner-secondary {
    background: var(--pwa-color-secondary);
    color: var(--pwa-color-dark);
}

/* 
 # PWA UI Banner close button
----------------------------- */

.pwa-banner-close-btn {
    cursor: pointer;
    min-width: 32px;
}

/* 
 # PWA UI Banner content
------------------------ */

.pwa-banner-content {
    flex-grow: 1;
    padding: 0 10px;
}

/* 
 # PWA UI Banner title
---------------------- */

.pwa-banner-title {
    display: block;
    font-weight: bold;
}

/* 
 # PWA UI Banner is-visible state
--------------------------------- */

.pwa-banner.is-visible {
    opacity: 1;
    transform: translate(0, 0);
}

/* ----------------------------------------------------------------------------
 ## PWA UI Banner to Snackbar (desktop)
---------------------------------------------------------------------------- */

@media only screen and (min-width : 1024px) {

    .pwa-banner.to-pwa-snackbar {
        border-radius: 10px;
        bottom: 20px;
        height: 100px;
        left: 20px;
        max-width: 400px;
        padding: 0 20px;
        right: auto;
        top: auto;
        transform: translate(calc(-100% - 20px), 0);
    }

    /* 
    # PWA UI Snackbar top left
    --------------------------- */

    .pwa-banner.to-pwa-snackbar.top-left {
        bottom: auto;
        left: 20px;
        right: auto;
        top: 20px;
    }

    /* 
    # PWA UI Snackbar top right
    ---------------------------- */

    .pwa-banner.to-pwa-snackbar.top-right {
        bottom: auto;
        left: auto;
        right: 20px;
        top: 20px;
        transform: translate(0, calc(-100% - 20px));
    }

    /* 
    # PWA UI Snackbar bottom left
    ------------------------------ */

    .pwa-banner.to-pwa-snackbar.bottom-left {
        bottom: 20px;
        left: 20px;
        right: auto;
        top: auto;
    }

    /* 
    # PWA UI Snackbar bottom right
    ------------------------------- */

    .pwa-banner.to-pwa-snackbar.bottom-right {
        bottom: 20px;
        left: auto;
        right: 20px;
        top: auto;
        transform: translate(0, calc(100% + 20px));
    }

}

/* 
 # PWA UI Banner to Snackbar is-visible state
--------------------------------------------- */

.pwa-banner.to-pwa-snackbar.is-visible {
    opacity: 1;
    transform: translate(0, 0);
}
```

### PWA Modal

The `pwa-modal` component is used by the `pwaParams()` function to display the parameters of the PWA.

The `pwa-modal` component is initially hidden and only shows when activated by the PWA application. When visible, the modal is displayed with a close button and the contents of the modal. When the user clicks the close button, the modal will close and will no longer be displayed.

#### PWA Modal component html elements

* `pwa-modal`: modal container
* `pwa-modal-inner`: container of the modal content which will be centered horizontally and vertically
* `pwa-modal-title`: modal titles
* `pwa-modal-close`: button to close the modal
* `pwa-modal-close-icon` (optional): close modal icon

```html
<div class="pwa-modal">
     <div class="pwa-modal-inner">
         <h2 class="pwa-modal-title">Title</h2>
         { Content of the modal }
         <button class="pwa-modal-close">
             <svg class="pwa-modal-close-icon"></svg>
         </button>
     </div>
</div>
```

#### CSS

```css
/* ----------------------------------------------------------------------------
## PWA UI Modal
---------------------------------------------------------------------------- */

.pwa-modal {
    align-items: center;
    background: var(--pwa-color-light);
    bottom: 0;
    display: flex;
    flex-direction: column;
    height: 100%;
    justify-content: center;
    left: 0;
    overflow-y: auto;
    position: fixed;
    right: 0;
    text-align: left;
    top: 0;
    transform: translateY(-100%);
    transition: transform 0.25s ease-in-out;
    width: 100%;
    z-index: var(--z-index);
}

/* 
# PWA UI Modal inner
--------------------- */

.pwa-modal-inner {
    padding: 0 20px;
}

/* 
# PWA UI Modal title
--------------------- */

.pwa-modal-title {
    font-size: 2rem;
    font-weight: bold;
    margin-bottom: 25px;
    margin-top: 0;
}

/* 
# PWA UI Modal close button
---------------------------- */

.pwa-modal-close {
    background: none;
    border: none;
    padding: 0;
    position: absolute;
    right: 10px;
    top: 10px;
}

/* 
# PWA UI Modal close btn icon
------------------------------ */

.pwa-modal-close-icon {
    fill: var(--pwa-color-primary);
    width: 40px;
}

/* 
# PWA UI Modal is-visible state
-------------------------------- */

.pwa-modal.is-visible {
    transform: translateY(0);
}
```

### PWA Switch

The pwa-switch component is used by the `pwaParams()`, `pwaNotifications()` and `pwaGeolocation()` functions to allow the management of permissions to the user.

It is used as a `checkbox` element and therefore has 2 states: normal and active with the class `is-active`.

#### PWA Switch component html elements

* `pwa-switch`: switch container
* `pwa-switch-slider`: switch slider indicating the state of the button

```html
<button class="pwa-switch">
    <span class="pwa-switch-slider"></span>
</button>
```

#### Etat actif

```html
<button class="pwa-switch is-active">
    <span class="pwa-switch-slider"></span>
</button>
```

#### CSS

```css
/* ----------------------------------------------------------------------------
## PWA UI Switch
---------------------------------------------------------------------------- */

.pwa-switch {
    background: none;
    border: none;
    display: inline-block;
    height: 34px;
    position: relative;
    width: 60px;
}

/* 
# PWA UI Switch slider
----------------------- */

.pwa-switch-slider {
    background-color: var(--pwa-color-gray);
    border-radius: 34px;
    bottom: 0;
    cursor: pointer;
    height: 34px;
    left: 0;
    position: absolute;
    right: 0;
    top: 0;
    transition: .4s;
    width: 60px;
}

.pwa-switch-slider::before {
    background-color: var(--pwa-color-light);
    border-radius: 50%;
    bottom: 4px;
    content: "";
    height: 26px;
    left: 4px;
    position: absolute;
    transition: .4s;
    width: 26px;
}
```

### PWA Alert

The `pwa-alert` component is used by the `pwaParams()`, `pwaNotifications()` and `pwaGeolocation()` functions to display explanatory text for revoking permissions.

The `pwa-alert` component is initially hidden and only shows when activated by the PWA application. When displayed, the user can click anywhere on the page to dismiss the alert.

#### PWA Alert component html elements

* `pwa-alert`: alert container
* `pwa-alert-inner`: container of the content of the alert which will be centered horizontally and vertically

```html
<div class="pwa-alert">
     <div class="pwa-alert-inner">
         { Content of the alert }
     </div>
</div>
```

#### CSS

```css
/* ----------------------------------------------------------------------------
## PWA UI Alert
---------------------------------------------------------------------------- */

.alert {
    align-items: center;
    background-color: var(--pwa-color-secondary-opacity);
    bottom: 0;
    display: flex;
    flex-direction: column;
    height: 100%;
    justify-content: center;
    left: 0;
    overflow-y: auto;
    position: fixed;
    right: 0;
    text-align: left;
    top: 0;
    transform: translateY(-100%);
    transition: transform 0.25s ease-in-out;
    width: 100%;
    z-index: var(--z-index);
}

/* 
# PWA UI Alert inner
--------------------- */

.alert-inner {
    background: #fff;
    border-radius: 20px;
    box-shadow: var(--pwa-box-shadow);
    max-width: 320px;
    padding: 20px;
    text-align: center;
}

/* 
# PWA UI Alert is-visible state
-------------------------------- */

.alert.is-visible {
    transform: translateY(0);
}
```

### PWA Loader

The pwa-loader component is used by the `pwaInstall()` and `pwaUpdate()` functions to allow the user to have visual information when the installation of the PWA is in progress or when the update of the PWA runs.

The `pwa-loader` component is initially hidden and shows only when activated by the PWA application. The background color of the svg container

#### PWA Loader component html elements

* `pwa-loader`: loader container
* `svg`: svg of an animated loader for example

```html
<div class="pwa-loader">
    <!-- SVG loader -->
    <svg></svg>
</div>
```

#### CSS

```css
/* ----------------------------------------------------------------------------
 ## PWA UI Loader
---------------------------------------------------------------------------- */

.pwa-loader {
    align-items: center;
    background-color: var(--pwa-color-primary-opacity);
    display: none;
    justify-content: center;
    padding: 20px;
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    top: 0;
    z-index: var(--z-index);
}

/* 
 # PWA UI Loader is-visible state
--------------------------------- */

.pwa-loader.is-visible {
    display: flex;
}
```

&nbsp;

## Additional Styles

This part is there to provide additional styling to some UI elements of pwabunga.js functions

### PWA Actionbar

This element will allow you to position the action buttons, such as the share button or the button to access the PWA settings, at the top right of the page and will provide styles for these buttons

#### Actionbar html elements

* `pwa-actions`: switch container
* `pwa-actions-btn`: switch slider indicating the state of the button
* `pwa-actions-icon`: switch slider indicating the state of the button

```html
<div class="pwa-actions">
     <button class="pwa-actions-btn">
         <svg class="pwa-actions-icon"></svg>
          Share
     </button>
     <button class="pwa-actions-btn">
         <svg class="pwa-actions-icon"></svg>
         Settings
     </button>
     { ... }
</div>
```

#### CSS

```css
/* ----------------------------------------------------------------------------
## PWA UI Actions bar
---------------------------------------------------------------------------- */

.pwa-actions {
    background: var(--pwa-color-light);
    display: flex;
    padding: 10px 0 0 20px;
    position: fixed;
    right: 0;
    top: 0;
    z-index: var(--z-index);
}

/* 
# PWA UI Actions bar button
---------------------------- */

.pwa-actions-btn {
    background: none;
    border: none;
    font-size: 1.2rem;
    margin-right: 20px;
}

/* 
# PWA UI Actions bar button icon
--------------------------------- */

.pwa-actions-icon {
    display: flex;
    fill: var(--pwa-color-primary);
    flex-direction: column;
    margin: 0 auto;
    width: 32px;
}
```

### The `version` element of the `pwaParams()` function

Simple spacing between version and permissions in the parameters inset used by the `pwaParams()` function

#### Version element

* `pwa-params-version`: PWA version container in the PWA settings box

```html
<div class="pwa-params-version">
    { ... }
</div>
```

#### CSS

```css
/* ----------------------------------------------------------------------------
## PWA UI Params Version (@for pwaParams() function)
---------------------------------------------------------------------------- */

.pwa-params-version {
    margin-bottom: 50px;
}
```

### List of permissions

Formatting of the permissions listing displayed in the parameters inset used by the `pwaParams()` function

#### Listing items

* `pwa-permission-item`: container of the choice of the authorization concerned
* `pwa-permission-item-label`: label of the concerned authorization

```html
<li class="pwa-permission-item">
    <button>{ ... }</button>
    <span class="pwa-permission-item-label"> { ... }</span>
</li>
```

#### CSS

```css
/* ----------------------------------------------------------------------------
## PWA UI Params Permissions (@for pwaParams() function)
---------------------------------------------------------------------------- */

.pwa-permission-item {
    align-items: center; 
    display: flex;
    margin-bottom: 20px;
}

.pwa-permission-item-label {
    display: block;
    margin-left: 10px;
}
```

&nbsp;

## States of elements useful to the functions of `pwabunga.js`

This part is present for the operation of the functions of the file `pwabunga.js`

### Install button for `pwaInstall()` function

Initially, we hide the install button of the PWA

```css
.pwa-install-btn {
    display: none;
}
```

If the conditions of the `pwaInstall()` function are met, the `is-visible` class is applied and displays the button

```css
.pwa-install-btn.is-visible {
    display: block;
}
```

### Share button of `pwaShare()` function

Initially, we hide the share button

```css
.pwa-share-btn {
    display: none;
}
```

If the conditions of the `pwaShare()` function are met, the `is-visible` class is applied and displays the button

```css
.pwa-share-btn.is-visible {
    display: block;
}
```

### Elements of the `pwaParams()` function

Initially, we hide some elements useful to the `pwaParams()` function

```css
.pwa-params-version,
.pwa-params-permission-notification,
.pwa-params-permission-geolocation,
.pwa-params-permission,
.pwa-params-btn {
    display: none;
}
```

If the conditions of the `pwaParams()` function are met, the `is-visible` class is applied to these different elements

```css
.pwa-params-version.is-visible,
.pwa-params-permission.is-visible,
.pwa-params-btn.is-visible {
    display: block;
}

.pwa-params-permission-notification.is-visible,
.pwa-params-permission-geolocation.is-visible {
    display: flex;
}
```