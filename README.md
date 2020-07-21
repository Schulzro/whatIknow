# whatIknow

## Javascript

* `null` et `undefined` sont deux choses différentes. `null`est une valeur primitive qui siginifie qu'une variable n'a pas de valeur alors qu'`undefined`est une variable globale de type `undefined` et de valeur `undefined. 
* Contrairement à `==`, `===` vérifie les types et est donc moins tolérant.
* Pour comparer deux objets en JS, il faut vérifier que les deux objets ont des propriétés de même nom avec les mêmes valeurs. L'égalité devient plus difficile à tester si les propriétés ont des objets en valeurs ou si une des valeurs est `NaN`car `NaN` n'est pas égale à elle-même.
* Les fonctions `bind`, `apply`et `call` permettent de specifier le contexte - this - à utiliser dans une autre fonction.
  * `bind` retourne une exacte copie de la fonction avec le nouveau this comme contexte et les paramètres mis en entrée.
  * A la différence de `bind`, `apply` et `call` doivent s'executer tout de suite avec le contexte fourni. `apply`prend les arguments sous la forme d'un tableau alors que `call`prend les arguments un par un.
* `arguments`est accessible dans chaque fonction et permet d'avoir accès aux arguments sous la forme d'un tableau-objet. Il n'a pas les méthodes classiques de `Array`.
* `this`fait référence au contexte d'execution d'une fonction. `this`est toujours un objet.
 * Dans le contexte global ou dans une fonction `this`fait référence à `window object`. 
* IIFE veut dire Immediate Invoking Function et fait référence à une fonction qui s'execute immédiatement. Avec le mode `'use strict'`, la valeur de `this` est undefined. 
 * IIFE: `(function(){})()`
* `var a = (2,3,5)`. La valeur de a est 5. La virgule retourne la valeur du dernier paramètre.
* `2 in [1,2]` retourne `false` car in retourne un index d'un tableau et 2 n'est pas un index du tableau.
* Closure c'est l'execution d'une fonction dans une fonction. Une closure maintient l'état du scope extérieur.
* L'ordre d'accès aux variables est variables locales, paramètres de la fonction, les scopes extérieurs de la fonction, puis le contexte global.
* L'ordre d'hoisting dans une fonction est la declaration de la fonction, puis la variable d'assignation de la fonction puis les variables. L'assignation d'une variable reste à sa place.
* Dans une fonction, une déclaration de fonction de type `function a (){}` est hoisted en premier et agit de la meme façon que `var a = function (){}`
* Quand on utilise `var customObject = Object.create(myObject);`, `customObject` a hérité de `myObject`donc `customObject`a accès à ses propriétés et aux propriétés de son père `myObject`.
* Les primitives string, number, etc. sont passées en paramètres par valeur alors que les objets sont passés en référence.
* Une déclaration de fonction est sauvegardé en mémoire et peut être utilisé à n'importe quel moment. Une expression de fonction s'écrit comme suit : 
` var foo = function(){ return 'bar'}`. Les expressions de fonctions sont executés uniquement quand l'interpreteur lit la ligne de code.
* Le scope fait référence à la visibilté des variables dans une fonction. Le contexte est lié à l'objet par lequel la fonction a été appelé.

## Structure de données

### Tableau
* Les tableaux sont accessibles rapidement O(1) time mais chaque élément du tableau doit être de la même taille et les tableaux ont besoin de gros blocs ininterrompus de mémoire pour fonctionner. Parce que les éléments d'un tableau doivent être tous de la même taille. On peut se retrouver avec des espaces mémoires inutiles.Les tableaux de pointeurs permettent de résoudre ce problème en stockant l'information où c'est possible en mémoire et les adresses mémoires dans le tableau. Enfin les tableaux de pointeurs permettent de résoudre le problème de l'espace mémoire mais ralentit la lecture des informations par le processeur qui ne peut pas mettre en cache les informations du tableau.
* En Python, JS et Ruby, les tableaux sont dynamiques par défault cad qu'ils s'agrandissent quand il n'y a plus de place. En Java les Array sont statiques et les ArrayList sont dynamiques.
* Les tableaux dynamiques, lorsque plein, crée un autre tableau et double sa taille, copie les éléments du tableau et ajoute le nouveau élément. L'ancien tableau est ensuite libéré. Cette opération prend O(n) time parce qu'il faut copier les n éléments du tableau. Toutefois en moyenne le coup d'un ajout est O(1).

### Liste chainée
* Les listes chainées sont des chaînes des tableaux de deux éléments, l'information et l'adresse mémoire du prochain élément. L'avantage des listes chaînées est qu'il n'y a pas besoin de savoir quel sera l'espace mémoire nécessaire à l'avance et que l'ajout d'un nouveau élément n'est qu'une simple opération de O(1).
* Le worst-case des listes chaînées est toujours O(1). De plus, ajouter un élément au début d'un tableau est O(1) alors que c'est O(n) pour un tableau dynamique.
* Toutefois, l'inconvénient est que la lecture d'une liste chainée est plus longue que celle d'un tableau dynamique. En lecture ces tableaux ont O(1) alors qu'il faut parcourir toute la chaine pour trouver un élément i donc O(i) time.
