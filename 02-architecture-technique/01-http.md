Comment utiliser le service $http ?
===================================

La gestion d'erreur est gérée au maximum par un intercepteur.
Le développeur se voit déchargé d'un ensemble de tâches de gestion d'erreur.
Son travail sera centré alors sur le caractére fonctionnel de son code.

Mise en oeuvre
--------------

L'implémentation repose sur un intercepteur (cf. ```app/common/utils/interceptor.js```).

Tous ce que le développeur doit savoir est d'appeler ```$http``` avec un objet de configuration
qui peut être surchagé.

L'intercepteur redirige sur une page d'erreur technique si erreur.
L'intercepteur redirige sur la page d'authentification si nécessaire.

Il existe actuellement deux propriétés spécifiques : 

- ```toBeIntercepted``` : si cet attribut est présent et valué à false, alors l'intercepteur 
est ignoré.
- ```jsonExpected``` : si cet attribut est présent et valué à true, alors l'intercepteur vérifie
que les données reçues sont au format json.

Exemples
--------

```javascript
var config = {
    method: 'GET',
    url: 'test.html',
    toBeIntercepted: false
};

$http(config)
	.success(function(data, status, headers, config) { 
		...
	})
	.error(function(data, status, headers, config) {
		...
	});
};
```

```javascript
var config = {
    method: 'GET',
    url: 'test.html',
    jsonExpected: true
};

$http(config)
	.success(function(data, status, headers, config) { 
		...
	})
	.error(function(data, status, headers, config) {
		...
	});
};
```
