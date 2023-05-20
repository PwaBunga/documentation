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

[English version](https://github.com/PwaBunga/documentation/blob/main/pwa/WEBMANIFEST.md)

# PWA Bunga! PWA Webmanifest

Le fichier `.webmanifest` est un fichier JSON qui décrit les métadonnées de votre Progressive Web App (PWA). Ce fichier est important car il permet à votre application d'être installée sur l'écran d'accueil de l'utilisateur, de définir les couleurs de la barre de navigation et d'autres éléments d'interface, de spécifier les icônes à utiliser pour l'application et bien plus encore.

PWA Bunga! inclut un modèle de fichier `.webmanifest` pour vous aider à démarrer rapidement avec la création de votre propre PWA. Dans cette documentation, nous allons passer en revue les différentes sections du fichier web manifest et expliquer comment les personnaliser en fonction des besoins de votre application.

* **Rendre la PWA installable**.
* **Appeler les icones qui apparaitront sur l'accueil** du mobile ou en raccourci dans les systèmes d'exploitations.
* **Définir les paramètres de la PWA**.

&nbsp;

* **`app.webmanifest`**

*Les exemples donnés dans cette partie ont été réalisés avec un Google Pixel 5 sous Android 13.*

&nbsp;

## Informations générales de la PWA

### Nom

Les 2 propriétés suivantes permettent de donner une version courte et longue du nom de la PWA :

```json
{
	"short_name": "PWA Bunga!",
	"name": "PWA Bunga! Template"
}
```

### short_name

`short_name` va être affiché sur l'écran d'accueil des appareils mobiles sous l'icône de l'application. Sur Google Pixel 5 sous Android 13, il sera affiché entièrement si le titre ne dépasse pas 160px de largeur, soit environ 8 caractères. Au-delà de cette dimension, le nom sera tronqué avec `...` à la fin :

![](https://www.pwabunga.com/assets/images/webmanifest-example-title-short.webp)

Pour cet exemple, voici les 4 valeurs de `short_name` renseigné (de gauche à droite) :

* `"PWA Bunga!"`
* `"PWABunga!"`
* `"PWA Bunga"`
* `"PWABunga"`

### Description

Cette propriété définit une description générale de l'application.

```json
{
	"description": "PWA Bunga! is a simple Front-end Template for built fast Progressive Web Apps"
}
```

### Langue

Cette propriété définit la langue de l'application :

```json
{
	"lang": "en"
}
```

### identifiant

Cette propriété définit un identifiant unique de l'application.

```json
{
	"id": "?homescreen=1"
}
```

## Navigation de la PWA

### URL de la page d'accueil

Cette propriété définit la page à afficher lors de l'ouverture de la PWA par l'utilisateur (Pour d'éventuels besoins statistiques, on ajoute un utm_soucre permettant de voir la provenance des utilisateurs) :

```json
{
	"start_url": "../?utm_source=homescreen"
}
```

### Portée de la navigation

Cette propriété définit la portée de la navigation. Si l'url est relative, il sera relatif à l'endroit où se trouve le fichier webmanifest.

```json
{
	"scope": "../"
}
```

## Thème de la PWA

### Mode d'affichage

Cette propriété définit le mode d'affichage :

```json
{
	"display": "fullscreen"
}
```

Valeurs possibles :

* `fullscreen` : l'application prendra toute la taille disponible de l'écran.

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-fullscreen.webp" alt="logo PWA Bunga! PWA"/>
</div>


* `standalone` : l'application prendra la même taille que les application native.

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-standalone.webp" alt="logo PWA Bunga! PWA"/>
</div>

* `minimal-ui` : standalone + les éléments basiques de navigation

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-minimal-ui.webp" alt="logo PWA Bunga! PWA"/>
</div>


* `browser` : avec cette valeur, l'application restera ouvert par le navigateur de manière classique et ne pourra pas être installé en tant que PWA.

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-browser.webp" alt="logo PWA Bunga! PWA"/>
</div>

### Orientation

Cette propriété définit l'orientation à utiliser par défaut :

```json
{
	"orientation": "portrait"
}
```

Valeurs possibles :

* `portrait`: portrait.
* `landscape`: paysage.

### Couleur du thème

Cette propriété définit la couleur du thème. Si cette propriété est reconnue par le navigateur, il l'utilisera sur les éléments de navigations.

```json
{
	"theme_color": "#5d00d8"
}
```

* `fullscreen` avec `theme_color`

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-fullscreen.webp" alt="logo PWA Bunga! PWA"/>
</div>


* `standalone` avec `theme_color`

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-theme-standalone.webp" alt="logo PWA Bunga! PWA"/>
</div>

* `minimal-ui` avec `theme_color`

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-theme-minimal-ui.webp" alt="logo PWA Bunga! PWA"/>
</div>


* `browser` avec `theme_color`

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-browser.webp" alt="logo PWA Bunga! PWA"/>
</div>

### Couleur de fond

Cette propriété définit la couleur de fond de l'application. Elle apparait au lancement de l'application par exemple.

```json
{
	"background_color": "#dfcdf8"
}
```
#### Ecran de lancement de la PWA

* Sans `background_color`

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-bg-without.webp" alt="logo PWA Bunga! PWA"/>
</div>


* Avec `background_color`

<div>
  <img src="https://www.pwabunga.com/assets/images/webmanifest-example-bg.webp" alt="logo PWA Bunga! PWA"/>
</div>

### Icônes

*Pour plus d'explications et de détails sur les formats utilisés, voir la partie PWA Bunga! PWA Icônes.*

Cette propriété définit les icones qui seront affichées sur les écrans d'accueil des appareils mobiles ou sur les raccourcis des systèmes d'exploitation. Nous appelons ici 4 fichiers, 2 icônes pour toutes utilisations et 2 icônes maskable pour les OS utilisant ce format.

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