Http Fake
=========

Le service $http peut être modifié (comme n'importe quel service Angular)
à l'aide du mécanisme de décorateur.
Un module httpFake.js a été écrit pour l'occasion.

Mise en oeuvre
--------------

- Inclure le fichier javascript dans le fichier HTML :
```javascript
<script type="text/javascript" src="fakeHttp.js"></script>
```

- Inclure le module `fakeHttp` :
```javascript
var app = angular.module('mainApp', [ 'fakeHttp' ]); 
```

- Configurer le service $http pour qu'il renvoit ce que l'on veut.

```javascript
window.fakeHttp = [ {
	key: function(config) {
		return config.url.match(new RegExp('http://bot.whatismyipaddress..*/'));
	},
	value: function(config) {
		console.log('config = ', config);
		return {
			data: '91.35.249.115',
			headers: function() {
				return 'headers not implemented';
			}
		};
	}
} ];
```



