Organisation de l'application en module
=======================================

- Toujours organiser son application de façon modulaire.
- Les modules doivent satisfaire le single responsibility principle et facilement réutilisables 

Exemple :

```

var serviceA =  angular.module('serviceA',[]);

var serviceB =  angular.module('serviceB',[]);

var serviceApp  = angular.module('serviceApp', ['serviceA','serviceB']);


```