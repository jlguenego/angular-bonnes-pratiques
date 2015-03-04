signature
=========

- Les fonctions ne doivent pas contenir trop d'arguments car cela rend le code trop illisible.
- On s'autorise donc maximum 3 arguments.

Si on doit utiliser plus de 3 arguments on applique l'une des techniaues suivantes :

- Mettre les arguments dans un objet.
- S'il s'agit d'injections dans angular, recourir au service $injector.

Exemples :

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
