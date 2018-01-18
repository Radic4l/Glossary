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
Ecrire et tester les requêtes suivantes :
o
Liste des boissons : SELECT * FROM `drinks`
o
Liste des ingrédients en manque (dont la quantité est nulle) : SELECT * FROM ingredients WHERE ISNULL (QteStock)
o
Liste des boissons dont le libellé contient le mot « café » : SELECT * FROM `drinks` WHERE `NAME` = "café"
o
Liste des boissons dont le prix est entre 0.40 et 0.70 euros : SELECT * FROM `drinks` WHERE `PRICE` > 140 AND `PRICE` < 180 // SELECT * FROM `drinks` WHERE `PRICE` BETWEEN 120 AND 170
o
Liste des ventes d’aujourd’hui classées par n° décroissant : SELECT * FROM `sale` WHERE DATE(DATE) = curdate() [ou CURRENT_DATE()] ORDER BY `ID` DESC
o
Liste des ingrédients (nom et qte nécesssaire) d’une boisson donnée : SELECT NAME_ING,Dose,Drinks_ID FROM `association` INNER JOIN ingredients ON association.Ingredients_ID = ingredients.ID WHERE Drinks_ID="CAF"
o
Liste des boissons disponibles (pour lesquelles les ingrédients sont dispo) // Der Question =====>
o
Liste des boissons vendues aujourd’hui : select NAME from `drinks` inner join sale on Drinks.ID = sale.Drinks_ID where DATE(DATE) = curdate()
o
Prix de la derniere boisson vendue : select PRICE from drinks ORDER BY ID LIMIT 1
o
Nombre de ventes de la boisson « CaféLong » : SELECT COUNT(Drinks_ID) FROM sale INNER JOIN drinks ON drinks.ID = Drinks_ID WHERE Drinks_ID ="CHO"
o
Rajouter la boisson « Café au lait » : : INSERT INTO `drinks` (`ID`, `NAME`, `PRICE`) VALUES ('CAL', 'Café au Lait', '250')
o
Rajouter 100 à la quantité en stock de l’ingrédient « sucre » : UPDATE `ingredients`
SET `QteStock` = `QteStock`+ 100
WHERE ID = 3
o
Augmenter de 0.10 euros le prix de toutes les boissons : UPDATE `drinks` SET `PRICE` = `PRICE` + 10

Créer une nouvelle vente d’expresso avec 2 sucres : INSERT INTO `sale` (`ID`, `Drinks_ID`, `DATE`, `Qte_Sugar`) VALUES (NULL, 'CAF',NOW(), '2')
o
Supprimer cette vente : DELETE FROM `sale` WHERE `sale`.`ID` = 7 AND `sale`.`Drinks_ID` = 'CAF'; // OU // DELETE FROM `sale` WHERE `ID` ORDER BY `ID` DESC LIMIT 1

Liste des boissons disponibles (pour lesquelles les ingrédients sont dispo) // Der Question
