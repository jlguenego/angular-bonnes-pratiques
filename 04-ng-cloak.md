ng-cloak
========

- Pour que ```ng-cloak``` soit utilisable il faut inclure dans le ```<head>``` le fichier ```angular-csp.css```.

```html
<link rel="stylesheet" type="text/css" href="https://ajax.googleapis.com/ajax/libs/angularjs/1.3.10/angular-csp.css" />
```

- Si la partie ```<head>``` de l'HTML inclue du code AngularJS, alors il faut inclure ```ng-cloak```
dans la balise ```<html>```, sinon l'inclure dans la balise ```<body>```.



