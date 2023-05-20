* [Documentation homepage](https://github.com/PwaBunga/documentation/)
* [Documentation of the PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)
* [Documentation of the PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/CSS.md)
* [Documentation of the PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-css-circle.png" alt="logo PWA Bunga! CSS"/>
</div>

[French version](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md)

# PWA Bunga! CSS

pwabunga.css is the base CSS file for PWA Bunga!

&nbsp;

## PWA Bunga content! CSS

The PWA Bunga! CSS includes:

* From **standardization**
* **Ergonomic improvements**
* From **reset**
* **good practices** (To facilitate the task of the developer)

&nbsp;

* **`pwabunga.css`**

&nbsp;

## PWA Documentation Summary Bunga! CSS

* [Scrolling behavior](https://github.com/PwaBunga/documentation/blob/main/en/CSS.md#scrolling-behaviour)
   - [Ergonomic improvements](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#ergonomic-improvements)
* [Universal Inheritances](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#universal-inheritances)
   - [Good practices](https://github.com/PwaBunga/documentation/blob/main/en/CSS.md#good-practices)
* [Selection](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#selection)
   - [Reset](https://github.com/PwaBunga/documentation/blob/main/en/CSS.md#reset)
* [The root element](https://github.com/PwaBunga/documentation/blob/main/en/CSS.md#the-root-element)
   - [Best practices](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#bonnes-pratiques-1)
   - [Ergonomic improvements](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#ergonomic-improvements-1)
* [Sections](https://github.com/PwaBunga/documentation/blob/main/en/CSS.md#sections)
   - [Reset](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#reset-1)
* [Grouping content](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#grouping-content)
   - [Ergonomic improvements](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#ergonomic-improvements-2)
   - [Reset](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#reset-2)
* [Text-level semantics](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#text-level-semantics)
   - [Normalization](https://github.com/PwaBunga/documentation/blob/main/en/CSS.md#normalization)
   - [Ergonomic improvements](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#ergonomic-improvements-3)
   - [Reset](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#reset-3)
* [Embedded content](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#embedded-content)
   - [Normalization](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#normalization-1)
   - [Ergonomic improvements](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#ergonomic-improvements-4)
   - [Reset](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#reset-4)
* [Tabular data](https://github.com/PwaBunga/documentation/blob/main/en/CSS.md#tabular-data)
   - [Normalization](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#normalization-2)
   - [Ergonomic improvements](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#ergonomic-improvements-5)
   - [Reset](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#reset-5)
* [Forms](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#forms)
   - [Normalization](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#normalization-3)
   - [Ergonomic improvements](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#ergonomic-improvements-6)
   - [Reset](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#reset-6)
* [Interactive](https://github.com/PwaBunga/documentation/blob/main/en/CSS.md#interactive)
   - [Normalization](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md#normalization-4)

&nbsp;

## Scroll behavior

### Ergonomic improvements

If the user has not modified their settings to minimize the amount of animation or motion, we define a smooth scrolling effect for the scrolling behavior of a box, when scrolling occurs due to navigation or CSSOM scrolling APIs.

```css
@media (prefers-reduced-motion: no-preference) { 
	:root {
		scroll-behavior: smooth; 
	}
}
```

&nbsp;

## Universal inheritances

### Best practices

We make the `box-sizing` property inheritable for all elements.

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

We remove the `text-shadow` from the highlight of the selection.

```css
::-moz-selection {
	text-shadow: none; 
}

::selection {
	text-shadow: none;
}
```

&nbsp;

## The root element

### Best practices

We modify the box model sizing for the `html` element.

```css
html {
	box-sizing: border-box;
}
```

The relative unit of value refers to the size of the parent element. The default browser font size is 16 pixels. For a ratio of 1em/10px, we divide the size by the default size: 10/16 x 100 = 62.5%.

```css
html {
	font-size: 62.5%;
}
```

### Ergonomic improvements

We improve the consistency of default fonts across all browsers.

```css
html {
	font-family: system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji';
}
```

We force the browser scrollbar to always be visible to avoid jarring jumps between pages that have/not enough content.

```css
html {
	overflow-y: scroll;
}
```

We display the scroll bar with auto-hiding during mouse interactions and touch and keyboard interactions.

```css
html {
	-ms-overflow-style: -ms-autohiding-scrollbar;
}
```

We make fonts on OSX more consistent with other systems that do not use sub-pixel antialiasing.

```css
html {
	-moz-osx-font-smoothing: grayscale;
	-webkit-font-smoothing: antialiased;
}
```

We remove the highlight effect on the 'tapped' action.

```css
html {
	-webkit-tap-highlight-color: rgba(0,0,0,0);
	-webkit-tap-highlight-color: transparent;
}
```

We prevent text size adjustment on iOS when changing orientation.

```css
html {
	-webkit-text-size-adjust: 100%;
}
```

We define a more readable tab size.

```css
html {
	tab-size: 4;
	-moz-tab-size: 4;
}
```

&nbsp;

## Sections

### Reset

We remove margins for `section` elements

```css
body, section, nav, article, aside,
h1, h2, h3, h4, h5, h6, header, footer, address {
	margin: 0;
	padding: 0;
}
```

&nbsp;

## Grouping content

### Ergonomic improvements

We prevent some content from overflowing their container.

```css
blockquote,
pre {
	max-width: 100%;
}
```

We improve the consistency of default fonts across all browsers.

```css
pre {
	font-family: ui-monospace, SFMono-Regular, Consolas, 'Liberation Mono', Menlo, monospace; 
}
```

### Reset

We remove the default bullets from lists.

```css
ol, ul {
	list-style: none;
}
```

We remove the margins for `grouping content` elements.

```css
p, hr, pre, blockquote, ol, ul, li, dl, dt, dd, figure, div {
	margin: 0;
	padding: 0;
}
```

&nbsp;

## Text-level semantics

### Normalization

We set the appropriate `text-decoration` value on `abbr[title]` for Chrome, Edge, and Safari.

```css
abbr[title] {
	text-decoration: underline dotted;
}
```

We set the correct `font-weight` value for `b` and `strong` elements in Chrome, Edge, and Safari.

```css
b,
strong {
	font-weight: bolder;
}
```

We set the correct `font-size` value for `small` on Chrome, Edge, and Safari.

```css
small {
	font-size: 80%;
}
```

We prevent the `sub` and `sup` elements from changing the line height of the text on all browsers.

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

### Ergonomic improvements

We remove the delay on the "tapped" action for clickable elements and remove the gaps on link underlines.

```css
a {
	touch-action: manipulation;
	-webkit-text-decoration-skip: objects;
}
```

We set the help cursor on elements that provide additional information on `:hover`.

```css
abbr[title],
dfn[title] {
	cursor: help;
}
```

To prevent text from overflowing its block, we indicate that spaces should be preserved as they are and we prevent certain content from exceeding its container.

```css
code {
	white-space: pre-wrap; /* 1 */
	max-width: 100%; /* 2 */
}
```

We improve the consistency of default fonts across all browsers.


```css
code,
kbd,
samp {
	font-family: ui-monospace, SFMono-Regular, Consolas, 'Liberation Mono', Menlo, monospace; 
}
```

### Reset

We remove the `text-decoration` and `outline` from links.

```css
a {
	outline: 0;
	text-decoration: none;
}
```

&nbsp;

## Embedded content

### Normalization

We change the fill color of `svg` elements to match the text color on browsers.

```css
svg {
	fill: currentColor;
}
```

### Ergonomic improvements

We remove the delay on the "tapped" action on clickable elements

```css
area {
	touch-action: manipulation;
}
```

We remove the gap between `audio`, `canevas`, `iframes`, `images`, `videos` elements and the bottom of their containers.

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

We preserve the aspect ratio (width/height ratio) of images.

```css
img {
	height: auto;
}
```

We remove the highlight on the image when selecting and dragging with the mouse.

```css
img::-moz-selection {
	background-color: transparent;
}

img::selection {
	background-color: transparent;
}
```

To prevent some contents from overflowing their container.

```css
img,
svg,
video {
	max-width: 100%;
}
```

### Reset

We remove margins for certain embedded content elements.

```css
iframe, embed, object, param, video {
	margin: 0;
	padding: 0;
}
```

## Tabular data

### Normalization

Remove indentation for `table` on Chrome and Safari and fix border color inheritance on Chrome and Safari.

```css
table {
	text-indent: 0;    
	border-color: inherit;
}
```

### Ergonomic improvements

We prevent certain content from overflowing their container.

```css
table,
td {
	max-width: 100%;
}
```

### Reset

We remove the margins for certain elements of `tabular data`.

```css
table, caption, tr, td, th {
	margin: 0;
	padding: 0;
}
```

&nbsp;

## Forms

### Normalization

We fix the inability to style clickable elements in iOS and Safari.

```css
button,
[type="button"],
[type="reset"],
[type="submit"] {
	-webkit-appearance: button;
}
```

We fix the appearance in Chrome and Safari and the `outline` on Safari.

```css
[type="search"] {
	-webkit-appearance: textfield;
	outline-offset: -2px;
}
```

We add the correct vertical alignment for Chrome and Firefox.

```css
progress {
	vertical-align: baseline;
}
```

We fix the inability to style clickable elements in iOS and Safari, and change the font properties to `inherit` for Safari.

```css
::-webkit-file-upload-button {
	-webkit-appearance: button; 
	font: inherit;
}
```

We add the correct vertical alignment for Chrome and Firefox.

```css
::-webkit-inner-spin-button,
::-webkit-outer-spin-button {
	height: auto;
}
```

### Ergonomic improvements

We remove the delay of the "tapped" action on clickable elements.

```css
button,
input,
label,
select,
textarea {
	touch-action: manipulation;
}
```

We add the `pointer` cursor style to clickable elements in forms.

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

We prevent certain content from overflowing their container.

```css
input,
textarea {
	max-width: 100%;
}
```

We only allow vertical resizing of `textarea`.

```css
textarea {
	resize: vertical;
}
```

### Reset

Remove `text-transform` inheritance for Edge and Firefox.

```css
button,
select {
	text-transform: none;
}
```

We reset the typo on certain elements for all browsers.

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

We remove the `padding` for Safari in macOS.

```css
[type="search"]::-webkit-search-decoration {
	-webkit-appearance: none;
}
```

We remove the margins for some elements of `forms`.

```css
form, button, input, label, select, textarea {
	margin: 0;
	padding: 0;
}
```

We remove the interior border and the interior margin on Firefox.

```css
::-moz-focus-inner {
	border-style: none;
	padding: 0;
}
```

Remove extra styles from `:invalid` on Firefox.

```css
:-moz-ui-invalid {
	box-shadow: none;
}
```

&nbsp;

## Interactive

### Normalization

We put the correct `display` for the `summary` element on Firefox.

```css
summary {
	display: list-item;
}
```

&nbsp;

## Contribute

To contribute, you can use the issue trackers of the PWA Bunga! Starter module repository.

* [https://github.com/PwaBunga/css/issues](https://github.com/PwaBunga/css/issues)

The modifications made on this repository will then be made on the main repository of the project.

The issue tracker is the preferred channel for bug reports, features requests and submitting pull requests, but please respect the following restrictions:

* Please **do not** use the issue tracker for personal support requests.
* Please **do not** derail or troll issues. Keep the discussion on topic and= respect the opinions of others.

&nbsp;