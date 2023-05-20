* [Accueil de la documentation](https://github.com/PwaBunga/documentation/blob/main/fr/)
* [Documentation du module PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md)
* [Documentation du module PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md)
* [Documentation du module PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/fr/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-css-circle.png" alt="logo PWA Bunga! CSS"/>
</div>

[English version](https://github.com/PwaBunga/documentation/blob/main/CSS.md)

# PWA Bunga! CSS

pwabunga.css est le fichier CSS de base de PWA Bunga!

&nbsp;

## Contenu de PWA Bunga! CSS

Le module PWA Bunga! CSS comprend :

* De la **normalisation**
* Des **améliorations ergonomiques**
* Du **reset**
* Des **bonnes pratiques** (Pour faciliter la tâche du développeur)

&nbsp;

* **`pwabunga.css`**

&nbsp;

## Sommaire de la documentation de PWA Bunga! CSS

* [Comportement au défilement](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#comportement-au-défilement)
  - [Améliorations ergonomiques](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#améliorations-ergonomiques)
* [Héritages universels](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#héritages-universels)
  - [Bonnes pratiques](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#bonnes-pratiques)
* [Selection](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#selection)
  - [Reset](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#reset)
* [L'élément root](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#lélément-root)
  - [Bonnes pratiques](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#bonnes-pratiques-1)
  - [Améliorations ergonomiques](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#améliorations-ergonomiques-1)
* [Sections](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#sections)
  - [Reset](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#reset-1)
* [Grouping content](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#grouping-content)
  - [Améliorations ergonomiques](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#améliorations-ergonomiques-2)
  - [Reset](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#reset-2)
* [Text-level semantics](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#text-level-semantics)
  - [Normalisation](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#normalisation)
  - [Améliorations ergonomiques](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#améliorations-ergonomiques-3)
  - [Reset](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#reset-3)
* [Embedded content](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#embedded-content)
  - [Normalisation](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#normalisation-1)
  - [Améliorations ergonomiques](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#améliorations-ergonomiques-4)
  - [Reset](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#reset-4)
* [Tabular data](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#tabular-data)
  - [Normalisation](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#normalisation-2)
  - [Améliorations ergonomiques](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#améliorations-ergonomiques-5)
  - [Reset](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#reset-5)
* [Forms](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#forms)
  - [Normalisation](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#normalisation-3)
  - [Améliorations ergonomiques](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#améliorations-ergonomiques-6)
  - [Reset](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#reset-6)
* [Interactive](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#interactive)
  - [Normalisation](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#normalisation-4)

&nbsp;

## Comportement au défilement

### Améliorations ergonomiques

Si l'utilisateur n'as pas modifié ses réglages pour minimiser la quantité d'animation ou de mouvement, on définit un effet de défilement fluide pour le comportement de défilement d'une boîte, lorsque le défilement se produit en raison de la navigation ou des API de défilement CSSOM.

```css
@media (prefers-reduced-motion: no-preference) { 
	:root {
		scroll-behavior: smooth; 
	}
}
```

&nbsp;

## Héritages universels

### Bonnes pratiques

On rend héritable la propriété `box-sizing` pour tous les éléments.

```css
*,
::before,
::after {
	box-sizing: inherit;
}
```

&nbsp;

## Selection

### Reset

On supprime le `text-shadow` de la surbrillance de la sélection.

```css
::-moz-selection {
	text-shadow: none; 
}

::selection {
	text-shadow: none;
}
```

&nbsp;

## L'élément root

### Bonnes pratiques

On modifie le dimensionnement du modèle de boîte pour l'élément `html`.

```css
html {
	box-sizing: border-box;
}
```

L'unité de valeur relative fait référence à la taille de l'élément parent. La taille de police par défaut des navigateurs est de 16 pixels. Pour un rapport de 1em/10px, nous divisons la taille par la taille par défaut : 10/16 x 100 = 62,5 %.

```css
html {
	font-size: 62.5%;
}
```

### Améliorations ergonomiques

On améliore la cohérence des polices par défaut pour tous les navigateurs.

```css
html {
	font-family: system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji';
}
```

On force la barre de défilement du navigateur à toujours être visible pour éviter les sauts gênants lorsque entre les pages qui ont/n'ont pas assez de contenu.

```css
html {
	overflow-y: scroll;
}
```

On affiche la barre de défilement à masquage automatique lors des interactions avec la souris et lors des interactions tactiles et clavier.

```css
html {
	-ms-overflow-style: -ms-autohiding-scrollbar;
}
```

On rend les polices sur OSX plus cohérentes avec d'autres systèmes qui n'utilise pas l'anticrénelage sous-pixel.

```css
html {
	-moz-osx-font-smoothing: grayscale;
	-webkit-font-smoothing: antialiased;
}
```

On supprime l'effet de surbrillance sur l'action "tapped".

```css
html {
	-webkit-tap-highlight-color: rgba(0,0,0,0);
	-webkit-tap-highlight-color: transparent;
}
```

On empêche l'ajustement de la taille du texte sur iOS lors du changement d'orientation.

```css
html {
	-webkit-text-size-adjust: 100%;
}
```

On définit une taille de tabulations plus lisible.

```css
html {
	tab-size: 4;
	-moz-tab-size: 4;
}
```

&nbsp;

## Sections

### Reset

On supprime les marges pour les éléments `section`

```css
body, section, nav, article, aside,
h1, h2, h3, h4, h5, h6, header, footer, address {
	margin: 0;
	padding: 0;
}
```

&nbsp;

## Grouping content

### Améliorations ergonomiques

On empêche certains contenus de dépasser de leur contenant.

```css
blockquote,
pre {
	max-width: 100%;
}
```

On améliore la cohérence des polices par défaut pour tous les navigateurs.

```css
pre {
	font-family: ui-monospace, SFMono-Regular, Consolas, 'Liberation Mono', Menlo, monospace; 
}
```

### Reset

On enlève les puces des listes par défaut.

```css
ol, ul {
	list-style: none;
}
```

On supprime les marges pour les éléments `grouping content`

```css
p, hr, pre, blockquote, ol, ul, li, dl, dt, dd, figure, div {
	margin: 0;
	padding: 0;
}
```

&nbsp;

## Text-level semantics

### Normalisation

On définit la bonne valeur de `text-decoration` sur `abbr[title]` pour Chrome, Edge et Safari.

```css
abbr[title] {
	text-decoration: underline dotted;
}
```

On définit la bonne valeur de `font-weight` sur `b` et `strong` pour Chrome, Edge et Safari.

```css
b,
strong {
	font-weight: bolder;
}
```

On met la bonne valeur de `font-size` sur `small` pour Chrome, Edge et Safari.

```css
small {
	font-size: 80%;
}
```

On empêche les éléments `sub` et `sup` de changer l'interlignage de la ligne sur tous les navigateurs.

```css
sub,
sup {
	font-size: 75%;
	line-height: 0;
	position: relative;
	vertical-align: baseline;
}

sub {
	bottom: -0.25em;
}

sup {
	top: -0.5em;
}
```

### Améliorations ergonomiques

On supprime le délai de l'action "tapped" sur les éléments cliquables et on supprime les écarts sur le soulignement des liens.


```css
a {
	touch-action: manipulation;
	-webkit-text-decoration-skip: objects;
}
```

On met le curseur d'aide aux éléments qui donnent des informations supplémentaires sur `:hover`.


```css
abbr[title],
dfn[title] {
	cursor: help;
}
```

Afin que le texte ne dépasse pas de son bloc, on indique que les espaces doivent être conservées telles quelles et on empêche certains contenus de dépasser de leur contenant.


```css
code {
	white-space: pre-wrap; /* 1 */
	max-width: 100%; /* 2 */
}
```

On améliore la cohérence des polices par défaut pour tous les navigateurs.


```css
code,
kbd,
samp {
	font-family: ui-monospace, SFMono-Regular, Consolas, 'Liberation Mono', Menlo, monospace; 
}
```

### Reset

On enlève le `text-decoration` et l'`outline` des liens.


```css
a {
	outline: 0;
	text-decoration: none;
}
```

&nbsp;

## Embedded content

### Normalisation

On modifie la couleur de remplissage des éléments `svg` pour qu'elle corresponde à la couleur du texte dans sur les navigateurs.

```css
svg {
	fill: currentColor;
}
```

### Améliorations ergonomiques

On supprime le délai de l'action "tapped" sur les éléments cliquables.

```css
area {
	touch-action: manipulation;
}
```

On supprime l'écart entre les éléments `audio`, `canevas` , `iframes` , `images`, `vidéos` et le bas de leurs contenants.

```css
audio,
canvas,
iframe,
img,
svg,
video {
	vertical-align: middle;
}
```

On préserve le ratio largeur/hauteur des images.

```css
img {
	height: auto;
}
```

On enlève la surbrillance sur l'image lorsque l'on sélectionne et faisons glisser avec la souris.

```css
img::-moz-selection {
	background-color: transparent;
}

img::selection {
	background-color: transparent;
}
```

On empêche certains contenus de dépasser de leur contenant.

```css
img,
svg,
video {
	max-width: 100%;
}
```

### Reset

On supprime les marges pour certains éléments de embedded content.

```css
iframe, embed, object, param, video {
	margin: 0;
	padding: 0;
}
```

&nbsp;

## Tabular data

### Normalisation

On supprime l'indentation des `table` sur Chrome et Safari et on corrige l'héritage de la couleur des bordures sur Chrome et Safari.

```css
table {
	text-indent: 0;    
	border-color: inherit;
}
```

### Améliorations ergonomiques

On empêche certains contenus de dépasser de leur contenant.

```css
table,
td {
	max-width: 100%;
}
```

### Reset

On supprime les marges pour certains éléments de `tabular data`.

```css
table, caption, tr, td, th {
	margin: 0;
	padding: 0;
}
```

&nbsp;

## Forms

### Normalisation

On Corrige l'impossibilité de styliser les éléments cliquables dans iOS et Safari.

```css
button,
[type="button"],
[type="reset"],
[type="submit"] {
	-webkit-appearance: button;
}
```

On Corrige l'apparence dans Chrome et Safari et l'`outline` sur Safari.

```css
[type="search"] {
	-webkit-appearance: textfield;
	outline-offset: -2px;
}
```

On ajoute le bon alignement vertical pour Chrome et Firefox.

```css
progress {
	vertical-align: baseline;
}
```

On Corrige l'impossibilité de styliser les éléments cliquables dans iOS et Safari et on change les propriétés de la police en `inherit` pour Safari.

```css
::-webkit-file-upload-button {
	-webkit-appearance: button; 
	font: inherit;
}
```

On ajoute le bon alignement vertical pour Chrome et Firefox.

```css
::-webkit-inner-spin-button,
::-webkit-outer-spin-button {
	height: auto;
}
```

### Améliorations ergonomiques

On supprime le délai de l'action "tapped" sur les éléments cliquables.

```css
button,
input,
label,
select,
textarea {
	touch-action: manipulation;
}
```

On ajoute le style du curseur `pointer` aux éléments cliquables des formulaires.

```css
[type=button]:not(:disabled),
[type=reset]:not(:disabled),
[type=submit]:not(:disabled),
button:not(:disabled),
label[for],
select {
	cursor: pointer;
}
```

On empêche certains contenus de dépasser de leur contenant.

```css
input,
textarea {
	max-width: 100%;
}
```

On autorise uniquement le redimensionnement vertical des `textarea`.

```css
textarea {
	resize: vertical;
}
```

### Reset

On supprime l'héritage de `text-transform` pour Edge et Firefox.

```css
button,
select {
	text-transform: none;
}
```

On reset la typo sur certains éléments pour tous les navigateurs.

```css
button,
input,
optgroup,
select,
textarea {
	font-family: inherit;
	font-size: 100%;
}
```

On supprime le `padding` pour Safari dans macOS.

```css
[type="search"]::-webkit-search-decoration {
	-webkit-appearance: none;
}
```

On supprime les marges pour certains éléments de `forms`.

```css
form, button, input, label, select, textarea {
	margin: 0;
	padding: 0;
}
```

On supprime la bordure intérieure et la marge intérieur sur Firefox.

```css
::-moz-focus-inner {
	border-style: none;
	padding: 0;
}
```

On supprime les styles supplémentaires de `:invalid` sur Firefox.

```css
:-moz-ui-invalid {
	box-shadow: none;
}
```

&nbsp;

## Interactive

### Normalisation

On met le bon `display` pour l'élément `summary` sur Firefox.

```css
summary {
	display: list-item;
}
```

&nbsp;

## Contribuer

Pour contribuer, vous pouvez utiliser les trackers de problèmes du dépôt du module PWA Bunga! CSS

* [https://github.com/PwaBunga/css/issues](https://github.com/PwaBunga/css/issues)

Les modifications apportées sur ce seront ensuite effectuées sur le dépôt principal du projet.

Le tracker de problèmes est le canal privilégié pour signaler des bugs, des demandes de fonctionnalités et soumettre des requêtes de fusion, mais veuillez respecter les restrictions suivantes :

* Merci **de ne pas** utiliser le tracker de problèmes pour des demandes de support personnel.
* Merci **de ne pas** détourner ou saboter les problèmes. Maintenez la discussion sur le sujet et respectez les opinions des autres.

&nbsp;
