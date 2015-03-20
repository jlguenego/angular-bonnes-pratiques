Organisation de l'application en module
=======================================

- Toujours organiser son application de façon modulaire.
- Les modules doivent satisfaire le [single responsibility principle](https://en.wikipedia.org/wiki/Single_responsibility_principle) et facilement réutilisables

Exemple :

```

var serviceA =  angular.module('serviceA',[]);

var serviceB =  angular.module('serviceB',[]);

var serviceApp  = angular.module('serviceApp', ['serviceA','serviceB']);


```