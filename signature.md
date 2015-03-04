signature
=========

- Les fonctions ne doivent pas contenir trop d'arguments car cela rend le code trop illisible.
- On s'autorise donc maximum 3 arguments.

Si on doit utiliser plus de 3 arguments on applique l'une des techniques suivantes :

- Mettre les arguments dans un objet.
- S'il s'agit d'injections dans AngularJS, recourir au service ```$injector```.

Exemple 1
---------

```javascript
function xyz(a, b, c, d, e) {...}
```
devient :
```javascript
function xyz(obj) {}
```
avec
```javascript
obj = {
	a: a,
	b: b,
	c: c,
	d: d,
	e: e
};
```

Exemple 2
---------
```javascript
app.controller('authentication.MainCtrl', [ '$scope', '$log', '$location', '$rootScope', '$window', function($scope, $log, $location, $rootScope, $window) {
	...
}]);
```
devient :
```javascript
app.controller('authentication.MainCtrl', [ '$injector', function($injector) {
	$scope = $injector.get("$scope");
	$log = $injector.get("$log");
	$location = $injector.get("$location");
	$rootScope = $injector.get("$rootScope");
	$window = $injector.get("$window");
	...
}]);
```
