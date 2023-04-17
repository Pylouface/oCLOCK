### Feedback pour le code apprenant2

### Points positifs
Assez bonne convention de nommage
Bon camelCase
Bonnes vues

### Points d'amélioration de index.js
Attention à l'utilisation du secret, il doit provenir d'un fichier .env, car sinon il peut être exposé, un hacker pourrait potentiellement s'en servir.
Pour les cookies: Lorsque l'option Secure est activée, le navigateur ne renvoie le cookie qu'à travers une connexion HTTPS. En le désactivant, le navigateur envoie le cookie même sur une connexion HTTP non sécurisée, ce qui rend le cookie plus vulnérable aux attaques de type interception de trafic.

### Points d'amélioration de dataMapper.js
Attention au nom des fonctions. Par exemple, getElements pourrait très bien être une fonction retournant tous les types d'éléments existants.
La requête de getElements retourne toutes les cartes qui ont un élément, mais on souhaite avoir toutes les cartes d'un élément spécifique passé en paramètre. 
Il faut prendre un élément en paramètre, vérifier s'il est null ou pas, et écrire deux requêtes différentes.
Dans la méthode getOneCard, utilise plutôt la syntaxe avec des requêtes préparées pour prévenir les cas d'injection SQL.

### Points d'amélioration de cardController.js
Si je demande une carte inexistante, le controller plante, il faut gérer l'erreur 404 not found.
item n'est pas très bien nommer, avec ce simple nom on comprend mal le but de la méthode.

### Points d'amélioration de deckController.js
Initialiser les variables de sessions req.session.deck dans un controller n'est pas une bonne pratique, il est difficile plus tard de savoir où l'initialisation a eu lieu, il faudrait plutôt utiliser un middleware au chargement de l'application.

### Points d'amélioration de deck.ejs
card.price ne retourne jamais rien , il affiche donc uniquement un $ dans la deuxième colonnes

### Points d'amélioration globaux
Attention, tu ne gères pas les cas d'erreur 404 quand on demande le détail d'une carte ou quand on ajoute une carte qui n'existe pas.
Il faudrait prévoir une page d'erreur.

### Bilan
Attention à la cybersécurité, les bases sont comprises. 
Tu arrives bien à paramétrer une route et à afficher le résultat des requêtes.
Il manquerait aussi la récupération des erreurs

### Manquant
étape 3.4