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

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md)

# PWA Bunga! PWA Icons

PWA Bunga! provides you with a set of icon files to serve as templates for dimensions and formats which will allow you to display your logo in an optimized way on all terminals and application environments. You will find:

* The **Icons and Touch icons** for application environments and older versions of Android.
* The **Adaptive icons** (Maskable icons) for the Android environment.
* The **Touch icons** for the iOS environment.

&nbsp;

## Icons and Touch icons for application environments and older versions of Android

* **`icon-192.png`**
* **`icon-512.png`**

It is this image format that is called by all environments that accept PWAs. It usually matches the site's favicon.

### Icon display

Here are some examples of icon display.

#### Windows 11 shortcut and taskbar

![](https://www.pwabunga.com/assets/images/icon-test-windows.webp)

#### Home screen shortcut older versions of Android OS (8-)

![](https://www.pwabunga.com/assets/images/icon-test-android.webp)

### Icon dimensions

A very large number of different sizes can be supplied. Microsoft, for example, uses about fifty different sizes, from 44px x 44px for Windows shortcut icons, to 2480px x 1200px for app launcher screens on large screens ([Source](https://learn.microsoft.com/en-us/microsoft-edge/progressive-web-apps-chromium/how-to/icon-theme-color)).

Browsers are quite capable (and do) of resizing the different formats offered to adapt them to the module where they will display them. It is therefore advisable to provide at least 2 formats, 192px x 192px and 512px x 512px, which will allow you to meet the vast majority of uses.

Is it useful to declare more? It all depends on the device target (if you are aiming for 4K, it will be interesting to declare specific sizes for this format) or the reading level of your icon.

#### Reading level of an icon

A simple icon will adapt easily to any format and will remain readable regardless of the size used. For icons with a more complex level of detail, it is sometimes interesting to offer different versions in order to keep its icon readable in all situations.

* Example with the same icon for all formats

192px x 192px

![](https://www.pwabunga.com/assets/images/icon-test-lisible-01.webp)

88px x 88px

![](https://www.pwabunga.com/assets/images/icon-test-lisible-02.webp)

32px x 32px

![](https://www.pwabunga.com/assets/images/icon-test-lisible-03.webp)

* Example with different reading levels

192px x 192px

![](https://www.pwabunga.com/assets/images/icon-test-lisible-01.webp)

88px x 88px

![](https://www.pwabunga.com/assets/images/icon-test-lisible-04.webp)

32px x 32px

![](https://www.pwabunga.com/assets/images/icon-test-lisible-05.webp)

### Call icons

Here is how they are called on the Webmanifest file (for more information on the Webmnifest file, go to the PWA Bunga! PWA Webmanifest part of the documentation)

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
            "src": "icons/icon-512.png",
            "type": "image/png",
            "sizes": "512x512",
            "purpose": "any"
        }
    ]
}
```

## Maskable icons: adaptive icons for the Android environment

* **`icon-maskable-192.png`**
* **`icon-maskable-512.png`**

Since Oreo (Android 8+), Android has introduced adaptive icons through "Maskable" icons. This format allows you to adapt your icon to the different display possibilities offered by the multitude of versions of Android Os available on the different terminals on the market.

So that the icon can adapt to all situations, there are rules to follow:

* Declare the `purpose` property to `maskable` in the icons call from the `.webmanifest`
* Respect the safe area so that the logo is not truncated.
* Set a background color if you want a background other than white.

### Safe area and adaptive icon shapes

#### Adaptive icon safe area

The safe area is the area in which the logo will not be truncated by the shape of the icon displayed by the terminal.

![](https://www.pwabunga.com/assets/images/icon-maskable-security-area.webp)

#### The different shapes of adaptive icons

Google Pixel

![](https://www.pwabunga.com/assets/images/icon-test-maskable-circle.webp)

Samsung Galaxy

![](https://www.pwabunga.com/assets/images/icon-test-maskable-cylinder.webp)

Xiaomi

![](https://www.pwabunga.com/assets/images/icon-test-maskable-rounded-rectangle.webp)

Autres exemples de formes possibles

![](https://www.pwabunga.com/assets/images/icon-test-maskable-drop.webp)
![](https://www.pwabunga.com/assets/images/icon-test-maskable-vessel.webp)
![](https://www.pwabunga.com/assets/images/icon-test-maskable-pebble.webp)

### Display of adaptive icons

In order to understand how adaptive icons are displayed, here are different possible scenarios:

File icon-192.png called on file .webmanifest with "purpose": "any"

![](https://www.pwabunga.com/assets/images/icon-maskable-01.webp)

File icon-192.png called on file .webmanifest with "purpose": "maskable"

![](https://www.pwabunga.com/assets/images/icon-maskable-02.webp)

File icon-maskable-192.png with transparent background called on file .webmanifest with "purpose": "maskable"

![](https://www.pwabunga.com/assets/images/icon-maskable-03.webp)

File icon-maskable-192.png with colored background called on file .webmanifest with "purpose": "maskable"

![](https://www.pwabunga.com/assets/images/icon-maskable-04.webp)

#### Situation

![](https://www.pwabunga.com/assets/images/webmanifest-example-maskable-icons.webp)

### Call for adaptive icons

Here is how they are called on the Webmanifest file (for more information on the Webmnifest file, go to the PWA Bunga! PWA Webmanifest part of the documentation)

```json
{ 
    "icons": [
        {
            "src": "icons/icon-maskable-192.png",
            "type": "image/png",
            "sizes": "192x192",
            "purpose": "maskable"
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

*To help you test, create or modify your adaptive icons, you can go to [Maskable​.app](https://maskable.app/).*

## Touch icon for iOS environment

* **`apple-touch-icon.png`**

When a user installs a PWA on their iOS device, the installed app icon on the home screen will be based on the icon that is specified in the app's Webmanifest file, rather than on the file `apple-touch-icon.png`.

However, it is still recommended to provide `apple-touch-icon.png`, as this can be used as a loading icon for your PWA when launching, and can also be used for functions such as sharing and adding the application to favorites.

When developing a PWA for iOS, you should specify the app icon in the app manifest, but you should also provide a Touch Icon to improve the user experience.

### Formats and dimensions of `apple-touch-icon.png`

To create a Touch Icon for iOS, you must use a square image in PNG or JPG format. The recommended size for the image is 180x180 pixels, but it is possible to use larger sizes. The image should be sharp and have a resolution of 72 DPI or higher.