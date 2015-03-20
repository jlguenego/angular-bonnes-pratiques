$scope
========

- Bien veiller à ce que l'ensemble des variables du scope soient déclarées dans le contrôleur.
- Les variables qui ne sont pas exposées dans la vue doivent rester locales au contrôleur. Il
ne faut pas surcharger le scope.
- La directive ```ng-init``` est proscrite.
- Mettre de préférence les variables dans $rootScope que si elles ont vraiment besoin
d'être vues par l'application entière.

Une variable ne doit pas etre déclarées dans la vue HTML.
Ainsi le lecteur du code sait où sont initialisées l'ensemble des variables du scope.
