Dans un premier temps, je te conseille d'utiliser Looping pour faire ton MCD (logiciel libre).
Sinon l'un des logiciels les plus utilisé est entreprise architect (très difficile à prendre en main).

Pour commencer, je ne vois pas de problème sur les noms des entités.

## L'entité ADDRESS :
    - Bon attributs
    - Une adresse a bien un est un seul utilisateur, la cardinalité est bonne


## L'entité USER
### les +
    - Bon attributs
    - Un utilisateur peut avoir 0 ou plusieurs adresse, la cardinalité avec ADDRESS est bonne
    - Un utilisateur peut avoir 0 ou plusieurs commandes, la cardinalité avec ORDER est bonne
## les -
    - Un utilisateur peut liker 0 ou plusieurs produit, la cardinalité devrait être 0, N


## L'entité ORDER
### les +
    - Bon attributs
    - Un order à bien 1 et un seul utilisateur
### les -
    - Il est dit dans la consigne "il peut aussi bien sûr passer une commande sur un produit" : cette phrase est ambiguë, il faudrait discuter avec le client pour savoir si une commande n'a qu'un seul produit (cardinalité 1,1)(ce qui est étrange, mais ce qui est noté dans la consigne) ou si une commande peut avoir plusieurs produits (cardinalité 1,N)
    - Dans le cas où il y aurait une cardinalité 1,N, la relation CONTAIN n'est pas très bien nommées, quand le MCD passera en MLD, cette relation sera traduite par une table suplémentaire, une table nommé CONTAIN est trop générique et ambiguë, je te propose ORDER_PRODUCT.


## L'entité PRODUCT
### les +
    - Bon attributs
    - Un produit à bien 0 ou plusieurs commande lié.
### les -
    - Un produit peut être liker par plusieurs utilisateurs, nous avons donc une relation 0,N


## Bilan
Revoir les relations many to many, le reste semble compris.


## Pour aller plus loin
Dans toutes les bases de données il y a des méta data, des données sur des données, par exemple :
- la date de création de la ligne
- la date de mis à jour de la ligne
- dernier utilisateur à avoir modifié la ligne
- statut de la ligne (supprimé, valide, en suspens ...)

