Fetch est une fonction de JavaScript côté client. Seul le navigateur peut lancer ce type de requête. Il est possible de tricher avec le module node-fetch pour les effectuer côté serveur avec Node.js. En gros, cela permet de faire une requête HTTP sur le web et de récupérer des données (fichier, image, JSON, texte, etc.).

Pour effectuer une requête fetch, on appelle simplement la fonction fetch() en lui passant l'URL visée. Par défaut, fetch envoie une requête GET, mais il est possible de spécifier d'autres méthodes HTTP (POST, PUT, DELETE, etc.) en passant un deuxième paramètre contenant les options de la requête, telles que le corps de la requête, les en-têtes (headers), les cookies, etc.

En gros, on envoie ce dont on a besoin au serveur, soit des données (un ID, par exemple) ou des tokens de connexion, on y ajoute ce qu'on veut faire : créer (POST), récupérer (GET), mettre à jour (PUT), supprimer (DELETE), etc. Ce sont les méthodes du protocole HTTP.

Fetch renvoie une promesse, c'est une variable asynchrone. Cela veut dire qu'on ne sait pas quand il y aura des données dedans (car il faut attendre la réponse du serveur !). Une fois qu'on a récupéré la réponse (on dit qu'on a résolu la promesse), on peut la traiter. Comme c'est une requête HTTP, elle contient des informations comme le statut de la réponse (code 200, 404, etc.), les en-têtes (headers) et le corps de la réponse (là où se trouvent les données renvoyées).


Pour essayer tu peux coller ce code tel quel dans n'importe quel vue, cela récupère des données sur internet depuis un site de test.

<script>
const getExternalCards = async () => {
  try {
    // Envoie une requête HTTP GET (get est le verbe(la méthode), pour dire que l'on souhaite récupérer des données)
    const response = await fetch('https://jsonplaceholder.typicode.com/todos/1');
    // on regarde si la réponse est ok (pas d'erreur 500, 404, 403 ...)
    if (!response.ok) {
      throw new Error('Erreur de récupération des données');
    }
    // Récupère les données sous la forme d'un objet JSON
    const data = await response.json();
    // on affiche les données dans la console coté client
    console.log(data);
  } catch (error) {
    // on affiche l'erreur dans la console coté client
    console.log(error);
  }
};
// on appelle la fonction
getExternalCards();
</script>