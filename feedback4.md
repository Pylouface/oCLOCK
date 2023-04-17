### Feedback pour l'apprenant4

### Points positifs
Route controller et view fonctionnel pour la page par défaut.

### Points d'amélioration de dataMapper.js
Dans la méthode getOneCard, utilise  la syntaxe avec des requêtes préparées pour prévenir les cas d'injection SQL.
La méthode getCardByElement doit prendre l'élément à chercher en paramètre, puis réaliser deux requêtes différentes en fonction de si l'élément est null ou non (en modifiant la clause WHERE).

### Points d'amélioration de mainController.js
Dans ta méthode cardPage, tu dois passer l'id de la page à rechercher, pour ce faire tu dois aller la chercher dans l'url (request.params.id, 10), puis la transformer en int. Ensuite dans ton render tu dois lui passer le résultat de ta requete, ici la variable card.
Il faut également gérer l'erreur 404, au cas ou la carte n'existe pas.


### Points d'amélioration globaux
Ne laisse pas de code mort en commentaire.

### Bilan
Tu ne sembles pas bien maîtriser les routes, les requetes SQL, et les controleurs.
Essaye de refaire pas à pas l'exercice en t'aidant de la correction.
Commente chaque ligne, si tu n'arrives pas à la commenter c'est que tu ne la comprends pas bien, c'est un excellent moyen de progresser et de ce rendre compte de ses lacunes.
Hésite pas à revenir vers l'équipe à chaque ligne que tu ne comprends pas.

### Manquant
étape 2/3.1/3.2/3.3/3.4