# Database Glossary

### Banque de données.
```
 La banque de données permet de stocker toute les DataBase, c'est un enssemble de base de données.
```
 | Banque De Données |
 |:-----------------:|
 | Bases de Données |
 | Tables |
 | Columns => Lignes d'enregistrements |

### Base De Donnée (BDD) or Database (DB).
```
Une base de données (database), permet de stocker et de retrouver l'intégralité de données brutes
ou d'informations en rapport avec un thème ou une activité; celles-ci peuvent être de natures différentes
et plus ou moins reliées entre elles, dans la très grande majorité des cas,
ces informations sont très structurées, et la base est localisée dans un même lieu et sur un même support.
Ce dernier est généralement informatisé.
```
### SGBD or (DBMS).
```
Le SGBD (Système de Gestion de Base de Donées) ou DBMS ( DataBase Management System)
est un système de requêtage qui permet de manipuler les données.
il en éxiste plusieurs tel que MySQL, Oracle, MariaDB, SQLServer ect ..
Il permet de gérer l'enssemble des fichiers de façon simplifier grâce à des requête.
Il est composé en 4 grandes tâches.

1. Un moteur SQL.
 - Permet de lire et de retranscrire les lignes d'enregistrements.
2. Un catalogue.
 - contient la description de la base de données don les utilisateurs et leurs droits.
3. Un Language de requête.
 - Pour faire les demandes de requêtes (SQL) à la base de données.
4. Un Processeur de requêtes.
 - Permet de comprendre et de traduire notre requête en SQL.
```


### Les Tables
```
Une table est un ensemble de données organisées sous forme d'un tableau où les colonnes
correspondent à des catégories d'information (une colonne peut stocker des numéros de téléphone, une autre des noms...)
et les lignes à des enregistrements, également appelés entrées.

Chaques tables possèdes deux fichiers.

1. Un fichier schéma qui permet d'afficher le nombres de colonnes (columns) et de lignes que possèdes la tables.
2. Un fichier qui contient l'enssemble des lignes d'enregistrements.
```
<!-- ![text alt](http://www.pintire.com/wp-content/uploads/2017/09/dbms.png) -->
### Le processus de requête.

| Requête SQL |
|:-----------:|
|Vérification des droits de l'utilisateur|
|Envois la commande au moteur SQL qui manipule les fichiers et fait les traitement necessaire.|
| Puis retourne le résultat de la requête|
