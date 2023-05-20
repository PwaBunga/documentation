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

[English version](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md)

# PWA Bunga! PWA Service Worker

Les service workers sont des scripts JavaScript qui s'exécutent en arrière-plan de votre application web et qui permettent d'ajouter des fonctionnalités avancées à celle-ci. Ils agissent comme des intermédiaires entre l'application web, le navigateur et le réseau, leur permettant de contrôler les requêtes entrantes et sortantes et de gérer la mise en cache des ressources.

Les service workers permettent notamment de stocker des fichiers tels que des images, des scripts et des feuilles de style CSS localement sur l'appareil de l'utilisateur, ce qui améliore considérablement les performances de l'application en réduisant les temps de chargement des pages et en permettant une utilisation hors ligne de l'application.

Les service workers peuvent également gérer les notifications push, synchroniser des données en arrière-plan, mettre à jour automatiquement l'application et bien d'autres fonctionnalités encore. Ils offrent ainsi une expérience utilisateur améliorée et permettent aux applications web de rivaliser avec les applications mobiles natives.

En somme, les service workers sont un élément clé des Progressive Web Apps, offrant une expérience utilisateur rapide, fiable et engageante, même lorsque l'utilisateur est hors ligne ou dans des conditions de réseau difficiles.

Le fichier `serviceworker.js` de PWA Bunga! va permettre :

* De **mettre en cache les ressources** statiques afin de **permettre la consultation hors ligne**.
* De définir la **stratégie du traitement des requêtes**.
* D'**agir sur les différents états du service worker**.

