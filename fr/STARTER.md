* [Accueil de la documentation](https://github.com/PwaBunga/documentation/blob/main/fr/)
* [Documentation du module PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md)
* [Documentation du module PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md)
* [Documentation du module PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/fr/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-starter-circle.png" alt="logo PWA Bunga! Starter"/>
</div>

[English version](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)

# PWA Bunga! Starter

Le module Starter de PWA Bunga! est conçu pour vous aider à démarrer rapidement avec un ensemble de dossiers et fichiers de base qui peuvent être personnalisés pour répondre aux besoins spécifiques de votre site ou application web.

&nbsp;

## Contenu de PWA Bunga! Starter

Le module PWA Bunga! Starter comprend :

* des dossiers de ressources
* des fichiers CSS et JS vides qui peuvent être remplis en fonction de vos besoins
* un template HTML
* des favicons aux formats .ico, .svg ou .png
* les pages d'erreur 404 et 403
* un fichier htaccess

&nbsp;

## Sommaire de la documentation de PWA Bunga! Starter

* [Dossiers de ressources](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#dossiers-de-ressources)
* [Fichiers vierges](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#fichiers-vierges)
* [Pages d'erreurs](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#)
  - [Erreur 403](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#erreur-403)
  - [Erreur 404](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#erreur-404)
* [Favicons](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#favicons)
  - [Fichier ICO](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#fichier-ico)
  - [Fichier SVG](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#fichier-scg)
  - [Vous n'avez pas de logo au format SVG ?](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#vous-navez-pas-de-logo-au-format-svg-)
* [Template HTML](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#template-html)
  - [Balise html](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#balise-html)
  - [Balise meta charset](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#balise-meta-charset)
  - [Balise title](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#balise-title)
  - [Balise meta description](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#balise-meta-description)
  - [Balise meta viewport](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#balise-meta-viewport)
  - [Open Graph](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#open-graph)
  - [Favicons](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#favicons-1)
  - [Touch-icon pour iOS](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#touch-icon-pour-ios)
  - [Progressive Web App](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#progressive-web-app)
  - [Gestion des thèmes en mode light ou dark](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#gestion-des-thèmes-en-mode-light-ou-dark)
  - [Appel des fichiers CSS](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#appel-des-fichiers-css)
  - [PWA Interface utilisateur](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#pwa-interface-utilisateur)
  - [Appel des fichiers Javascript](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#appel-des-fichiers-javascript)
* [Fichier .htaccess](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#fichier-htaccess)
  - [Performances](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#performances)
  - [Sécurité](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#sécurité)
  - [Redirections](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#redirections)

&nbsp;

## Dossiers de ressources

Le dossier `assets` se compose des dossiers de base pour organiser les fichiers de votre site ou application Web.

* **`assets`** : contient les ressources communes du projet.
  - **`css`** : contient les feuilles de styles du projet.
  - **`fonts`** : contient les fonts du projet.
  - **`images`** : contient les images du projet.
  - **`js`** : contient les fichiers javascript du projet.
    - **`vendor`** : contient les bibliothèques js tierces.

&nbsp;

## Fichiers vierges

PWA Bunga! contient une feuille de styles et un fichier javascript vierges et prêts-à-l'emploi. Ces 2 fichiers sont appelés depuis le template html.

* assets
  - css
    - **`styles.css`**
  - js
    - **`scripts.js`**

&nbsp;

## Pages d'erreurs

PWA Bunga! fournit 2 pages d'erreurs

### Erreur 403

* **`403.html`**

Cette erreur indique que le serveur comprend la requête mais refuse de l'autoriser. On peut par exemple interdire l'accès aux dossiers du site qui ne contiennent pas de fichier index.html à leur racine et rediriger vers la page d'erreur 403 indiquant que l'accès est interdit.

### Erreur 404

* **`404.html`**

Cette erreur indique que la requête pour consulter une page web est erronée d'une manière ou d'une autre. C'est par exemple le cas lorsque la page est inexistante.

*La redirection des erreurs vers ces pages se fait au niveau du fichier de configuration serveur (Voir le [fichier .htaccess](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#fichier-htaccess)).*

&nbsp;

## Favicons

Actuellement, pour avoir un favicon fonctionnant sur tous les navigateurs, il faut appeler 2 fichiers :

### Fichier ICO

* **`favicon.ico`**

Ce fichier va être utilisé par les anciens navigateurs pour afficher le favicon et par Google pour afficher l'icône sur le résultat de la recherche. Ce format permet d'encapsuler plusieurs dimensions, et nous allons avoir besoin d'un .ico contenant les 3 dimensions suivantes : 16px x 16px et 32px x 32px pour les navigateurs, et 48px x 48px pour le résultat de la recherche Google ([Source](https://developers.google.com/search/docs/appearance/favicon-in-search?hl=fr)).

### Fichier SVG

* **`favicon.svg`**

Ce fichier va être utilisé par tous les navigateurs modernes. Il est idéal car léger, sans perte de qualité et permet des fonctionnalités intéressantes comme un affichage différent si l'utilisateur à définit le "Mode Sombre" sur son environnement.

### Vous n'avez pas de logo au format SVG ?

* **`favicon-16.png`**
* **`favicon-32.png`**

Vous pouvez utiliser à la place 2 fichiers png aux formats 16px x 16px et 32px x 32px. Ils seront utilisés par tous les navigateurs modernes et moins modernes.

Vous devrez alors modifier le template html en remplaçant cette partie :

```html
<link rel="icon" type="image/svg+xml" href="favicon.svg">
```

par :

```html
<link rel="icon" type="image/png" sizes="32x32" href="favicon-32.png">
<link rel="icon" type="image/png" sizes="16x16" href="favicon-16.png">
```

*Les icônes et touch-icons se trouvent et sont détaillés dans la partie [PWA Bunga! PWA Icônes](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md).*

&nbsp;

## Template HTML

index.html est un template HTML qui contient tout le nécessaire pour démarrer un projet de site ou d'application web.

* **`index.html`**

```html
<!doctype html>
```

### Balise `html`

#### Lang

Mettez ici la langue de votre site ou application web.

#### prefix

L'attribut `prefix` présent sur la balise html est le préfixe requis pour les balises meta du protocole Open Graph. Vous pouvez l'enlever si vous ne vous servez pas de ce dernier.

```html
<html lang="" prefix="og: http://ogp.me/ns#">
```

### Balise `meta` `charset`

Cette déclaration indique au navigateur d’utiliser le jeu de caractère universel Unicode.

```html
<meta charset="utf-8">
```

### Balise `title`

Cette balise permet de donner un titre à la page web, elle apparait sur l'onglet du navigateur et dans les résultats de recherches. C'est un des éléments fondamentaux du référencement naturel.

```html
<title></title>
```

### Balise `meta` `description`

Cette balise permet de décrire le contenu de la page web. Le contenu se retrouve sous le titre et l'URL de la page dans les résultats des moteurs de recherche.

```html
<meta name="description" content="">
```

### Balise `meta` `viewport`

Cette déclaration permet d'optimiser le viewport pour le mobile.

#### width=device-width

Indique au navigateur d'utiliser la largeur disponible de l'appareil.

#### initial-scale=1

Définit le niveau de zoom initial à 1 pixel de la fenêtre d'affichage est égal à 1 pixel CSS.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### Open Graph

l’Open Graph Protocol (OGP) permet d’ajouter des meta données sur les pages d’un site web. Il autorise les pages web à se comporter comme des objets de réseaux sociaux, et permet d'afficher le bon titre, la bonne description et la bonne image lors d'un partage.

#### og:type

Indique au réseau social la nature du contenu principal de la page (exemple : article, vidéo, musique...)

#### og:title

Détermine le titre de la page pour l’Open Graph (au-delà de 65 caractères environ, le titre sera tronqué).

#### og:description

Indique un court descriptif du contenu de la page (La recommandation actuelle est de ne pas dépasser les 300 caractères pour avoir un affichage optimal). Cette déclaration est facultative.

#### og:url

Indique l'URL canonique de la page.

#### og:image

Indique l’image à afficher lors du partage de la page sur les réseaux sociaux.

```html
<meta property="og:type" content="">
<meta property="og:title" content="">
<meta property="og:description" content="">
<meta property="og:url" content="">
<meta property="og:image" content="">
```

### Favicons

Appel des favicons. Si vous avez votre favicon au format SVG :

```html
<link rel="icon" href="favicon.ico" sizes="any">
<link rel="icon" href="favicon.svg" type="image/svg+xml">
```

Sinon, utilisez le format PNG :

```html
<link rel="icon" href="favicon.ico" sizes="any">
<link rel="icon" type="image/png" sizes="32x32" href="favicon-32.png">
<link rel="icon" type="image/png" sizes="16x16" href="favicon-16.png">
```

### Touch-icon pour iOS

Appel de l'icône pour l'environnement iOS.

```html
<link rel="apple-touch-icon" href="pwa/apple-touch-icon.png">
```

### Progressive Web App

Appel du fichier webmanifest qui va permettre de rendre vote projet web installable et définir certains paramètres. Ce fichier est détaillé dans la partie [PWA Bunga! PWA Webmanifest](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md).

```html
<link rel="manifest" href="pwa/app.webmanifest">
```

### Gestion des thèmes en mode light ou dark

Ces déclarations vont permettre au navigateur de proposer un thème de couleur sur votre site selon le thème choisi (dark ou light) par l'utilisateur.

```html
<meta name="theme-color" content="#fafafa" media="(prefers-color-scheme: light)">
<meta name="theme-color" content="#afafaf" media="(prefers-color-scheme: dark)">
```

### Appel des fichiers CSS

Appel du fichier CSS de base pwabunga.css (ce fichier est détaillé dans la partie [PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md)) et du fichier styles.css.

```html
<link rel="stylesheet" href="assets/css/pwabunga.css">
<link rel="stylesheet" href="assets/css/styles.css">
<link rel="stylesheet" href="pwa/css/pwabunga-ui.css">
```

### PWA Interface utilisateur

Ces éléments HTML sont les éléments d’interface utilisateur proposés par PWA Bunga! pour améliorer l’expérience utilisateur. 
Ils fonctionnent avec les fonctions présentent dans le fichier [`pwabunga.js`](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md) et utilisent les composants de [`pwabunga-ui.css`](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md) pour la mise en forme.

#### Bannière de promotion et bouton d'installation

Utilisé par la fonction `pwaInstall()`, ce code permet d’afficher une bannière faisant la promotion de l’installation de la PWA avec un bouton d’installation.

Il utilise les composants `pwa-banner` et `pwa-btn`, mis en forme dans le fichier `pwabunga-ui.css`.

```html
<div class="pwa-install-promotion pwa-banner to-pwa-snackbar">
  <svg class="pwa-banner-close-btn pwa-install-promotion-close" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="32">
    <title>close</title>
    <path d="M19,6.41L17.59,  5L12,10.59L6.41,5L5,6.41L10.59,12L5,17.59L6.41,19L12,13.41L17.59,19L19,17.59L13.41,12L19,6.41Z" />
  </svg>
  <p class="pwa-banner-content">
  <strong class="pwa-banner-title">Your PWA</strong>
    Get our free app. It won't take up space on your phone.
  </p>
  <button class="pwa-install-btn pwa-btn">Install</button>
</div>
```

#### Bannière de confirmation de l'installation

Utilisé par la fonction `pwaInstall()`, ce code permet d’afficher une bannière de confirmation apparaissant lorsque l'installation de la PWA ets effectuée.

Il utilise le composant `pwa-banner`, mis en forme dans le fichier `pwabunga-ui.css`.

```html
<div class="pwa-install-confirm pwa-banner pwa-banner-secondary to-pwa-snackbar">
  <p class="pwa-banner-text">
    <strong class="pwa-banner-content">The app has been successfully installed!</strong>
    The icon will appear shortly on your home screen
  </p>
  <svg class="pwa-banner-close-btn pwa-install-confirm-close" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="32">
    <title>close</title>
    <path d="M19,6.41L17.59,5L12,10.59L6.41,5L5,6.41L10.59,12L5,17.59L6.41,19L12,13.41L17.59,19L19,17.59L13.41,12L19,6.41Z" />
  </svg>
</div>
```

#### Bannière de mise à jour

Utilisé par la fonction `pwaUpdate()`, ce code permet d’afficher une bannière indiquant qu'une mise à jour de l'application est disponible avec un bouton pour l'effectuer.

Il utilise les composants `pwa-banner` et `pwa-btn`, mis en forme dans le fichier `pwabunga-ui.css`.

```html
<div class="pwa-update pwa-banner to-pwa-snackbar">
  <svg class="pwa-update-close pwa-install-confirm-close" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="32">
    <title>close</title>
    <path d="M19,6.41L17.59,5L12,10.59L6.41,5L5,6.41L10.59,12L5,17.59L6.41,19L12,13.41L17.59,19L19,17.59L13.41,12L19,6.41Z" />
  </svg>
  <p class="pwa-banner-text">
    <strong class="pwa-banner-title">New version available!</strong>
  </p>
  <button class="pwa-update-btn pwa-btn">Update</button>
</div>
```

#### Barre des boutons d'actions

Utilisé par les fonctions `pwaShare()` et `pwaParams()`, ce code permet d’afficher les boutons d'actions de la PWA, à savoir le bouton de partage et le bouton d'accès aux paramètres de l'application.

Il utilise les composants `pwa-actions` et `pwa-btn`, mis en forme dans le fichier `pwabunga-ui.css`.

```html
<div class="pwa-actions">
  <button class="pwa-share-btn pwa-actions-btn">
    <!-- SVG Source : https://pictogrammers.com/library/mdi/icon/share-variant/ -->
    <svg class="pwa-actions-icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
      <title>share-variant</title>
      <path d="M18,16.08C17.24,16.08 16.56,16.38 16.04,16.85L8.91,12.7C8.96,12.47 9,12.24 9,12C9,11.76 8.96,11.53 8.91,11.3L15.96,7.19C16.5,7.69 17.21,8 18,8A3,3 0 0,0 21,5A3,3 0 0,0 18,2A3,3 0 0,0 15,5C15,5.24 15.04,5.47 15.09,5.7L8.04,9.81C7.5,9.31 6.79,9 6,9A3,3 0 0,0 3,12A3,3 0 0,0 6,15C6.79,15 7.5,14.69 8.04,14.19L15.16,18.34C15.11,18.55 15.08,18.77 15.08,19C15.08,20.61 16.39,21.91 18,21.91C19.61,21.91 20.92,20.61 20.92,19A2.92,2.92 0 0,0 18,16.08Z" />
    </svg>
    Share
  </button>
  <button class="pwa-params-btn pwa-actions-btn">
    <!-- SVG Source : https://pictogrammers.com/library/mdi/icon/cog/ -->
    <svg class="pwa-actions-icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
      <title>cog</title>
      <path d="M12,15.5A3.5,3.5 0 0,1 8.5,12A3.5,3.5 0 0,1 12,8.5A3.5,3.5 0 0,1 15.5,12A3.5,3.5 0 0,1 12,15.5M19.43,12.97C19.47,12.65 19.5,12.33 19.5,12C19.5,11.67 19.47,11.34 19.43,11L21.54,9.37C21.73,9.22 21.78,8.95 21.66,8.73L19.66,5.27C19.54,5.05 19.27,4.96 19.05,5.05L16.56,6.05C16.04,5.66 15.5,5.32 14.87,5.07L14.5,2.42C14.46,2.18 14.25,2 14,2H10C9.75,2 9.54,2.18 9.5,2.42L9.13,5.07C8.5,5.32 7.96,5.66 7.44,6.05L4.95,5.05C4.73,4.96 4.46,5.05 4.34,5.27L2.34,8.73C2.21,8.95 2.27,9.22 2.46,9.37L4.57,11C4.53,11.34 4.5,11.67 4.5,12C4.5,12.33 4.53,12.65 4.57,12.97L2.46,14.63C2.27,14.78 2.21,15.05 2.34,15.27L4.34,18.73C4.46,18.95 4.73,19.03 4.95,18.95L7.44,17.94C7.96,18.34 8.5,18.68 9.13,18.93L9.5,21.58C9.54,21.82 9.75,22 10,22H14C14.25,22 14.46,21.82 14.5,21.58L14.87,18.93C15.5,18.67 16.04,18.34 16.56,17.94L19.05,18.95C19.27,19.03 19.54,18.95 19.66,18.73L21.66,15.27C21.78,15.05 21.73,14.78 21.54,14.63L19.43,12.97Z" />
    </svg>
    Params
  </button>
</div>
```

#### Encart des paramètres de la PWA

Utilisé par la fonction `pwaParams()`, ce code permet d’afficher l'encart des paramètres contenant la version de la PWA et les autorisations.

Il utilise les composants `pwa-modal`, `pwa-switch`, `pwa-alert` et `pwa-permission-item`, mis en forme dans le fichier `pwabunga-ui.css`.

```html
<div class="pwa-params pwa-modal">
  <div class="pwa-modal-inner">
    <div class="pwa-params-version">
      <p class="pwa-modal-title">Version</p>
      <p>
        <span class="pwa-name"></span> 
        <span class="pwa-version"></span>
      </p>
    </div>
    <div class="pwa-params-permission">
      <p class="pwa-modal-title">Permissions</p>
      <ul>
        <li class="pwa-params-permission-notification pwa-permission-item">
          <button class="pwa-permission-notifications-btn pwa-switch">
            <span class="pwa-switch-slider"></span>
          </button>
          <span class="pwa-permission-item-label">I authorize to receive notifications</span>
        </li>
        <li class="pwa-params-permission-geolocation pwa-permission-item">
          <button class="pwa-permission-geolocation-btn pwa-switch">
            <span class="pwa-switch-slider"></span>
          </button>
          <span class="pwa-permission-item-label">I authorize geolocation</span>
        </li>
      </ul>

      <div class="pwa-permission-remove pwa-alert">
        <p class="pwa-alert-inner">To remove permission, please go to your device or browser settings</p>
      </div>
    </div>
    <button class="pwa-params-close-btn pwa-modal-close">
      <!-- SVG Source : https://pictogrammers.com/library/mdi/icon/close/ -->
      <svg class="pwa-modal-close-icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
        <title>close-box</title>
        <path d="M19,3H16.3H7.7H5A2,2 0 0,0 3,5V7.7V16.4V19A2,2 0 0,0 5,21H7.7H16.4H19A2,2 0 0,0 21,19V16.3V7.7V5A2,2 0 0,0 19,3M15.6,17L12,13.4L8.4,17L7,15.6L10.6,12L7,8.4L8.4,7L12,10.6L15.6,7L17,8.4L13.4,12L17,15.6L15.6,17Z" />
      </svg>
    </button>
  </div>
</div>	
```

#### Loader de la PWA

Utilisé par les fonctions `pwaInstall()` et `pwaUpdate()`, ce code permet d’afficher un loader lorsque la PWA s'installe ou se met à jour.

Il utilise le composant `pwa-loader`, mis en forme dans le fichier `pwabunga-ui.css`.

```html
<div class="pwa-loader">
  <!-- By Sam Herbert (@sherb). More @ http://goo.gl/7AJzbL -->
  <svg width="38" height="38" viewBox="0 0 38 38" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <linearGradient x1="8.042%" y1="0%" x2="65.682%" y2="23.865%" id="a">
        <stop stop-color="white" stop-opacity="0" offset="0%"/>
        <stop stop-color="white" stop-opacity=".631" offset="63.146%"/>
        <stop stop-color="white" offset="100%"/>
      </linearGradient>
    </defs>
    <g fill="none" fill-rule="evenodd">
      <g transform="translate(1 1)">
        <path d="M36 18c0-9.94-8.06-18-18-18" id="Oval-2" stroke="url(#a)" stroke-width="2">
          <animateTransform
            attributeName="transform"
            type="rotate"
            from="0 18 18"
            to="360 18 18"
            dur="0.9s"
            repeatCount="indefinite" />
        </path>
        <circle fill="#fff" cx="36" cy="18" r="1">
          <animateTransform
            attributeName="transform"
            type="rotate"
            from="0 18 18"
            to="360 18 18"
            dur="0.9s"
            repeatCount="indefinite" />
        </circle>
      </g>
    </g>
  </svg>
</div>	
```

### Appel des fichiers Javascript

Appel du fichier JS de base pwabunga.js (ce fichier est détaillé dans la partie [PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md)) et du fichier scripts.js.

```html
<script src="pwa/js/pwabunga.js"></script>
<script src="assets/js/scripts.js"></script>
```

&nbsp;

## Fichier .htaccess

Le fichier de configuration htaccess est utilisé par le serveur web Apache, utilisé par la plupart des hébergeurs.

* **`.htaccess`**

### Performances

#### Cache navigateur

On donne des directives pour contrôler la mise en cache dans les navigateurs et caches partagées.

```apache
<IfModule mod_headers.c>
  <FilesMatch "\.(ico|jpe?g|png|gif|svg|css|webp|woff2|gz)$">
    Header set Cache-Control "max-age=2592000, public"
  </FilesMatch>
  <FilesMatch "\.(js)$">
    Header set Cache-Control "max-age=2592000, private"
  </FilesMatch>
  <FilesMatch  "\.(html|htm)$">
    Header set Cache-Control "max-age=7200, public"
  </FilesMatch>
  <FilesMatch "\.(pl|php|cgi|spl|scgi|fcgi)$">
    Header unset Cache-Control
  </FilesMatch>
</IfModule>
```

#### Compression Gzip

Le module deflate permet de faire compresser au serveur les données avant de les envoyer au client. Il permet d’alléger le poids des pages lors de leur transaction entre le serveur et le client et ainsi diminuer le temps de chargement des pages.

```apache
SetOutputFilter DEFLATE
AddOutputFilterByType DEFLATE "application/atom+xml" "application/javascript" "application/json" "application/ld+json" "application/manifest+json" "application/rdf+xml" "application/rss+xml" "application/schema+json" "application/vnd.geo+json" "application/vnd.ms-fontobject" "application/x-font-ttf" "application/x-javascript" "application/x-web-app-manifest+json" "application/xhtml+xml" "application/xml" "font/eot" "font/opentype" "image/bmp" "image/svg+xml" "image/vnd.microsoft.icon" "image/x-icon" "text/cache-manifest" "text/css" "text/html" "text/javascript" "text/plain" "text/vcard" "text/vnd.rim.location.xloc" "text/vtt" "text/x-component" "text/x-cross-domain-policy" "text/xml"
```

### Sécurité

#### Redirection des requêtes http:// vers https://

Un des points primordiaux des PWA est d'être sécurisé. Elle ne sera pas installable si le site n'a pas de certificat SSL. PWA Bunga! ne peut pas vous fournir ce certificat mais peut vous aider à rediriger automatiquement les requêtes http:// vers https://.

```apache
<IfModule mod_rewrite.c>
	RewriteCond %{HTTPS} off
	RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
</IfModule>
```

#### Empêcher le listing des répertoires

Si un dossier ne contient pas de fichier index.html à sa racine, l'utilisateur à accès à tous les dossiers et fichiers de ce dernier. Nous pouvons rendre l'accès interdit en redirigeant ces requêtes vers la page erreur 403

```apache
Options All -Indexes
```

#### Protection des fichiers cachés

Afin que personne n'est accès aux fichiers cachés comme les fichiers .htaccess ou .git, nous ajoutons cette déclaration au fichier :

```apache
<files .*>
	order allow,deny
	deny deny from all
</files>
```

### Redirections

#### Erreurs

Redirige les erreurs 403 et 404 vers les pages html correspondantes.

```apache
ErrorDocument 403 /403.html   
ErrorDocument 404 /404.html
```

#### Redirection des requêtes https:// vers https://www ou inversement

Si vous préférez https://www.nomdedomaine :

```apache
<IfModule mod_rewrite.c>
	RewriteCond %{HTTP_HOST} !^www\..+$ [NC]
	RewriteRule ^ https://www.%{HTTP_HOST}%{REQUEST_URI} [R=301,L]
</IfModule>
```

Si vous préférez https://nomdedomaine :

```apache
<IfModule mod_rewrite.c>
	RewriteCond %{HTTP_HOST} ^www\.(.+)$ [NC]
	RewriteRule ^ https://%1%{REQUEST_URI} [R=301,L]
</IfModule>
```

&nbsp;

## Contribuer

Pour contribuer, vous pouvez utiliser les trackers de problèmes du dépôt du module PWA Bunga! Starter

* [https://github.com/PwaBunga/starter/issues](https://github.com/PwaBunga/starter/issues)

Les modifications apportées sur ce dépôt seront ensuite effectuées sur le dépôt principal du projet.

Le tracker de problèmes est le canal privilégié pour signaler des bugs, des demandes de fonctionnalités et soumettre des requêtes de fusion, mais veuillez respecter les restrictions suivantes :

* Merci **de ne pas** utiliser le tracker de problèmes pour des demandes de support personnel.
* Merci **de ne pas** détourner ou saboter les problèmes. Maintenez la discussion sur le sujet et respectez les opinions des autres.

&nbsp;