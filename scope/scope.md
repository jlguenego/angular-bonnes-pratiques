$scope
========

- Bien veiller à ce que l'ensemble des variables du scope soient déclarées dans le controleur.
- La directive ```ng-init``` est proscrite.

Une variable ne doit pas etre déclarées dans la vue HTML. Ainsi le lecteur du code sait où sont initialisées l'ensemble des variables du scope.
