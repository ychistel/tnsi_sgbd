Système de gestion de base de données
=====================================

Après avoir défini un modèle relationnel pour gérer des données, il faut le mettre en place. Bien entendu, il est toujours possible de recourir à la programmation et gérer ses données dans différents fichiers. Différents problèmes risquent de se présenter:

-   Déjà l'écriture du programme pour effectuer des requêtes sur les données;
-   Ensuite, l'accès aux données et surtout l'écriture des données dans les fichiers représentant les relations. 
-   Quels utilisateurs peuvent avoir accès aux données ? Quels droits : écriture, lecture ?
-   Il faut également gérer les accès concurrents, c'est à dire un accès simultanné à des données de la base;
-   Penser à une interface de gestion pour gérer sa base.

Le rôle d'un SGBD est justement de gérer tous ces problèmes. Un SGBD est un ensemble de programmes qui permet de gérer des bases de données. Il propose également pour acéder et modifier les données de la base un langage de requêtes avec une syntaxe précise.

Un SGBD doit permettre:

-   de créer et gérer les utilisateurs;
-   de créer et gérer des bases de données relationnelles;
-   de définir les permissions d'accès en écriture et en lecture des différentes bases de données;
-   de proposer un langage permettant d'effectuer des requêtes sur les données : langage SQL
-   de proposer une interface de gestion des utilisateurs et des bases de données.

Une caractéristique importante des SGBD est la vérification de la cohérence des données dans les tables d'une base de données. Un modèle relationnel bien construit va imposer des contraintes d'intégrité que le SGBD doit pouvoir vérifier. Parmi ces contraintes d'intégrité, un SGBD doit:

-   vérifier l'unicité d'une clé primaire, l'auto incrémenter pour éviter tout doublon.
-   vérifier la cohérence d'une clé étrangère en contrôlant par exemple l'existence de la clé primaire de la relation référencée.
-   contrôler la cohérence des données, leur appartenance à un domaine que l'on précise pour chaque attribut.
-   contrôler qu'un attribut d'un tuple de données n'est pas vide s'il est ainsi construit.

La plupart des SGBD sont construits sur le modèle **client / serveur**. 

-   Côté serveur, on a les programmes qui permettent de construire et gérer les bases de données et les utilisateurs. Les données des bases sont enregistrées dans des fichiers. L'organisation de ces fichiers permet un accès rapide aux données. Le SGBD gère les accès aux fichiers selon les permissions des utilisateurs et gère aussi les accès concurrent.
-   Côté client, un programme permet à un utilisateur authentifié d'accéder et de gérer ses bases de données. Ce programme peut être en ligne de commandes dans un terminal ou avec une interface graphique pour les SGBD les plus évolués. Certains SGBD propose une interface web pour gérer les bases de données après authentification.

Il existe de nombreux SGBD. Certains sont libres comme **MySQL**, **PostgreSQL** et **SQLite** et d'autres sont des logiciels propriétaires comme **Oracle database** et **Microsoft SQL Serveur**.

.. warning::
    
    L'installation de **MySQL** ou **PostgreSQL** nécessite d'avoir un serveur, ce qui implique d'installer des programmes sur sa machine pour créer un environnement type serveur. 
    
    Le SGBD **SQLite** ne nécessite pas de serveur. Il peut être utilisé directement sur sa machine. L'inconvénient est l'absence de gestion des utilisateurs.
