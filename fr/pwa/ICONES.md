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

[English version](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONS.md)

# PWA Bunga! PWA Icônes

PWA Bunga! vous fourni un ensemble de fichiers d'icônes permettant de servir de gabarits pour avoir les dimensions et les formats qui vous permettront d'afficher votre logo de manière optimisé sur tous les terminaux et environnements applicatifs. Vous trouverez :

* Les **Icônes et Touch icons** pour les environnements applicatifs et les anciennes versions d'Android.
* Les **Icônes adaptatives** (Maskable icons) pour l'environnement Android.
* Les **Touch icons** pour l'environnement iOS.

&nbsp;

## Icônes et Touch icons pour les environnements applicatifs et les anciennes versions d'Android

* **`icon-192.png`**
* **`icon-512.png`**

C'est ce format d'image qui est appelé par tous les environnements acceptant les PWA. Il correspond habituellement au favicon du site.

### Affichage des icônes

Voici quelques exemples d'affichage des icônes.

#### Raccourci et barre des tâches Windows 11

![](https://www.pwabunga.com/assets/images/icon-test-windows.webp)

#### Raccourci écran d'accueil anciennes versions d'Android OS (8-)

![](https://www.pwabunga.com/assets/images/icon-test-android.webp)

### Dimensions des icônes

On peut fournir un très grand nombre de dimensions différentes. Microsoft, par exemple, utilise une cinquantaine de tailles différentes, de 44px x 44px pour les icones de raccourci Windows, à 2480px x 1200px pour les écrans de lancement de l'app sur les grands écrans ([Source](https://learn.microsoft.com/en-us/microsoft-edge/progressive-web-apps-chromium/how-to/icon-theme-color)).

Les navigateurs sont tout à fait capable (et le font) de redimensionner les différents formats proposés pour les adapter au module où ils vont les afficher. Il est donc conseillé de fournir au moins 2 formats, 192px x 192px et 512px x 512px, qui vont permettre de répondre à la grande majorité des utilisations.

Est-ce utile d'en déclarer plus ? Tout dépend de la cible des appareils (si vous visez le 4K, il va être intéressant de déclarer des tailles spécifiques à ce format) ou du niveau de lecture de votre icone.

#### Niveau de lecture d'une icone

Une icône simple s'adaptera facilement à tout format et restera lisible quel que soit la taille utilisée. Pour des icônes avec un niveau de détails plus complexe, il est parfois intéressant de proposer des versions différentes afin de garder son icône lisible dans toute les situations.

* Exemple avec la même icône pour tous les formats

192px x 192px

![](https://www.pwabunga.com/assets/images/icon-test-lisible-01.webp)

88px x 88px

![](https://www.pwabunga.com/assets/images/icon-test-lisible-02.webp)

32px x 32px

![](https://www.pwabunga.com/assets/images/icon-test-lisible-03.webp)

* Exemple avec différents niveaux de lecture

192px x 192px

![](https://www.pwabunga.com/assets/images/icon-test-lisible-01.webp)

88px x 88px

![](https://www.pwabunga.com/assets/images/icon-test-lisible-04.webp)

32px x 32px

![](https://www.pwabunga.com/assets/images/icon-test-lisible-05.webp)

### Appel des icônes

Voici la manière dont ont les appellent sur le fichier Webmanifest (pour plus d'informations sur le fichier Webmanifest, allez sur la partie PWA Bunga! PWA Webmanifest de la documentation)

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

&nbsp;

## Maskable icons : icônes adaptatives pour l'environnement Android

* **`icon-maskable-192.png`**
* **`icon-maskable-512.png`**

Depuis Oreo (Android 8+), Android à introduit les icônes adaptatives par le biais des "Maskable" icônes. Ce format permet d'adapter votre icône aux différentes possibilités d'affichage que propose la multitude de déclinaison d'Android Os disponibles sur les différents terminaux du marchés.

Afin que l'icone puisse s'adapter à toutes les situations, il y a des règles à respecter :

* Déclarer la propriété `purpose` à `maskable` dans l'appel des icônes du fichier `.webmanifest`
* Respectez la zone de sécurité afin que le logo ne soit pas tronqué.
* Mettre une couleur de fond si vous souhaitez un fond autre que blanc.

### Zone de sécurité et formes des icônes adaptatives

#### Zone de sécurité des icônes adaptatives

La zone de sécurité est la zone dans laquelle le logo ne sera pas tronqué par la forme de l'icône affichée par le terminal.

![](https://www.pwabunga.com/assets/images/icon-maskable-security-area.webp)

#### Les différentes formes d'icônes adaptatives

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

### Affichage des icônes adaptatives

Afin de comprendre comment sont affichées les icônes adaptatives, voici différents cas de figures possibles :

Fichier icon-192.png appelé sur le fichier .webmanifest avec "purpose": "any"

![](https://www.pwabunga.com/assets/images/icon-maskable-01.webp)

Fichier icon-192.png appelé sur le fichier .webmanifest avec "purpose": "maskable"

![](https://www.pwabunga.com/assets/images/icon-maskable-02.webp)

Fichier icon-maskable-192.png avec un fond transparent appelé sur le fichier .webmanifest avec "purpose": "maskable"

![](https://www.pwabunga.com/assets/images/icon-maskable-03.webp)

Fichier icon-maskable-192.png avec un fond de couleur appelé sur le fichier .webmanifest avec "purpose": "maskable"

![](https://www.pwabunga.com/assets/images/icon-maskable-04.webp)

#### Mise en situation

![](https://www.pwabunga.com/assets/images/webmanifest-example-maskable-icons.webp)

### Appel des icônes adaptatives

Voici la manière dont ont les appellent sur le fichier Webmanifest (pour plus d'informations sur le fichier Webmanifest, allez sur la partie PWA Bunga! PWA Webmanifest de la documentation)

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

*Pour vous aidez à tester, créer ou modifier vos icônes adaptatives, vous pouvez aller sur [Maskable​.app](https://maskable.app/).*

&nbsp;

## Touch icon pour l'environnement iOS

* **`apple-touch-icon.png`**

Lorsqu'un utilisateur installe une PWA sur son appareil iOS, l'icône de l'application installée sur l'écran d'accueil sera basée sur l'icône qui est spécifiée dans le ficher Webmanifest de l'application, plutôt que sur le fichier `apple-touch-icon.png`.

Cependant, il est toujours recommandé de fournir `apple-touch-icon.png`, car celui-ci peut être utilisé comme une icône de chargement pour votre PWA lors du lancement, et peut également être utilisé pour des fonctions telles que le partage et l'ajout de l'application aux favoris.

Lorsque vous développez une PWA pour iOS, vous devez spécifier l'icône de l'application dans le manifeste de l'application, mais vous devez également fournir un Touch Icon pour améliorer l'expérience utilisateur.

### Formats et dimensions de `apple-touch-icon.png`

Pour créer un Touch Icon pour iOS, vous devez utiliser une image carrée au format PNG ou JPG. La taille recommandée pour l'image est de 180x180 pixels, mais il est possible d'utiliser des tailles plus grandes. L'image doit être nette et avoir une résolution de 72 DPI ou plus.