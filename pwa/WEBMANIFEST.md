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

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md)

# PWA Bunga! PWA Webmanifest

The `.webmanifest` file is a JSON file that describes metadata for your Progressive Web App (PWA). This file is important because it allows your application to be installed on the user's home screen, set the colors of the navigation bar and other interface elements, specify the icons to use for the application and much more.

PWA Bunga! includes a template `.webmanifest` file to help you get started quickly with creating your own PWA. In this documentation, we'll walk through the different sections of the web manifest file and explain how to customize them to suit your application's needs.

* **Make the PWA installable**.
* **Call the icons that will appear on the homepage** of the mobile or as a shortcut in the operating systems.
* **Set PWA settings**.

&nbsp;

* **`app.webmanifest`**

&nbsp;

## General information about the PWA

### Name

The following 2 properties allow you to give a short and long version of the PWA name:

```json
{
	"short_name": "PWA Bunga!",
	"name": "PWA Bunga! Template"
}
```

### short_name

`short_name` will be displayed on the home screen of mobile devices under the app icon. On Google Pixel 5 running Android 13, it will be displayed entirely if the title does not exceed 160px in width, or approximately 8 characters. Beyond this dimension, the name will be truncated with `...` at the end:

![](https://www.pwabunga.com/assets/images/webmanifest-example-title-short.webp)

For this example, here are the 4 values of `short_name` entered (from left to right):

* `"PWA Bunga!"`
* `"PWABunga!"`
* `"PWA Bunga"`
* `"PWABunga"`

### Description

This property defines a general description of the application.

```json
{
	"description": "PWA Bunga! is a simple Front-end Template for built fast Progressive Web Apps"
}
```

### Language

This property defines the language of the application:

```json
{
	"lang": "en"
}
```

### identifier

This property defines a unique application identifier.

```json
{
	"id": "?homescreen=1"
}
```

## Navigating the PWA

### Homepage URL

This property defines the page to display when the user opens the PWA (For possible statistical needs, we add a utm_soucre to see where the users come from):

```json
{
	"start_url": "../?utm_source=homescreen"
}
```

### Navigation scope

This property defines the scope of the navigation. If the url is relative, it will be relative to where the webmanifest file is located.

```json
{
	"scope": "../"
}
```

## PWA Theme

### Display mode

This property defines the display mode:

```json
{
	"display": "fullscreen"
}
```

Possible values:

* `fullscreen` the application will take all available screen size.

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-fullscreen.webp" alt="logo PWA Bunga! PWA"/>
</div>


* `standalone` the application will take the same size as the native applications.

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-standalone.webp" alt="logo PWA Bunga! PWA"/>
</div>

* `minimal-ui` standalone + basic navigation elements

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-minimal-ui.webp" alt="logo PWA Bunga! PWA"/>
</div>


* `browser` with this value, the application will remain opened by the browser in the classic way and cannot be installed as a PWA.

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-browser.webp" alt="logo PWA Bunga! PWA"/>
</div>

### Orientation

This property defines the orientation to use by default:

```json
{
	"orientation": "portrait"
}
```

Possible values:

* `portrait`: portrait.
* `landscape`: landscape.

### Theme color

This property sets the color of the theme. If this property is recognized by the browser, it will use it on the navigation elements.

```json
{
	"theme_color": "#5d00d8"
}
```

* fullscreen with theme

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-fullscreen.webp" alt="logo PWA Bunga! PWA"/>
</div>


* standalone with theme

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-theme-standalone.webp" alt="logo PWA Bunga! PWA"/>
</div>

* minimal-ui with theme

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-theme-minimal-ui.webp" alt="logo PWA Bunga! PWA"/>
</div>


* browser with theme

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-browser.webp" alt="logo PWA Bunga! PWA"/>
</div>

### Background color

This property sets the background color of the application. It appears when the application is launched, for example.

```json
{
	"background_color": "#dfcdf8"
}
```
#### PWA launch screen

* Without `background_color`

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-bg-without.webp" alt="logo PWA Bunga! PWA"/>
</div>


* With `background_color`

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-bg.webp" alt="logo PWA Bunga! PWA"/>
</div>

### Icons

*For more explanation and details on the formats used, see the PWA Bunga! PWA Icons.*

This property defines the icons that will be displayed on the home screens of mobile devices or on the shortcuts of operating systems. We call here 4 files, 2 icons for all uses and 2 maskable icons for OS using this format.

```json
{ 
	"icons": [
		{
			"src": "icons/icon-192.png",
			"type": "image/png",
			"sizes": "192x192",
			"purpose": "any"
		},
		{
			"src": "icons/icon-maskable-192.png",
			"type": "image/png",
			"sizes": "192x192",
			"purpose": "maskable"
		},
		{
			"src": "icons/icon-512.png",
			"type": "image/png",
			"sizes": "512x512",
			"purpose": "any"
		},
		{
			"src": "icons/icon-maskable-512.png",
			"type": "image/png",
			"sizes": "512x512",
			"purpose": "maskable"
		}
	]
}
```

&nbsp;