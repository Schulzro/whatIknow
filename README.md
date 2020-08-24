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

* Propagation des évenements. Lors d'un event en mode bubbling, les handlers s'activent du child element au parent element. En mode Capturing, les handlers s'activent du parent vers l'enfant. Par défaut le mode bubbling est activé. `event.target`correspond à l'element qui a initié l'évènement. Cette valeur ne change pas au cours de la propagation de l'event. Pour stopper la propagation des events, il faut appeler `event.stopPropagation()`. Pour empecher l'activation des handlers sur un meme event, il faut appeler `event.stopImmediatePropagation()`

## Structure de données

### Tableau
* Les tableaux sont accessibles rapidement O(1) time mais chaque élément du tableau doit être de la même taille et les tableaux ont besoin de gros blocs ininterrompus de mémoire pour fonctionner. Parce que les éléments d'un tableau doivent être tous de la même taille. On peut se retrouver avec des espaces mémoires inutiles.Les tableaux de pointeurs permettent de résoudre ce problème en stockant l'information où c'est possible en mémoire et les adresses mémoires dans le tableau. Enfin les tableaux de pointeurs permettent de résoudre le problème de l'espace mémoire mais ralentit la lecture des informations par le processeur qui ne peut pas mettre en cache les informations du tableau.
* En Python, JS et Ruby, les tableaux sont dynamiques par défault cad qu'ils s'agrandissent quand il n'y a plus de place. En Java les Array sont statiques et les ArrayList sont dynamiques.
* Les tableaux dynamiques, lorsque plein, crée un autre tableau et double sa taille, copie les éléments du tableau et ajoute le nouveau élément. L'ancien tableau est ensuite libéré. Cette opération prend O(n) time parce qu'il faut copier les n éléments du tableau. Toutefois en moyenne le coup d'un ajout est O(1).

### Liste chainée
* Les listes chainées sont des chaînes des tableaux de deux éléments, l'information et l'adresse mémoire du prochain élément. L'avantage des listes chaînées est qu'il n'y a pas besoin de savoir quel sera l'espace mémoire nécessaire à l'avance et que l'ajout d'un nouveau élément n'est qu'une simple opération de O(1).
* Le worst-case des listes chaînées est toujours O(1). De plus, ajouter un élément au début d'un tableau est O(1) alors que c'est O(n) pour un tableau dynamique.
* Toutefois, l'inconvénient est que la lecture d'une liste chainée est plus longue que celle d'un tableau dynamique. En lecture ces tableaux ont O(1) alors qu'il faut parcourir toute la chaine pour trouver un élément i donc O(i) time.

### Tableaux de hashages
* Les Hash tables fonctionnent grâce au système clé-valeur. On obtient la clé grâce à la fonction de hashage. Avec un tableau de hashage, on peut rapidement lire une valeur à partir d'une clé, O(1) time. L'inverse n'est pas vrai.
* Si deux clés formées par la fonction de hashage sont égales, il y a une hash collision. Une des strategies est de stocker les valeurs dans une liste chainée. La clé donne accès à un pointeur qui permet d'accéder à la liste. Mais dans ce cas la, la lecture de la chaine redevient O(n). Mais globalement c'est rare donc on se dit que c'est O(1).
* Pour empecher des man-in-the-middle attack, on peut vérifier que le hash fournit est bien égale au hash du fichier téléchargé.

## Algorithmie
### Binary search 
* On divise un tableau de moitié n fois donc on a un cost time de O(log2(n)) 

## Package.json
### Versions 

## Achitecture
### Microservices
Voir gdoc https://drive.google.com/drive/u/0/folders/1xkmmvdybXlNgy7dk4UTPNerjTte3fGDW

Dans une architecture en microservice, on essaye de partager les données et les services communs aussi peu que possible afin que chaque service puisse fonctionner indépendament.
On parle de "share-as-little-as-possible".
Les microservices sont un style d'architecture qui compose une application par une collection de services autonomes representant un business domain ( a bounded context).
Architecturally, a bounded context refers to the coupling of a component (or in this case, a service) and its associated data as a single closed unit with minimal dependencies.
Dans une architecture SOA, on aura tendance à mettre de la business logic dans le méchanisme de communication, en utilisant un ESB par exemple. Au contraire dans l'architecture microservices, on parle de smart endpoints et dumb pipes. En effet, les services possèdent la logique métier, recoivent une requete, calculent des trucs et renvoient une réponse. Les pipes ne font que transmettre la réponse à un autre service.
### Service Oriented Architecture

Dans une architecture de style SOA, on parle de "share-as-much-as-possible". L'important c'est de pouvoir réutiliser des fonctionnalités business.

### Proxies 
Un Proxy c'est un système qui agit au nom d'un autre système.
Une fois que le proxy a intercepté la requete du client, il peut effectuer plusieurs actions comme bloquer l'accès au site car il est infecté par un virus ou le bloquer car le client est un spammeur. C'est le site internet qui utilise un proxy pour controler qui accède à son site.

Un reverse proxy va transmettre les requetes d'un client X à un site Z. Le client pense qu'il accède au site Y mais en fait, Y est un reverse proxy qui transmet tout à Z. Un reverse proxy ne necessite aucune configuration du côté du client.
Les CDN, content distribution network, fonctionne sur ce modèle. Pour éviter qu'un site web Z soit innondé de requetes qu'il ne peut pas gérer, il envoie tout sur des reverse proxy d'abord.
### Remote access protocol
Liste de certains protocole d'accès à des services par exemple: 
* REST Respresentational State Transfer
* SOAP Simple Object Access Protocol
* AMQP Advanced Message Queuing Protocol
* JMS Java Message Service
* MSMQ Microsoft Message Queuing
* Remote Method Invocation RMI

## Event Loop JavaScript
L'event loop regarde la callstack et pousse la première call back de la file Task queue si la call stack est vide. Les call backs arrivent dans la task queue via les Web APIs. Les Web Apis sont par exemple, la DOM API, l'api Ajax ou setTimeout.

## OOPS
* Inheritance: l'héritage permet de définir une classe à partir d'une autre classe. L'héritage est utile pour la réulitisation du code et accélérer l'implémentation du code.
* Encapsulation: l'encapsulation permet de protéger l'accès à des variables d'une classe. Ces variables pourront uniquement être accéder via une méthode de la classe.
* Polymorphisme: le polymorphisme permet à un objet de prendre plusieurs formes. En Java, tous les objets sont polymorphiques puisqu'ils sont au moins leurs types et de type Objet.
* Les attributs privés d'une classe sont uniquement accessibles depuis la cla
* Abstaction: En utilisant le mot-clé abstract sur une classe, on l'empêche d'etre instantier. Pour l'utiliser, il faut hériter la classe et fournir une implémentation pour toutes les méthodes abstract de la classe.

## Java
* Un fichier Java ne peut contenir qu'une seule classe publique.
* Ce n'est pas obligatoire d'avoir un constructeur par défaut dans une classe.
*  Pour empecher une classe d'être hérité, il faut utliser le mot-clé `final`. Les méthodes d'une classe final ne peuvent pas être override.
* Le garbage collection ne garantit pas à un programme de ne pas épuiser sa mémoire. Un programme peut créer des objets plus rapidement qu'ils ne seront collectés. Certains objets ne sont pas soumis au garbage collector.
* Une classe `abstract`peut avoit des méthodes abstract et des méthodes non abstract.
