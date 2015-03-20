# Maximiser la lisibilité du code

**On maximise la lisibilité du code pour augmenter la productivité et le confort du programmeur.**

Pourquoi est-il plus facile de développer dans un langage comme Java qu’en
assembleur MASM,  voire directement en langage machine ?

Pourquoi n'écrit-on pas
directement un programme dans son format final, c’est-à-dire par exemple sur
Windows, le « .exe » (au format Microsoft Portable Exécutable) ?


La réponse à ces questions a l’air évidente mais comment le dire de manière
claire ? Théoriquement, il n’est pas plus difficile de faire une addition entre
deux variables Java qu’entre deux registres du CPU ou d’appeler une fonction en
assembleur qu’en Java.

Pour répondre à cette question, on peut prendre **l’exemple du système de
robinetterie**.


Imaginons que l’on doive remplir une bassine d’eau à environ ```T = 35``` degré
selon un certain débit ```D``` pour donner un bain à un nourrisson, à l’aide
d’une
vieille robinetterie équipée de deux robinets, l’un pour l’eau chaude à
température ```Tc```, et l’autre pour l’eau froide ```Tf```.

Pour cela, il faut ouvrir les deux robinets de manière à ce que la somme des
débits ```Dc + Df``` soit égale au débit voulu ```D```.
Et en plus, il faut que la température résultante soit celle recherchée :
```(Dc*Tc + Df*Tf)/(Tc+Tf) = T```.

Faut avouer que ce n’est pas facile.

Pourquoi ?

L’ergonome va vous répondre que c’est parce que les **variables
physiques** du système (en l’occurrence ```Dc``` et ```Df```) ne
coïncident pas avec les **variables psychologiques** de l’utilisateur (en
l’occurrence le débit ```D``` et la température ```T``` voulue).

Un **robinet avec un mitigeur** et muni d’une manette qu’il faut soulever pour
augmenter le débit et faire pivoter pour augmenter ou diminuer la température
est jugée nettement plus ergonomique, car elle fait davantage coïncider les
variables psychologiques et physiques.

Le mathématicien, lui, voit cela comme faire des **changements de base**
(diagonalisation de matrice, inversion de matrice).

Eh bien cela est pareil entre le langage machine, et le langage Java : les
variables physiques du langage machine sont plus éloignées des variables
psychologiques que les variables physiques du langage Java.

En d’autre terme, l’ergonome dit aussi que la **distance sémantique** réalisée
lors
de la lecture ou l’écriture de code assembleur est plus importante que la
distance sémantique réalisée pour le langage Java.

Il y a aussi la **distance articulatoire** à diminuer : la distance
articulatoire d'exécution respectivement d'évaluation
consiste en tous les petits gestes à effectuer, pour écrire respectivement lire
du code.

Par exemple, le nombre de caractères  à saisir, la longueur d’un texte peut
rallonger la distance articulatoire.

**Ce qu’il faut retenir :**

Une bonne pratique consiste à mettre en place une disposition visant à diminuer
le plus possible la distance sémantique et articulatoire lors des phases de
lecture et d’écriture du code.

# Avoir du « feed back »

Lorsqu’on pilote un véhicule, comme par exemple une voiture, on aime toujours à
ce que la machine nous renvoie un « feed back » lorsqu’on actionne une commande.

C’est le cas par exemple lorsqu’on allume le clignotant : celui-ci renvoie à la
fois une information visuelle sur le tableau de bord mais aussi une information
sonore. Si on oublie de l’éteindre après avoir effectué le virage, celui-ci
s’éteint de lui-même lorsque le volant est remis en direction droite, ou alors
le bruit du clignotant (le « tic tac » devient plus fort et s’élève en
fréquence.

Sur un projet informatique, c’est la même chose : le développeur met en place
une méthode lui permettant d’avoir du « feed back » à chaque petite modification
de code : il effectue immédiatement un test unitaire qui doit prendre le moins
de temps possible pour ramener une vision si le programme « marche » ou pas.

On dit qu’il faut minimiser au maximum le temps de la **boucle incrémentale «
développe & test »**.

**Ce qu’il faut retenir :**

Toujours faire un test unitaire après une modification. Et donc mettre en place
les outils permettant de ne pas rendre « pénible » le test unitaire.

# Performances

**On ne s’intéresse aux performances QUE si on constate un manque de performance.**

Sinon, c’est de la perte de temps et d’argent.

Rappel : on est en projet web, payé
par un client, généralement au temps passé.
Dans le cas d’un manque de performance constaté, on va s’intéresser aux **«
bottlenecks »**, c’est-à-dire aux parties du code les plus critiques, et
UNIQUEMENT celle-là. Souvent, un problème de performance se règle par la
modification de quelques lignes de code seulement.

**Ce qu’il faut retenir :**

La lisibilité du code est plus importante sur un projet que ses performances.
« Sinon, codez en assembleur ! »

# Gérer l’historique et les versions

En programmation incrémentale, il doit être possible de :

-	revenir à la dernière version stable du logiciel, ou plus généralement à
n’importe quelle version stable précédente ;
-	de coder en équipe, c’est-à-dire de « forker » (dupliquer) à n’importe quel
moment le logiciel sur un ordinateur local, de le modifier pour ajouter ou
corriger une fonctionnalité, puis de livrer, avec accord du chef d’équipe, le
logiciel.
-	Tagguer le logiciel en version.

A noter que l’**outil GIT** prend aujourd’hui nettement plus d’ampleur dans le monde
informatique (voir par exemple l’essor de github). Ses avantages par rapport à
**SVN** ou autre est sa nature décentralisée et qu’il est possible au développeur de
travailler même sans avoir accès au repository central. Il permet aussi au chef
de projet de pouvoir ajouter ou rejeter une modification, ou de la remettre à
plus tard.

Mais le plus disruptif avec « git », c’est le nombre d’exemples de  projets que
l’on peut voir fait avec. On a davantage le sentiment de coder comme tous les
développeurs, d’utiliser les même choses et de faire partie de la plus grande
communauté mondiale d’entraide entre développeurs.

Voir par exemple
[ce lien](http://stackoverflow.com/questions/871/why-is-git-better-than-subversion).

Concernant les versions, utiliser une notation comprise par tous. Il existe
aujourd’hui, tout comme les licences « open source » des spécifications de
versionning. La plus connue et utiliser est **semver**. Voir la spécification
[http://semver.org/](http://semver.org/) (version 2.0.0)
Il est important de « commiter » très souvent, à chaque fois que le logiciel est
retesté et stable. C’est la boucle « analyse, pull, développe, test, commit, pull, merge, test, push ».

Un développeur doit en moyenne « commiter » une fois par heure.

**Ce qu’il faut retenir :**

Utiliser un logiciel de gestion de version et d’historique, et « commiter » à
chaque modification, une fois celle-ci testée et considérée comme stable.

