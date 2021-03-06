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
* Une classe dit mixin est une classe qui contient des méthodes pouvant être utilisées par d'autres classes sans pour autant être parent de ces classes.

## Java
* Un fichier Java ne peut contenir qu'une seule classe publique.
* `Long` est un objet, il peut donc être null alors que `long` est une valeur primitive et doit avoir une valeur.
* Ce n'est pas obligatoire d'avoir un constructeur par défaut dans une classe.
*  Pour empecher une classe d'être hérité, il faut utliser le mot-clé `final`. Les méthodes d'une classe final ne peuvent pas être override.
* final variables -> creér une constante
* final method -> la méthode ne peut pas être override
* final class -> la classe ne peut pas être héritée
* Le garbage collection ne garantit pas à un programme de ne pas épuiser sa mémoire. Un programme peut créer des objets plus rapidement qu'ils ne seront collectés. Certains objets ne sont pas soumis au garbage collector.
* Une classe `abstract`peut avoit des méthodes abstract et des méthodes non abstract.
* en Java, le polymorphime prend principalement deux formes: overloading et overriding. 
** Overriding est une fonctionnalité qui permet d'avoir une implémentation spécifique d'une méthode présente dans une classe parent. L'overriding s'effectue à runtime.Les signatures des deux classes doivent être les mêmes.
** Overloading est un polymorphisme de compiletime. Il s'agit de méthodes ayant le même nom mais pas le même nombre et le même type de paramètres.
* Le Factory Pattern permet de cacher la logique de création d'un objet au client.
* Quand un constructor est private, la classe ne peut pas être hérité. La seule façon de créer un objet de la classe est de créer une méthode statique dans la classe qui crée l'objet.
* Dans un bloc try-catch-finally, le finally est executé même si il y a un return ou un break dans le try.
* Object Reflection en Java permet d'avoir des informations sur les variables et méthodes d'une classe.
* DTO vs DAO: DTO pour Data transfer object, objet utilisé uniquement pour de la manipulation de données donc que des getters et des setters, pas de business logic. DAO pour Data Access Objet, objet utilisé pour persister de la donnée. Un DAO contient des méthodes de CRUD.
* autoboxing: l'autoboxing en java est une action du compiler permet de convertir des types primitives en leur classes objet long to Long. A l'inverse, one parle d'unboxing quand le compiler convertit un Long en long.
* Un .jar contient des fichiers de ressources, des librairies, des fichiers de config. Un .war est packagé pour le web avec des fichiers en plus que le .jar comme des fichiers html/js/jsp. Un war peut être deployé sur n'importe quel container servlet.
* HashSet vs TreeSet: 
** HashSet: C'est un set qui utilise une Data Structure de hashage. Efficace pour les recherches, insertions et suppressions.O(1). Les hashSet permettes des éléments null et pas les TreeSet
** TreeSet: C'est un set qui utilise une Data Structure de graphe. Plus long pour la recherche, l'insertion et la suppression O(log(n)). Par contre un TreeSet garde l'ordre d'insertion.

## Maven
* Project Object Model (POM), Maven reads the pom.xml to build a project. It defines the address for the project artifact using a coordinate system. Specifies project informatio, plugins, goals, dependencies and plugins.
* Repositories hold artifiacts and dependencies
** local repository .m2 folder -local cache
** remote repository accessible via un protocole (ex: HTTP) pour accéder à des dependences. Remote Repo example The Central Maven Repository
** le repo local est vérifié avant le remote repository
* A Plugin a collection of goals, a goal is an action performed. Ex: The compiler plugin has two goals: compile sources and compile tests
* Les plugins sont appelés dans des phases du lifecycle. Il y a 3 lifecycles: clean, default et site. Et chacun de ses lifecycles est composé de phases.
* Executer une phase fait executer toutes les phases lui précédent dans le lifecycle.

## GitLab
* Un job correspond à la plus petite brique executable par un pipeline. Un job est défini par les contraintes sous lesquels il doit être executé. Un job doit contenir un tag script. 
* Un Runner est un programme permettant d'executer des jobs dans un pipeline. Un Runner est lié à un executor qui définit l'environnement dans lequel est executé le job. Exemple d'Executors (SSH, Shell, VirtualBox, Docker, etc.)

## Git
* Move changes from one commit to another
** git reset --soft <commit_id>^ (reset soft to the commit before the one you want to change)
** git restore <file-path> 
** git commit --fixup <commit_id>
** git stash the file to put to another commit
** git rebase 
** git stash pop on the commit you want to assign the changes
** amend the commit 
** finish rebase
 
## Bases de données
* INNER JOIN sélectionne seulement les entrées qui sont dans la table A et dans la table B.
* LEFT OUTER JOIN sélectionne toutes les entrées de la table A et les entrées qui matchent dans la table B.
* RIGHT OUTER JOIN sélectionne les entrées qui matchent de la table a et toutes les entrées de la table B.
* **Denormalization** Dénormaliser c'est optimiser le temps de lecture d'une base de données en copiant des données ou en regroupant les données d'une certaine façon. C'est le job du developpeur de s'assurer que les données vont rester consistentes quand elles seront dénormaliser. La dénormalisation accélère la lecture mais ralentit l'écriture, la suppression et la mise à jour des données.
* Une view en SQL c'est une sorte de variable de requête SQL. Ca permet de faire des requêtes plus simples et plus sécurisées car on peut choisir quelles sont les colonnes à rendre disponible dans la vue.
* **Collation**: Une collation est un réglage qui permet de définir comment une base de données doit gérér un caractère, soit au niveau du server, de la base ou de la colonne. Chaque collation définit un bit pattern associé à chaque character. Ensuite une collation définit comment des données de caractères doivent être comparées et triées en prenant en compte les spécifités de la langue mais aussi des options tel que respect de la casse ou des accents. Des requêtes identiques accédant à des colonnes identiques mais avec des collations différentes peut donc donner des résultats différents
* utf8 est une encodage de caractères informatiques. Il permet de stocker des caractères dans une base de données sur 3 octets. utf8mb4 est une autre tecnique d'encodage qui permet de stocker des caractères sur 4 octets et notamment les emojis.
* **SQL_CALC_FOUND_ROWS**: permet de compter le nombre maximum de résultats sans prendre en compte le LIMIT. Une fois une requête faite avec SQL_CALC_FOUND_ROWS, il faut faire une autre requête avec la fonction FOUND_ROWS() pour connaitre le nombre maximum de résultats
* **Coalesce**: retourne la première valeur non null dans une liste

## Testing

* **e2e tesing** : Un programme teste l'application comme s'il était un utilisateur
* **integration testing** : l'interaction entre plusieurs composants sont testés
* **unit testing** : test des petites parties de façon isolées
* **static testing** : test les typos et les erreurs de types dans le code

### Selenium
Selenium est une suite d'outils de testing de web apps. Selenium fonctionne dans une architecture client/server. Cette suite comprend 3 componsants
* Selenium IDE 
* Selenium WebDriver
* SeleniumGrid

### Bash
* Rendre un fichier executable: chmod +x nom du fichier

## Networking

Une socket correspond à un endpoint dans une communication entre deux programmes. Une socket est liée à une adresse IP et à un numéro de port afin que la couche TCP puisse identifier l'application à laquelle les données sont destinées.


