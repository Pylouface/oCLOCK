### Feedback pour le code apprenant1

### Points positifs
Bonne compréhension des routes
Bonne compréhension des view
Bonne utilisation du camelCase
Bonne requête SQL
Bonne vues

### Points d'amélioration de dataMapper.js
ATTENTION : dans ta fonction searchByValues, tu t'exposes à des injections SQL en raison de l'utilisation directe de variables d'entrée (les paramètres direction, value et string) dans la construction de la requête SQL. Pour améliorer la sécurité, il est recommandé d'utiliser des requêtes préparées ou des outils d'ORM qui utilisent des mécanismes de liaison de paramètres pour éviter l'injection SQL.
Dans les méthodes searchByName/searchByValues/searchByLevel, je te conseille de toujours utiliser la syntaxe de construction de requêtes préparées utilisant text et values. Cela évite les risques d'injection SQL et, de plus, ça permet de séparer la logique de la requête des variables utilisées.

### Points d'amélioration de cardController.js
Ton contrôleur s'appelle cardController, du coup toutes les fonctions concernant le deck ne devraient pas y figurer. La solution serait de renommer ton contrôleur en deckController.js et de mettre ta méthode renderOneCard dans un contrôleur cardController.js ou dans le main, car cette méthode ne concerne pas le deck, mais une carte.
Ligne 35, une console.log traîne.

### Points d'amélioration globaux
Attention aux conventions de nommage des fonctions, essaye de toujours respecter la même logique, par exemple utiliser le mot get pour récupérer un ou des éléments plutôt que d'alterner get/search.
Attention à ne pas laisser de code mort en commentaire.
Garde une cohérence entre le nom de ton contrôleur et la route. Ton chemin se nomme deck, ton contrôleur devrait porter le même nom.
Pour chipoter : dans la méthode searchByLevel et renderOneCard, utilise plutôt parseInt que Number, même si les deux marchent. 'parseInt' est plus explicite et offre une plus grande cohérence de comportement sur différentes plateformes.
Attention aux console.log persistants.

### Bilan
Pas grand-chose à redire, mis à part les problèmes d'injection SQL et les conventions de nommage. Attention a garder la même logique de nommage dans tout ton code.