![](https://www.pwabunga.com/assets/images/pwa-service-worker-overview.png)

&nbsp;

* **`serviceworker.js`**

*Les exemples donnés dans cette partie ont été réalisés avec un Google Pixel 5 sous Android 13.*

&nbsp;

## Configuration du cache et du traitement des requêtes

Le fichier `serviceworker.js` de PWA Bunga! contient des variables permettant de rapidement configurer le système de cache et la stratégie de traitement des requêtes.

### Nom et version du cache

La constante `cacheTitle` est une variable qui doit être définie dans votre application web afin de stocker le nom de votre application. Elle est utilisée pour identifier les fichiers en cache associés à votre application. Le nom de l'application doit être unique et descriptif pour éviter toute confusion avec d'autres applications.

```js
const cacheTitle = 'yourAppName'
```

La constante `cacheVersion` est une variable qui doit être définie dans votre application web afin de stocker le numéro de version de votre application. Elle est utilisée pour identifier les différents ensembles de fichiers en cache associés à différentes versions de l'application. Il est important de mettre à jour cette valeur chaque fois que vous publiez une nouvelle version de votre application pour vous assurer que les utilisateurs ont la dernière version.

```js
const cacheVersion = 'v1.0'
```

La constante `cacheName` est une variable qui combine les valeurs de "cacheTitle" et "cacheVersion" pour former un nom de cache unique pour votre application. Elle est utilisée pour créer un cache pour votre application et stocker les fichiers associés à cette version de l'application.

```js
const cacheName = cacheTitle + '-' + cacheVersion
```

### Ressources mises en cache

La constante `contentToCache` est une variable qui doit être définie dans votre application web afin de stocker une liste de fichiers à mettre en cache pour une utilisation hors ligne. Les fichiers peuvent inclure des pages, des images, des styles CSS, des scripts JavaScript, des icônes et d'autres éléments nécessaires pour que l'application fonctionne correctement lorsqu'elle est hors ligne.

```js
const contentToCache = [
	// - Pages
	'/',
	'index.html',
	// - Favicons
	'favicon.ico',
	'favicon.svg',
	// 'favicon-16.png',
	// 'favicon-32.png',
	// - CSS
	'assets/css/pwabunga.css',
	'assets/css/styles.css',
	// - JS
	'assets/js/scripts.js',
	// - PWA
	'pwa/css/pwabunga-ui.css',
	'pwa/icons/apple-touch-icon.png',
	'pwa/icons/icon-192.png',
	'pwa/icons/icon-512.png',
	'pwa/icons/icon-maskable-192.png',
	'pwa/icons/icon-maskable-512.png',
	'pwa/js/pwabunga.js',
	'pwa/app.webmanifest'
]
```

### Choix de la stratégie du traitement des requêtes

La constante `requestProcessingMethod` est une variable qui doit être définie dans votre application web afin de déterminer la stratégie à utiliser pour traiter les requêtes de réseau. Elle peut prendre l'une des valeurs suivantes : 'cacheOnly', 'networkOnly', 'cacheFirst', 'networkFirst' ou 'staleWhileRevalidate'. Chaque valeur correspond à une stratégie différente pour répondre aux requêtes de réseau et pour gérer le contenu mis en cache.

* `cacheOnly` : Si cette valeur est utilisée, les requêtes seront traitées à partir du cache uniquement. Si le contenu n'est pas disponible dans le cache, la requête échouera.
* `cacheOnly` : Si cette valeur est utilisée, les requêtes seront traitées à partir du réseau uniquement. Si le réseau est inaccessible, la requête échouera.
* `cacheFirst` : Si cette valeur est utilisée, les requêtes seront traitées à partir du cache en premier lieu. Si le contenu n'est pas disponible dans le cache, l a requête sera envoyée au réseau. Si le réseau n'est pas disponible, la requête échouera.
* `networkFirst` : Si cette valeur est utilisée, les requêtes seront traitées à partir du réseau en premier lieu. Si le réseau est inaccessible, la requête sera envoyée au cache. Si le contenu n'est pas disponible dans le cache, la requête échouera.
* `staleWhileRevalidate` : Si cette valeur est utilisée, les requêtes seront traitées à partir du cache. Le contenu du cache sera retourné immédiatement, même s'il est expiré. Une requête sera envoyée au réseau pour récupérer la dernière version du contenu, qui sera ensuite mise en cache pour les prochaines requêtes.

```js
const requestProcessingMethod = 'cacheFirst'
```

### Déclaration d'un dossier dynamique

La constante `dynamicFolder` est une variable qui peut être utilisée dans votre application web pour définir le chemin d'un dossier dynamique qui ne doit pas être mis en cache. Cette variable est utilisée en conjonction avec la stratégie "networkOnly" pour s'assurer que les requêtes vers ce dossier sont toujours traitées à partir du réseau et jamais mises en cache.

Lorsque cette variable est définie, toutes les requêtes qui commencent par le chemin défini seront considérées comme des requêtes "networkOnly". Cela signifie que ces requêtes seront toujours envoyées au réseau pour être traitées et que le contenu ne sera jamais mis en cache.

```js
const dynamicFolder = '/api/'
```

## Manipulation du cache

Afin d'agir sur le cache, nous utilisons les fonctions suivantes :

### Ajout des ressources au cache

La fonction `addResourcesToCache` est une fonction asynchrone qui peut être utilisée dans votre application web pour ajouter des ressources dans le cache. Cette fonction prend un seul paramètre, `resources`, qui doit être un tableau contenant une liste de toutes les ressources que vous souhaitez ajouter au cache.

#### Explications

Ouvre une instance du cache de l'application en utilisant la méthode `open()` de l'API CacheStorage, avec la variable `cacheName` en paramètre.

```js
const cache = await caches.open(cacheName)
```

Utilise la méthode `addAll()` pour mettre dans le cache de l'application les ressources

```js
await cache.addAll(resources)
```

#### Fonction complète

Notez que cette fonction est asynchrone, ce qui signifie qu'elle peut être utilisée avec l'opérateur `await` pour attendre que toutes les ressources soient ajoutées dans le cache avant de continuer l'exécution du code.

```js
const addResourcesToCache = async (resources) => {
	const cache = await caches.open(cacheName)
	await cache.addAll(resources)
}
```

### Mise à jour des ressources du cache

La fonction `putInCache` est une fonction asynchrone qui peut être utilisée dans votre application web pour mettre en cache une requête et sa réponse. Cette fonction prend deux paramètres, `request` et `response`, qui représentent respectivement la requête et la réponse que vous souhaitez mettre en cache.

#### Explications

Ouvre l'instance du cache de l'application

```js
const cache = await caches.open(cacheName)
```

Utilise la méthode `put()` pour ajouter ou remplacer dans le cache de l'application la ressource.

```js
await cache.put(request, response)
```

#### Fonction complète

Notez que cette fonction est asynchrone, ce qui signifie qu'elle peut être utilisée avec l'opérateur `await` pour attendre que la mise en cache soit terminée avant de continuer l'exécution du code.

```js
const putInCache = async (request, response) => {
	const cache = await caches.open(cacheName)
	await cache.put(request, response)
}
```

### Suppression d'une instance de cache

La fonction `deleteCache` est une fonction asynchrone qui peut être utilisée dans votre application web pour supprimer un cache spécifique en utilisant sa clé.

#### Explications

Utilise la méthode `delete()` avec le paramètre `key`, l'entrée du cache à supprimer.

```js
await caches.delete(key)
```

#### Fonction complète

Notez que cette fonction est asynchrone, ce qui signifie qu'elle peut être utilisée avec l'opérateur `await` pour attendre que la suppression soit terminée avant de continuer l'exécution du code.

```js
const deleteCache = async (key) => {
	await caches.delete(key)
}
```

### Suppression des anciennes versions du cache

La fonction `deleteOldCaches` est une fonction asynchrone qui peut être utilisée dans votre application web pour supprimer tous les caches qui ne sont pas nécessaires à votre application

#### Explications

Récupère l'instance de la version du cache à conserver

```js
const cacheKeepList = [cacheName]
```

Récupère les différentes instances de cache disponibles

```js
const keyList = await caches.keys()
```

Enlève à la variable précédente l'instance de la version du cache de l'application à conserver

```js
const cachesToDelete = keyList.filter((key) => !cacheKeepList.includes(key))
```

Supprime les anciennes versions du cache de l'application en utilisant la fonction `deleteCache`

```js
await Promise.all(cachesToDelete.map(deleteCache))
```

#### Fonction complète

Notez que cette fonction est asynchrone, ce qui signifie qu'elle peut être utilisée avec l'opérateur `await` pour attendre que la suppression soit terminée avant de continuer l'exécution du code.

```js
const deleteOldCaches = async () => {
	const cacheKeepList = [cacheName]
	const keyList = await caches.keys()
	const cachesToDelete = keyList.filter((key) => !cacheKeepList.includes(key))
	await Promise.all(cachesToDelete.map(deleteCache))
}
```

## Stratégies de traitement des requêtes

### Cache only

La fonction `cacheOnly` est une fonction asynchrone qui peut être utilisée dans votre service worker pour répondre aux requêtes en utilisant le cache uniquement.

![](https://www.pwabunga.com/assets/images/pwa-service-worker-cacheonly.png)

#### Explications

Teste si la requête à une correspondance dans le cache de l'application avec la méthode `.match()`.

```js
const responseFromCache = await caches.match(request)]
```

S'il y a une correspondance, renvoie la réponse provenant du cache

```js
if (responseFromCache) {
	return responseFromCache
}
```

Sinon, renvoie une réponse 404 avec un message d'erreur en texte brut

```js
else {
	return new Response("Cache error happened", {
		status: 404,
		headers: { "Content-Type": "text/plain" },
	})
}
```

#### Fonction complète

Notez que cette fonction est asynchrone, ce qui signifie qu'elle peut être utilisée avec l'opérateur `await` pour attendre que la suppression soit terminée avant de continuer l'exécution du code.

```js
const cacheOnly = async ({ request }) => {
	const responseFromCache = await caches.match(request)
	if (responseFromCache) {
		return responseFromCache
	} else {
		return new Response("Cache error happened", {
			status: 404,
			headers: { "Content-Type": "text/plain" }
		})
	}
}
```

### Network only

La fonction `networkOnly` est une fonction asynchrone qui prend un objet en paramètre qui contient une requête à traiter. Elle essaie d'abord de récupérer la ressource demandée à partir du réseau. Si la requête réseau réussit, elle renvoie la réponse. Si la requête réseau échoue, elle renvoie une réponse 408 avec un message d'erreur.

![](https://www.pwabunga.com/assets/images/pwa-service-worker-networkonly.png)

#### Explications

Teste si la requête trouve une réponse sur le serveur avec la méthode `.fetch()`.

```js
const responseFromNetwork = await fetch(request)
```

S'il y a une correspondance, renvoie la réponse provenant du serveur

```js
return responseFromNetwork
```

Sinon, renvoie une réponse 408 (Request Timeout) avec un message d'erreur "Network error happened"

```js
catch (error) {
	return new Response("Network error happened", {
		status: 408,
		headers: { "Content-Type": "text/plain" }
	})
}
```

#### Fonction complète

Notez que cette fonction est asynchrone, ce qui signifie qu'elle peut être utilisée avec l'opérateur `await` pour attendre que la suppression soit terminée avant de continuer l'exécution du code.

```js
const networkOnly = async ({ request }) => {
	try {
		const responseFromNetwork = await fetch(request)
		return responseFromNetwork
	} catch (error) {
		return new Response("Network error happened", {
			status: 408,
			headers: { "Content-Type": "text/plain" }
		})
	}
}
```

### Cache first

La fonction `cacheFirst` est une fonction asynchrone qui peut être utilisée dans une application web pour améliorer les performances en réduisant le temps de réponse et le nombre de requêtes réseau. Cette fonction suit une stratégie de mise en cache qui consiste à chercher en premier la réponse dans le cache avant de faire appel au réseau.

![](https://www.pwabunga.com/assets/images/pwa-service-worker-cachefirst.png)

#### Explications

Si l'URL de la requête contient le dossier dynamique (`dynamicFolder`)

```js
if (request.url.includes(dynamicFolder)) {
```

renvoie la réponse provenant du serveur

```js
return fetch(request);
```

Teste si la requête à une correspondance dans le cache de l'application avec la méthode `.match()`

```js
const responseFromCache = await caches.match(request)
```

S'il y a une correspondance, renvoie la réponse provenant du cache

```js
if (responseFromCache) {
	return responseFromCache
}
```

Sinon, teste si la requête a une correspondance sur le serveur

```js
const responseFromNetwork = await fetch(request)
```

Si elle en a une, met à jour le cache de l'application en y ajoutant la nouvelle ressource avec la fonction `putInCache`

```js
putInCache(request, responseFromNetwork.clone())
```

Et renvoie la réponse provenant du serveur

```js
return responseFromNetwork
```

Sinon, renvoie une réponse 408 (Request Timeout) avec un message d'erreur "Network error happened"

```js
catch (error) {
	return new Response("Network error happened", {
		status: 408,
		headers: { "Content-Type": "text/plain" }
	})
}
```

#### Fonction complète

Notez que cette fonction est asynchrone, ce qui signifie qu'elle peut être utilisée avec l'opérateur `await` pour attendre que la suppression soit terminée avant de continuer l'exécution du code.

```js
const cacheFirst = async ({ request }) => {
	if (request.url.includes(dynamicFolder)) {
		return fetch(request);
	}
	const responseFromCache = await caches.match(request)
	if (responseFromCache) {
		return responseFromCache
	}
	try {
		const responseFromNetwork = await fetch(request)
		putInCache(request, responseFromNetwork.clone())
		return responseFromNetwork;
	} catch (error) {
		return new Response("Network error happened", {
			status: 408,
			headers: { "Content-Type": "text/plain" },
		})
	}
}
```

### Network first

La fonction `networkFirst` est une fonction asynchrone qui peut être utilisée dans votre application web pour récupérer une ressource depuis le réseau. Si la récupération à partir du réseau échoue, elle tente de récupérer la réponse depuis le cache.

![](https://www.pwabunga.com/assets/images/pwa-service-worker-networkfirst.png)

#### Explications

Teste si la requête a une correspondance sur le serveur

```js
const responseFromNetwork = await fetch(request)
```

si elle en a une, met à jour le cache de l'application en y ajoutant ou en remplaçant la ressource avec la fonction `putInCache`

```js
putInCache(request, responseFromNetwork.clone())
```

Et renvoie la réponse provenant du serveur

```js
return responseFromNetwork
```

Sinon, teste si la requête à une correspondance dans le cache de l'application avec la méthode `.match()`

```js
const responseFromCache = await caches.match(request)
```

S'il y a une correspondance, renvoie la réponse provenant du cache

```js
if (responseFromCache) {
	return responseFromCache
}
```

Sinon, renvoie une réponse 408 (Request Timeout) avec un message d'erreur "Network error happened"

```js
catch (error) {
	return new Response("Network error happened", {
		status: 408,
		headers: { "Content-Type": "text/plain" }
	})
}
```

#### Fonction complète

Notez que cette fonction est asynchrone, ce qui signifie qu'elle peut être utilisée avec l'opérateur `await` pour attendre que la suppression soit terminée avant de continuer l'exécution du code.

```js
const networkFirst = async ({ request }) => {
	try {
		const responseFromNetwork = await fetch(request)
		putInCache(request, responseFromNetwork.clone())
		return responseFromNetwork;
	} catch (error) {
		const responseFromCache = await caches.match(request)
		if (responseFromCache) {
			return responseFromCache
		}
		return new Response("Network error happened", {
			status: 408,
			headers: { "Content-Type": "text/plain" }
		})
	}
}
```

### Stale While Revalidate

La fonction `staleWhileRevalidate` est une fonction asynchrone qui peut être utilisée pour améliorer les performances des applications Web en fournissant une réponse rapide à un utilisateur tout en mettant à jour la version du cache en arrière-plan.

![](https://www.pwabunga.com/assets/images/pwa-service-worker-stale.png)

#### Explications

Ouvre l'instance du cache de l'application en utilisant la méthode `open()` de l'API CacheStorage

```js
const cache = await caches.open(cacheName)
```

Teste si la requête à une correspondance dans le cache de l'application avec la méthode .match()

```js
const responseFromCache = await caches.match(request)]
```

Teste si la requête trouve une réponse sur le serveur avec la méthode .fetch()

```js
const responseFromNetwork = fetch(request)
```

Si la requête a une correspondance dans le cache

```js
if (responseFromCache) {
```

Crée une copie de la réponse trouvée dans le cache pour que la réponse originale ne soit pas modifiée

```js
const responseClone = responseFromCache.clone()
```

Récupère la réponse du réseau

```js
responseFromNetwork.then(response => {
```

Ajoute la réponse récupérée depuis le réseau dans le cache

```js
cache.put(request, response.clone())
```

Renvoie la copie de la réponse du cache pour terminer l'exécution de la fonction

```js
return responseClone
```

Essaie d'exécuter une requête réseau en utilisant la méthode fetch() de l'API Web

```js
try {
	const response = await responseFromNetwork
```

Ajoute la réponse récupérée depuis le réseau dans le cache

```js
cache.put(request, response.clone())
```

Renvoie la réponse récupérée depuis le réseau pour terminer l'exécution de la fonction.

```js
return response
```

Sinon, renvoie une réponse 408 (Request Timeout) avec un message d'erreur "Network error happened"

```js
return new Response("Network error happened", {
	status: 408,
	headers: { "Content-Type": "text/plain" }
})
```

#### Fonction complète

Notez que cette fonction est asynchrone, ce qui signifie qu'elle peut être utilisée avec l'opérateur `await` pour attendre que la suppression soit terminée avant de continuer l'exécution du code.

```js
const staleWhileRevalidate = async ({ request }) => {
	const cache = await caches.open(cacheName)
	const responseFromCache = await caches.match(request)
	const responseFromNetwork = fetch(request)
	if (responseFromCache) {
		const responseClone = responseFromCache.clone()
		responseFromNetwork.then(response => {
			cache.put(request, response.clone())
		})
		return responseClone
	} 
	try {
		const response = await responseFromNetwork
		cache.put(request, response.clone())
		return response
	} catch (error) {
		return new Response('Network error occurred.', {
			status: 408,
			headers: { 'Content-Type': 'text/plain' }
		})
	}
}
```

## Évènements du service worker

### Évènement install

Cet évènement correspond à la phase d'installation du service worker.

```js
self.addEventListener('install', (event) => {
	console.log(cacheName + ' Installation')
})
```

#### Mise en cache des ressources statiques

C'est au moment de l'évènement install que l'on va créer l'instance du cache de l'application avec les ressources statiques avec à la fonction `addResourcesToCache`. La fonction utilise la méthode `waitUntil` de l'objet event pour attendre que toutes les ressources soient ajoutées au cache.

```js
event.waitUntil(
	addResourcesToCache(contentToCache)
)
```

#### Évènement complet

```js
self.addEventListener('install', (event) => {
	console.log(cacheName + ' Installation')
	event.waitUntil(
		addResourcesToCache(contentToCache)
	)
})
```

### Évènement activate

L'évènement `activate` est émis lorsque le service worker est téléchargé et exécuté par le navigateur, et qu'il est activé.

```js
self.addEventListener('activate', (event) => {
})
```

#### Suppression des instances de cache de l'application des aniciennes versions

C'est pendant cette évènement que l'on va demander au service worker d'exécuter la fonction `deleteOldCaches()`, afin de supprimer l'instance du cache de l'ancienne version du service worker lors de l'activation de la nouvelle version

```js
event.waitUntil(
	deleteOldCaches()
)
```

#### Évènement complet

```js
self.addEventListener('activate', (event) => {
	event.waitUntil(
		deleteOldCaches()
	)
})
```

### Évènement message

L'évènement `message` va être utilisé ici pour recevoir les messages via l'API Message, qui permet aux scripts de différents contextes (comme un service worker et une fenêtre de navigateur) de communiquer entre eux en envoyant des messages.

```js
self.addEventListener('message', (event) => {
})
```

#### Exécution de la mise à jour du service worker

Quand le Service worker reçoit le message indiquant que l'utilisateur a demandé d'effectuer la mise à jour (voir la fonction [fonction pwaUpdate()](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/UPDATE.md) du fichier [pwabunga.js](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md))

```js
if (event.data === 'SKIP_WAITING') {
```

Le Service worker exécute la mise à jour en activant le nouveau service worker

```js
self.skipWaiting()
```

#### Envoi de la version de la PWA

Quand le Service worker reçoit le message indiquant que l'on souhaite afficher la version de la PWA (voir la [fonction pwaParams()](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/js/PARAMS.md) du fichier [pwabunga.js](https://github.com/PwaBunga/documentation/blob/main/fr/pwa/JS.md))

```js
if (event.data === 'GET_VERSION') {
```

Pour tous les clients associés au service worker

```js
self.clients.matchAll().then(function(clients) {
	clients.forEach(function(client) {
```

Envoie le message contenant la variable de la version de la PWA

```js
client.postMessage(cacheVersion)
```

#### Évènement complet

```js
self.addEventListener('message', (event) => {
	if (event.data === 'SKIP_WAITING') {
		self.skipWaiting()
	}
	if (event.data === 'GET_VERSION') {
	self.clients.matchAll().then(function(clients) {
		clients.forEach(function(client) {
		client.postMessage(cacheVersion)
		})
	})
	}
})
```

### Évènement fetch

L'évènement fetch permet de gérer les requêtes HTTP provenant de l'application cliente. Il est utilisé pour récupérer des ressources depuis le réseau ou le cache, selon la configuration de l'application

```js
self.addEventListener('fetch', (event) => {
})
```

#### Récupération de la requête

Récupère l'objet request depuis l'événement fetch

```js
const request = event.request
```

#### Gestion des requêtes

Définit un objet methods contenant les méthodes de traitement de requêtes possibles

```js
const methods = {
	'cacheOnly': cacheOnly,
	'networkOnly': networkOnly,
	'cacheFirst': cacheFirst,
	'networkFirst': networkFirst,
	'staleWhileRevalidate': staleWhileRevalidate
}
```

Récupère la méthode de traitement de requête correspondante à la méthode de la requête choisie dans la constante requestProcessingMethod

```js
const method = methods[requestProcessingMethod]
```

Si une méthode de traitement de requête existe pour la méthode courante, elle l'utilise pour gérer la requête

```js
if (method) {
	event.respondWith(method({request}))
}
```

#### Évènement complet

```js
self.addEventListener('fetch', (event) => {
	const request = event.request
	const methods = {
		'cacheOnly': cacheOnly,
		'networkOnly': networkOnly,
		'cacheFirst': cacheFirst,
		'networkFirst': networkFirst,
		'staleWhileRevalidate': staleWhileRevalidate
	}
	const method = methods[requestProcessingMethod]
	if (method) {
		event.respondWith(method({request}))
	}
})
```