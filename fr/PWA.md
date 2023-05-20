* [Accueil de la documentation](https://github.com/PwaBunga/documentation/blob/main/fr/)
* [Documentation du module PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/fr/STARTER.md)
* [Documentation du module PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/fr/CSS.md)
* [Documentation du module PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/fr/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-pwa-circle.png" alt="logo PWA Bunga! PWA"/>
</div>

[English version](https://github.com/PwaBunga/documentation/blob/main/PWA.md)

# PWA Bunga! PWA

Une PWA (Progressive Web App) est une application web qui utilise les dernières technologies web pour offrir une expérience utilisateur similaire à celle d'une application native. Contrairement aux applications natives, les PWA ne nécessitent pas de téléchargement à partir d'un magasin d'applications et peuvent être utilisées directement à partir d'un navigateur web.

Elles sont conçues pour être fiables, rapides et engageantes, en permettant aux utilisateurs d'accéder à une version hors ligne de l'application, de recevoir des notifications push, de s'adapter à différentes tailles d'écran et de s'intégrer à d'autres fonctionnalités du système, telles que la caméra ou le microphone.

Les PWA ont une portée plus large que les applications natives car elles peuvent être utilisées sur différents types de périphériques (smartphones, tablettes, ordinateurs de bureau) et sur différents navigateurs web (Chrome, Firefox, Safari, etc.). Cela signifie que l'on peut créer une seule PWA qui fonctionnera pour tous les utilisateurs, au lieu de devoir créer plusieurs versions pour chaque plateforme ou système d'exploitation.

Elles ont aussi d'autres avantages comme le fait qu'elles soient applications web, ce qui signifie qu'elles sont accessibles via un navigateur et donc facilement indexables par les moteurs de recherche.

Les PWA sont de plus en plus populaires car elles offrent une alternative moins coûteuse et plus accessible aux applications natives, tout en offrant une expérience utilisateur de qualité similaire.

&nbsp;

## Contenu de PWA Bunga! PWA

Afin de mettre en place votre PWA, vous trouverez dans PWA Bunga! PWA :

* **Le fichier app.webmanifest** : Ce fichier contient les métadonnées de l'application, telles que son nom, sa description, son icône et sa couleur de thème. Il permet également à l'application d'être installée sur l'écran d'accueil de l'appareil.
* **Les fichiers d'icônes** : Il est important d'avoir des icônes de différentes tailles pour l'application, pour qu'elle puisse s'adapter à différents écrans et être installée sur l'écran d'accueil de l'appareil.
* **Le fichier serviceworker.js** : Il s'agit d'un script JavaScript qui fonctionne en arrière-plan et qui permet à l'application d'être disponible hors ligne. Le service worker peut mettre en cache des ressources pour une utilisation ultérieure, ce qui améliore la vitesse de chargement de l'application.
* **Le fichier pwabunga.js** : Ce fichier va permettre d'enregistrer le Service worker et fournir des fonctions permettant d'améliorer l'expérience utilisateur des évènements de la PWA.
* **Le fichier pwabunga-ui.css** : Un fichier CSS optionnel pour mettre en forme les éléments d'interface utilisateur utilisés par pwabunga.js.

&nbsp;

## Sommaire de la documentation de PWA Bunga! PWA

### [Webmanifest](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md)

* [Informations générales de la PWA](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#informations-générales-de-la-pwa)
  - [Nom](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#nom)
  - [Description](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#description)
  - [Langue](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#langue)
  - [Identifiant](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#identifiant)
* [Navigation de la PWA](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#navigation-de-la-pwa)
  - [URL de la page d'accueil](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#url-de-la-page-daccueil)
  - [Portée de la navigation](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#portée-de-la-navigation)
* [Thème de la PWA](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#thème-de-la-pwa)
  - [Mode d'affichage](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#mode-daffichage)
  - [Orientation](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#orientation)
  - [Couleur du thème](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#couleur-du-thème)
  - [Couleur de fond](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#couleur-de-fond)
  - [Icônes](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/WEBMANIFEST.md#icônes)

### [Icônes](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md)

* [Icônes et Touch icons pour les environnements applicatifs et les anciennes versions d'Android](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md#icônes-et-touch-icons-pour-les-environnements-applicatifs-et-les-anciennes-versions-dandroid)
  - [Affichage des icônes](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md#affichage-des-icônes)
  - [Dimensions des icônes](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md#dimensions-des-icônes)
  - [Appel des icônes](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md#appel-des-icônes)
* [Maskable icons : icônes adaptatives pour l'environnement Android](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md#maskable-icons--icônes-adaptatives-pour-lenvironnement-android)
  - [Zone de sécurité et formes des icônes adaptatives](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md#zone-de-sécurité-et-formes-des-icônes-adaptatives)
  - [Affichage des icônes adaptatives](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md#affichage-des-icônes-adaptatives)
  - [Appel des icônes adaptatives](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md#appel-des-icônes-adaptatives)
* [Touch icon pour l'environnement iOS](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md#appel-des-icônes-adaptatives)
  - [Formats et dimensions de apple-touch-icon.png](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/ICONES.md#formats-et-dimensions-de-apple-touch-iconpng)

### [Service worker](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md)

* [Configuration du cache et du traitement des requêtes](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#configuration-du-cache-et-du-traitement-des-requêtes)
  - [Nom et version du cache](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#nom-et-version-du-cache)
  - [Ressources mises en cache](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#ressources-mises-en-cache)
  - [Choix de la stratégie du traitement des requêtes](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#choix-de-la-stratégie-du-traitement-des-requêtes)
  - [Déclaration d'un dossier dynamique](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#déclaration-dun-dossier-dynamique)
* [Manipulation du cache](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#manipulation-du-cache)
  - [Ajout des ressources au cache](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#ajout-des-ressources-au-cache)
  - [Mise à jour des ressources du cache](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#mise-à-jour-des-ressources-du-cache)
  - [Suppression d'une instance de cache](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#suppression-dune-instance-de-cache)
  - [Suppression des anciennes versions du cache](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#suppression-des-anciennes-versions-du-cache)
* [Stratégies de traitement des requêtes](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#stratégies-de-traitement-des-requêtes)
  - [Cache only](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#cache-only)
  - [Network only](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#network-only)
  - [Cache first](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#cache-first)
  - [Network first](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#network-first)
  - [Stale While Revalidate](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#stale-while-revalidate)
* [Évènements du service worker](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#évènements-du-service-worker)
  - [Évènement install](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#évènement-install)
  - [Évènement activate](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#évènement-activate)
  - [Évènement message](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#évènement-activate)
  - [Évènement fetch](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/SERVICEWORKER.md#évènement-fetch)

### [pwabunga.js](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md)

* [Enregistrement du Service worker](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md#enregistrement-du-service-worker)
  - [Fonction pwaRegister](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/REGISTER.md)
* [Amélioration de l'expérience utilisateur](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md#am%C3%A9lioration-de-lexp%C3%A9rience-utilisateur)
  - [Fonction pwaInstall](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/INSTALL.md)
  - [Fonction pwaUpdate](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/UPDATE.md)
  - [Fonction pwaShare](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/SHARE.md)
  - [Fonction pwaParams](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/PARAMS.md)
* [Autorisations](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md#autorisations)
  - [Fonction pwaNotification](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/NOTIFICATION.md)
  - [Fonction pwaGeolocation](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/GEOLOCATION.md)

### [pwabunga-ui.css](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md)

* [Variables](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#variables)
* [Composants d'interface utilisateur de la PWA](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#composants-dinterface-utilisateur-de-la-pwa)
  - [Boutons](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#boutons)
  - [PWA Banner](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#pwa-banner)
  - [PWA Modal](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#pwa-modal)
  - [PWA Switch](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#pwa-switch)
  - [PWA Alert](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#pwa-alert)
  - [PWA Loader](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#pwa-loader)
* [Styles additionnels](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#styles-additionnels)
  - [Barre d'actions de la PWA](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#barre-dactions-de-la-pwa)
  - [Elément version de la fonction pwaParams()](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#elément-version-de-la-fonction-pwaparams)
  - [Listing des autorisations](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#listing-des-autorisations)
* [Etats des éléments utiles aux fonctions de pwabunga.js](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#etats-des-éléments-utiles-aux-fonctions-de-pwabungajs)
  - [Bouton d'installation de la fonction pwaInstall()](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#bouton-dinstallation-de-la-fonction-pwainstall)
  - [Bouton de partage de la fonction pwaShare()](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#bouton-de-partage-de-la-fonction-pwashare)
  - [Eléments de la fonction pwaParams()](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/CSS_UI.md#eléments-de-la-fonction-pwaparams)
  
&nbsp;

## Contribuer

Pour contribuer, vous pouvez utiliser les trackers de problèmes du dépôt du module PWA Bunga! PWA

* [https://github.com/PwaBunga/pwa/issues](https://github.com/PwaBunga/pwa/issues)

Les modifications apportées sur ce seront ensuite effectuées sur le dépôt principal du projet.

Le tracker de problèmes est le canal privilégié pour signaler des bugs, des demandes de fonctionnalités et soumettre des requêtes de fusion, mais veuillez respecter les restrictions suivantes :

* Merci **de ne pas** utiliser le tracker de problèmes pour des demandes de support personnel.
* Merci **de ne pas** détourner ou saboter les problèmes. Maintenez la discussion sur le sujet et respectez les opinions des autres.

&nbsp;

