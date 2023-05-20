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

[English version](https://github.com/PwaBunga/documentation/blob/main/pwa/CSS_UI.md)

# PWA Bunga! PWA CSS Interface utilisateur

`pwabunga-ui.css` est un fichier CSS optionnel conçu pour la mise en forme des différents éléments utilisés par les fonctions du fichier `pwabunga.js`.

&nbsp;

* **`pwabunga-ui.css`**

&nbsp;

## Variables

Les variables suivantes vont permettre de configurer les couleurs, les box-shadow des éléments d'interface utilisateur de la PWA

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

## Composants d'interface utilisateur de la PWA

### Boutons

PWA Bunga! CSS UI fournit 4 boutons.

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

Le composant `pwa-banner` est utilisé par la fonction `pwaInstall()` pour afficher une bannière de promotion et de confirmation de l'installation de la PWA, et par la fonction par la fonction `pwaUpdate()` pour avertir l'utilisateur qu'une mise à jour de la PWA est disponible.

Le composant `pwa-banner` est initialement caché et s'affiche uniquement lorsqu'il est activé par l'application PWA. Lorsqu'il est visible, la bannière s'affiche en haut de la page avec un bouton de fermeture, un titre et un texte de description. Lorsque l'utilisateur clique sur le bouton de fermeture, la bannière se ferme et ne sera plus affichée.

#### Eléments html du composant PWA Banner

* `pwa-banner` : conteneur de la bannière
* `pwa-banner-close-btn` : bouton de fermeture de la bannière
* `pwa-banner-content` : conteneur du contenu de la bannière
* `pwa-banner-title` : titre de la bannière

```html
<div class="pwa-banner">
    <button class="pwa-banner-close-btn">PWA Banner close</button>
    <div class="pwa-banner-content">
        <h2>PWA Banner Title</h2>
        PWA Banner content
    <div>
</div>
```

#### Option : thème alternatif

Par défaut, le composant `pwa-banner` utilise la couleur définit par la variable CSS `--pwa-color-primary` comme couleur de fond.

Par avoir une couleur de fond correspondante à la couleur secondaire (`--pwa-color-secondary`), vous pouvez utiliser la classe `pwa-banner-secondary`

```html
<div class="pwa-banner pwa-banner-secondary">
    { ... }
</div>
```

#### Option : Option : Snackbar pour le desktop

Selon le design de votre application, il se peut que la bannière n'offre pas la meilleure expérience utilisateur en desktop. Vous pouvez donc utiliser la classe `to-pwa-snackbar` afin que la bannière apparaisse en snackbar quand l'utilisateur est sur desktop.

Afin de déterminer à quel endroit de la page afficher la snackbar, vous pouvez utiliser ces classes :

* `top-left` : affichage en haut à gauche de la page
* `top-right` : affichage en haut à droite de la page
* `bottom-left` : affichage en bas à gauche de la page
* `bottom-right` : affichage en bas à droite de la page

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

Le composant `pwa-modal` est utilisé par la fonction `pwaParams()` pour afficher les paramètres de la PWA.

Le composant `pwa-modal` est initialement caché et s'affiche uniquement lorsqu'il est activé par l'application PWA. Lorsqu'elle est visible, la modal s'affiche avec un bouton de fermeture et le contenu de la modal. Lorsque l'utilisateur clique sur le bouton de fermeture, la modal se ferme et ne sera plus affichée.

#### Eléments html du composant PWA Modal

* `pwa-modal` : conteneur de la modal
* `pwa-modal-inner` : conteneur du contenu de la modal qui sera centré horizontalement et verticalement
* `pwa-modal-title` : titres de la modal
* `pwa-modal-close` : bouton de fermeture de la modal
* `pwa-modal-close-icon` (facultatif) : icône de fermeture de la modal

```html
<div class="pwa-modal">
    <div class="pwa-modal-inner">
        <h2 class="pwa-modal-title">Title</h2>
        { Contenu de la modal }
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

Le composant pwa-switch est utilisé par les fonctions `pwaParams()`, `pwaNotifications()` et `pwaGeolocation()` pour permettre la gestion les autorisations auprès de l'utilisateur.

Il s'utilise comme un élément `checkbox` et possède donc 2 états : normal et actif avec la classe `is-active`.

#### Eléments html du composant PWA Switch

* `pwa-switch` : conteneur du switch
* `pwa-switch-slider` : slider du switch indiquant l'état du bouton

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

Le composant `pwa-alert` est utilisé par les fonction `pwaParams()`, `pwaNotifications()` et `pwaGeolocation()` pour afficher un texte d'explication pour révoquer les autorisations.

Le composant `pwa-alert` est initialement caché et s'affiche uniquement lorsqu'il est activé par l'application PWA. Lorsque elle est affichée, l'utilisateur peut cliquer sur n'importe quel endroit de la page pour fermer l'alerte.

#### Eléments html du composant PWA Alert

* `pwa-alert` : conteneur de l'alerte
* `pwa-alert-inner` : conteneur du contenu de l'alerte qui sera centré horizontalement et verticalement

```html
<div class="pwa-alert">
    <div class="pwa-alert-inner">
        { Contenu de l'alerte }
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

Le composant pwa-loader est utilisé par les fonctions `pwaInstall()` et `pwaUpdate()` pour permettre à l'utilisateur d'avoir une information visuelle lorsque l'installation de la PWA est en cours ou lorsque la mise à jour de la PWA s'exécute.

Le composant `pwa-loader` est initialement caché et s'affiche uniquement lorsqu'il est activé par l'application PWA. La couleur de fond du conteneur du svg

#### Eléments html du composant PWA Loader

* `pwa-loader` : conteneur du loader
* `svg` : svg d'un loader animé par exemple

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

## Styles additionnels

Cette partie est présente pour fournir des styles additionnels à certains éléments d'interface utilisateur des fonctions de pwabunga.js

### Barre d'actions de la PWA

Cet éléments va permettre de positionner les boutons d'actions, comme le bouton de partage ou le bouton d'accès aux paramètres de la PWA, en haut à droite de la page et va fournir des styles pour ces boutons

#### Eléments html de la barre d'actions

* `pwa-actions` : conteneur du switch
* `pwa-actions-btn` : slider du switch indiquant l'état du bouton
* `pwa-actions-icon` : slider du switch indiquant l'état du bouton

```html
<div class="pwa-actions">
    <button class="pwa-actions-btn">
        <svg class="pwa-actions-icon"></svg> 
         Partager
    </button>
    <button class="pwa-actions-btn">
        <svg class="pwa-actions-icon"></svg> 
        Paramètres
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

### Elément `version` de la fonction `pwaParams()`

Un simple espacement entre la version et les autorisations dans l'encart de paramètres utilisé par la fonction `pwaParams()`

#### Elément version

* `pwa-params-version` : conteneur da version de la PWA dans l'encart des paramètres de la PWA

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

### Listing des autorisations

Mise en forme du listing des autorisations affiché dans l'encart des paramètres utilisé par la fonction `pwaParams()`

#### Eléments du listing

* `pwa-permission-item` : conteneur du choix de l'autorisation concernée
* `pwa-permission-item-label` : libellé de l'autorisation concernée

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

## Etats des éléments utiles aux fonctions de `pwabunga.js`

Cette partie est présente pour le fonctionnement des fonctions du fichier `pwabunga.js`

### Bouton d'installation de la fonction `pwaInstall()`

Initialement, on cache le bouton d'installation de la PWA

```css
.pwa-install-btn {
    display: none;
}
```

Si les conditions de la fonction `pwaInstall()` sont réunies, la classe `is-visible` est appliquée et affiche le bouton

```css
.pwa-install-btn.is-visible {
    display: block;
}
```

### Bouton de partage de la fonction `pwaShare()`

Initialement, on cache le bouton de partage

```css
.pwa-share-btn {
    display: none;
}
```

Si les conditions de la fonction `pwaShare()` sont réunies, la classe `is-visible` est appliquée et affiche le bouton

```css
.pwa-share-btn.is-visible {
    display: block;
}
```

### Eléments de la fonction `pwaParams()`

Initialement, on cache certains éléments utiles à la fonction `pwaParams()`

```css
.pwa-params-version,
.pwa-params-permission-notification,
.pwa-params-permission-geolocation,
.pwa-params-permission,
.pwa-params-btn {
    display: none;
}
```

Si les conditions de la fonction `pwaParams()` sont réunies, la classe `is-visible` est appliquée à ces différents éléments

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