* [Documentation homepage](https://github.com/PwaBunga/documentation/)
* [Documentation of the PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)
* [Documentation of the PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/CSS.md)
* [Documentation of the PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-starter-circle.png" alt="logo PWA Bunga! Starter"/>
</div>

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md)

# PWA Bunga! Starter

The PWA Bunga! is designed to get you started quickly with a set of basic folders and files that can be customized to meet the specific needs of your web site or application.

&nbsp;

## PWA Bunga! content Starter

The PWA Bunga! Starter includes:

* resource folders
* empty CSS and JS files which can be filled according to your needs
* an HTML template
* favicons in .ico, .svg or .png formats
* 404 and 403 error pages
* an htaccess file

&nbsp;

## PWA Documentation Summary Bunga! Starter

* [Resource Folders](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#resource-folders)
* [Blank files](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#blank-files)
* [Error pages](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#)
   - [Error 403](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#error-403)
   - [Error 404](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#error-404)
* [Favicons](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#favicons)
   - [ICO file](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#fichier-ico)
   - [SVG file](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#fichier-scg)
   - [You don't have a logo in SVG format?](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#vous-navez-pas-de-logo-au-format -svg-)
* [HTML Template](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#template-html)
   - [HTML tag](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#html-tag)
   - [Meta charset tag](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#balise-meta-charset)
   - [Title tag](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#title-tag)
   - [Meta description tag](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#balise-meta-description)
   - [Viewport meta tag](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#viewport-meta-tag)
   - [Open Graph](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#open-graph)
   - [Favicons](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#favicons-1)
   - [Touch-icon for iOS](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#touch-icon-for-ios)
   - [Progressive Web App](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#progressive-web-app)
   - [Management of themes in light or dark mode](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#gestion-des-thèmes-en-mode-light-ou-dark)
   - [Call CSS files](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#call-des-fichiers-css)
   - [PWA User Interface](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#pwa-user-interface)
   - [Call Javascript files](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#call-des-fichiers-javascript)
* [.htaccess file](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#htaccess-file)
   - [Performances](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#performances)
   - [Security](https://github.com/PwaBunga/documentation/blob/main/en/STARTER.md#security)
   - [Redirections](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md#redirections)

&nbsp;

## Assets folders

The `assets` folder consists of the basic folders to organize the files for your website or web application.

* **`assets`**: Contains common project resources.
  - **`css`**: Contains the style sheets of the project..
  - **`fonts`**: Contains project fonts.
  - **`images`**: Contains the images of the project.
  - **`js`**: Contains the project's javascript files.
    - **`vendor`**: Contains third-party js libraries.

&nbsp;

## Empty files

PWA Bunga! contains a empty, ready-to-use style sheet and javascript file. These 2 files are called from the html template.

* assets
  - css
    - **`styles.css`**
  - js
    - **`scripts.js`**

&nbsp;

## Error Pages

PWA Bunga! provides 2 error pages:

### Erreur 403

* **`403.html`**

This error indicates that the server understands the request but refuses to authorize it. For example, you can prohibit access to site folders that do not contain an index.html file at their root and redirect to the 403 error page indicating that access is prohibited.

### Erreur 404

* **`404.html`**

This error indicates that the request to view a web page is incorrect in some way. This is for example the case when the page does not exist.

*The redirection of errors to these pages is done at the server configuration file level (See .htaccess file).*

&nbsp;

## Favicons

Currently, to have a favicon activated on all browsers, you have to call 2 files:

### ICO File

* **`favicon.ico`**

This file will be used by old browsers to display the favicon and by Google to display the icon on the search result. This format allows to encapsulate multiple dimensions, and we are going to need an .ico containing the following 3 dimensions: 16px x 16px and 32px x 32px for browsers, and 48px x 48px for Google search result ([Source](https://developers.google.com/search/docs/appearance/favicon-in-search?hl=fr)).

### SVG file

* **`favicon.svg`**

This file is going to be used by all modern browsers. It is ideal because light, without loss of quality and allows interesting functionalities like a different display if the user defines the "Dark Mode" on his environment.

### You don't have a logo in SVG format?

* **`favicon-16.png`**
* **`favicon-32.png`**

You can use 2 png files in 16px x 16px and 32px x 32px formats instead. They will be used by all modern and less modern browsers.

You will then have to modify the html template by modifying this part:

```html
<link rel="icon" type="image/svg+xml" href="favicon.svg">
```

by :

```html
<link rel="icon" type="image/png" sizes="32x32" href="favicon-32.png">
<link rel="icon" type="image/png" sizes="16x16" href="favicon-16.png">
```

*The icons and touch-icons can be found and will be detailed in the PWA Bunga! PWA part.*

## HTML template

index.html is an HTML template that contains everything you need to start a website or web application project.

* **`index.html`**

```html
<!doctype html>
```

### Balise `html`

#### Lang

Put here the language of your site or web application.

#### prefix

The `prefix` attribute present on the html tag is the required prefix for Open Graph protocol meta tags. You can remove it if you don't use it.

```html
<html lang="" prefix="og: http://ogp.me/ns#">
```

### Balise `meta` `charset`

This declaration tells the browser to use the universal Unicode character set.

```html
<meta charset="utf-8">
```

### Balise `title`

This tag is used to give a title to the web page, it appears on the browser tab and in search results. It is one of the fundamental elements of natural referencing.

```html
<title></title>
```

### Balise `meta` `description`

This tag is used to describe the content of the web page. The content is found under the title and URL of the page in search engine results.

```html
<meta name="description" content="">
```

### Balise `meta` `viewport`

This statement optimizes the viewport for mobile.

#### width=device-width

Tells the browser to use the device's available width.

#### initial-scale=1

Sets the initial zoom level to 1 pixel of the viewport equals 1 CSS pixel.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### Open Graph

The Open Graph Protocol (OGP) allows you to add metadata to the pages of a website. It allows web pages to behave like social network objects, and allows the correct title, description and image to be displayed when sharing.

#### og:type

Indicates to the social network the nature of the main content of the page (example: article, video, music, etc.)

#### og:title

Determines the title of the page for the Open Graph (beyond about 65 characters, the title will be truncated).

#### og:description

Indicates a short description of the content of the page (The current recommendation is not to exceed 300 characters for optimal display). This declaration is optional.

#### og:url

Specifies the canonical URL of the page.

#### og:image

Indicates the image to display when sharing the page on social networks.

```html
<meta property="og:type" content="">
<meta property="og:title" content="">
<meta property="og:description" content="">
<meta property="og:url" content="">
<meta property="og:image" content="">
```

### Favicons

Calling favicons. If you have your favicon in SVG format:

```html
<link rel="icon" href="favicon.ico" sizes="any">
<link rel="icon" href="favicon.svg" type="image/svg+xml">
```

Otherwise, use the PNG format:

```html
<link rel="icon" href="favicon.ico" sizes="any">
<link rel="icon" type="image/png" sizes="32x32" href="favicon-32.png">
<link rel="icon" type="image/png" sizes="16x16" href="favicon-16.png">
```

### Touch icon for iOS

Call of the icon for the iOS environment.

```html
<link rel="apple-touch-icon" href="pwa/apple-touch-icon.png">
```

### Progressive Web App

Call of the webmanifest file which will make your web project installable and define certain parameters. This file is detailed in the PWA Bunga! PWAs.

```html
<link rel="manifest" href="pwa/app.webmanifest">
```

### Management of themes in light or dark mode

These declarations will allow the browser to offer a color theme on your site according to the theme chosen (dark or light) by the user.

```html
<meta name="theme-color" content="#fafafa" media="(prefers-color-scheme: light)">
<meta name="theme-color" content="#afafaf" media="(prefers-color-scheme: dark)">
```

### Calling CSS files

Call of the basic pwa bunga.css CSS file (this file will be detailed in the PWA Bunga! CSS part) and of the styles.css file.

```html
<link rel="stylesheet" href="assets/css/pwabunga.css">
<link rel="stylesheet" href="assets/css/styles.css">
<link rel="stylesheet" href="pwa/css/pwabunga-ui.css">
```

### PWA UI

These HTML elements are the UI elements offered by PWA Bunga! to improve the user experience.
They work with the functions present in the file [`pwabunga.js`](https://github.com/PwaBunga/documentation/blob/main/pwa/JS.md) and use the components of [`pwabunga- ui.css`](https://github.com/PwaBunga/documentation/blob/main/pwa/CSS_UI.md) for formatting.

#### Promo banner and install button

Used by the `pwaInstall()` function, this code displays a banner promoting the installation of the PWA with an install button.

It uses the `pwa-banner` and `pwa-btn` components, formatted in the `pwabunga-ui.css` file.

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

#### Installation confirmation banner

Used by the `pwaInstall()` function, this code is used to display a confirmation banner that appears when the PWA installation is complete.

It uses the `pwa-banner` component, formatted in the `pwabunga-ui.css` file.

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

#### Update banner

Used by the `pwaUpdate()` function, this code displays a banner indicating that an application update is available with a button to perform it.

It uses the `pwa-banner` and `pwa-btn` components, formatted in the `pwabunga-ui.css` file.

```html
<div class="pwa-update pwa-banner to-pwa-snackbar">
   <svg class="pwa-update-close pwa-install-confirm-close" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="32">
     <title>close</title>
     <path d="M19,6.41L17.59,5L12,10.59L6.41,5L5,6.41L10.59,12L5,17.59L6.41,19L12,13.41L17.59,19L19,17.59L13.41,12L19,6.41 Z" />
   </svg>
   <p class="pwa-banner-text">
     <strong class="pwa-banner-title">New version available!</strong>
   </p>
   <button class="pwa-update-btn pwa-btn">Update</button>
</div>
```

#### Action button bar

Used by the `pwaShare()` and `pwaParams()` functions, this code is used to display the action buttons of the PWA, namely the share button and the button for accessing the application settings.

It uses the `pwa-actions` and `pwa-btn` components, formatted in the `pwabunga-ui.css` file.

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

#### PWA settings insert

Used by the `pwaParams()` function, this code displays the parameters box containing the PWA version and permissions.

It uses the `pwa-modal`, `pwa-switch`, `pwa-alert` and `pwa-permission-item` components, formatted in the `pwabunga-ui.css` file.

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

#### PWA Loader

Used by the `pwaInstall()` and `pwaUpdate()` functions, this code displays a loader when the PWA installs or updates.

It uses the `pwa-loader` component, formatted in the `pwabunga-ui.css` file.

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

### Calling JavaScript files

Call of the basic JS file pwabunga.js (this file will be detailed in the PWA Bunga! PWA part) and of the scripts.js file.

```html
<script src="pwa/js/pwabunga.js"></script>
<script src="assets/js/scripts.js"></script>
```

## .htaccess File

The htaccess configuration file is used by the Apache web server, which is used by most hosting providers.

* **`.htaccess`**

### Performance

#### Browser cache

Directives are provided to control caching in browsers and shared caches.

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

The deflate module allows the server to compress data before sending it to the client. This reduces the size of pages during transmission between the server and the client, thereby reducing the page loading time and improving overall performance.

```apache
SetOutputFilter DEFLATE
AddOutputFilterByType DEFLATE "application/atom+xml" "application/javascript" "application/json" "application/ld+json" "application/manifest+json" "application/rdf+xml" "application/rss+xml" "application/schema+json" "application/vnd.geo+json" "application/vnd.ms-fontobject" "application/x-font-ttf" "application/x-javascript" "application/x-web-app-manifest+json" "application/xhtml+xml" "application/xml" "font/eot" "font/opentype" "image/bmp" "image/svg+xml" "image/vnd.microsoft.icon" "image/x-icon" "text/cache-manifest" "text/css" "text/html" "text/javascript" "text/plain" "text/vcard" "text/vnd.rim.location.xloc" "text/vtt" "text/x-component" "text/x-cross-domain-policy" "text/xml"
```

### Security

#### Redirection of http:// requests to https://

One of the primary requirements for PWAs is to be secure. It cannot be installed if the site does not have an SSL certificate. PWA Bunga! cannot provide you with this certificate but can help you automatically redirect http:// requests to https://.

```apache
<IfModule mod_rewrite.c>
	RewriteCond %{HTTPS} off
	RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
</IfModule>
```

#### Preventing directory listing

If a directory does not have an index.html file at its root, the user has access to all the folders and files in it. We can make access forbidden by redirecting these requests to the 403 error page.

```apache
Options All -Indexes
```

#### Protection of hidden files

To prevent access to hidden files such as .htaccess or .git, we add the following statement to the file:

```apache
<files .*>
	order allow,deny
	deny deny from all
</files>
```

### Redirects

#### Errors

Redirects error 403 and 404 to the corresponding HTML pages.

```apache
ErrorDocument 403 /403.html   
ErrorDocument 404 /404.html
```

#### Redirection of https:// requests to https://www or vice versa

If you prefer https://www.domainname:

```apache
<IfModule mod_rewrite.c>
	RewriteCond %{HTTP_HOST} !^www\..+$ [NC]
	RewriteRule ^ https://www.%{HTTP_HOST}%{REQUEST_URI} [R=301,L]
</IfModule>
```

If you prefer https://domainname:

```apache
<IfModule mod_rewrite.c>
	RewriteCond %{HTTP_HOST} ^www\.(.+)$ [NC]
	RewriteRule ^ https://%1%{REQUEST_URI} [R=301,L]
</IfModule>
```

&nbsp;

## Contribute

To contribute, you can use the issue trackers of the PWA Bunga! Starter module repository.

* [https://github.com/PwaBunga/starter/issues](https://github.com/PwaBunga/starter/issues)

The modifications made on this repository will then be made on the main repository of the project.

The issue tracker is the preferred channel for bug reports, features requests and submitting pull requests, but please respect the following restrictions:

* Please **do not** use the issue tracker for personal support requests.
* Please **do not** derail or troll issues. Keep the discussion on topic and= respect the opinions of others.

&nbsp;