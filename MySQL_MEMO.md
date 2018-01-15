# Administrez vos bases de données avec MySQL

## Syntaxe de SELECT :
* La requête qui permet de sélectionner et afficher des données s'appelle SELECT.
* SELECT permet donc d'afficher des données directement. Des chaînes de caractères, des résultats de calculs, etc.

#### exemple :
```
SELECT 'Hello World !';
SELECT 3+2;
```
* SELECT permet également de sélectionner des données à partir d'une table. Pour cela,
  il faut ajouter une clause à la commande SELECT : FROM
  La clause FROM, qui définit de quelle structure (dans notre cas, une table) viennent les données.

```
SELECT colonne1, colonne2, ...
FROM nom_table;
```
* Sélectionner toutes les colonnes :
```
SELECT *
FROM Animal;
```
* Il est cependant déconseillé d'utiliser SELECT * trop souvent.
  Donner explicitement le nom des colonnes dont vous avez besoin présente deux avantages :

 1. D'une part, vous êtes certains de ce que vous récupérez ;
 2. D'autre part, vous récupérez uniquement ce dont vous avez vraiment besoin, ce qui permet d'économiser des ressources.

## La clause WHERE :
 * La clause WHERE ("où" en anglais) permet de restreindre les résultats selon des critères de recherche.
   On peut par exemple vouloir ne sélectionner que les chiens :
   ```
   SELECT *
   FROM Animal
   WHERE espece='chien';
   ```
### Les opérateurs de comparaison :
* Les opérateurs de comparaison sont les symboles que l'ont utilise pour définir les critères de recherche
  (le = dans notre exemple précédent). Huit opérateurs simples peuvent être utilisés.
  | Opérateur | Signification |
  |:---------:|:-------------:|
  | = | égale |
  | < | inférieur |
  | <= | inférieur ou égal |
  | > | Supérieur |
  | => | Supérieur ou égal |
  | <> ou =! | Différent |
  | <=> | 2gal ( Valable pour NULL aussi) |

#### Exemple :
 ```
SELECT *
FROM Animal 
WHERE date_naissance < '2008-01-01'; -- Animaux nés avant 2008

SELECT *
FROM Animal
WHERE espece <> 'chat'; -- Tous les animaux sauf les chats
```
#### Combinaisons de critères :

## SQL dans PHP :

* Pour connecter votre base de données à votre page vous devez renseigner la ligne suivante entre balise php.
```
$bdd = new PDO('mysql:host=localhost;dbname=test', 'root','');
```
* pour lancer une requête MySQL
```
$bdd->query('ma requête SQL');
```
