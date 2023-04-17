### Feedback pour l'apprenant3

### Points positifs
Bonne récupération des erreurs
Bonne convention de nommage
Cohérence noms des controller/route

### Points d'amélioration de index.js
Le secret devrait provenir d'un fichier .env pour éviter l'exposition du secret. Il est recommandé d'utiliser un secret plus complexe.
Pour les cookies, l'option "secure" devrait être activée pour que le navigateur ne renvoie le cookie qu'à travers une connexion HTTPS.

### Points d'amélioration de router.js
Il manque beaucoup de routes, mais c'est cohérent avec ce qui a été réalisé.

### Points d'amélioration de dataMapper.js
La méthode getCardByElement doit prendre l'élément à chercher en paramètre, puis réaliser deux requêtes différentes en fonction de si l'élément est null ou non (en modifiant la clause WHERE).

### Points d'amélioration de mainController.js / cardDetails.ejs
Dans le controller, une variable nommée "oneCard" est passée, mais elle n'est pas utilisée dans la vue.
La boucle "for" est inutile car on souhaite uniquement afficher le détail d'une carte.
Il faut utiliser "oneCard" dans le contexte ou renommer la variable dans le controller.
Dans la vue, la variable "card" n'existe pas. Il faut utiliser "oneCard" ou renommer la variable dans le controller.

### Points d'amélioration de searchController.js
La méthode cardElement n'existe pas dans dataMapper.
Pour faire les quatres outils de recherche il faut réaliser quatre méthodes sur quatre routes permettant de répondre aux quatre outils de recherche. Il faut également réaliser les quatre requêtes SQL dans dataMapper. Puis réaliser une route supplémentaire pour afficher les résultats de la requête.

### Points d'amélioration globaux
Difficulté à réaliser les requêtes SQL et à travailler avec CSS/HTML avec EJS.
Attention aux noms des variables entre la vue et le controller.

### Bilan
Tu as réussi à réaliser un morceau de code fonctionnel. 
Inspire toi de ce qui fonctionne pour réaliser la suite pas à pas.
N'hesite pas a commenter le code, cela te permet d'être sur de savoir ce que tu fait et de pouvoir mettre le doigt sur tes lacunes.

### Manquant
étape 3.1/3.2/3.3/3.4