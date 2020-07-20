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
