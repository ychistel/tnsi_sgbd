Système de gestion de base de données
=====================================

Le rôle d'un SGBD
-----------------

**SGBD** est l'acronyme de **S**\ ystème de **G**\ estion de **B**\ ase de **D**\ onnées.

Un SGBD est un logiciel qui permet de créer et gérer des bases de données accessibles à un ou plusieurs utilisateurs.

Le langage utilisé dans les SGBD est le **SQL**, acronyme de **S**\ tructured **Q**\ uery **L**\ anguage.

Les fonctionnalités d'un SGBD sont:

-  créer des bases de données, ensemble de relations (tables);
-  créer des relations (tables) à partir d'un schéma relationnel;
-  ajouter, modifier, supprimer des données dans les relations (tables);
-  effectuer des requêtes pour interroger les relations, obtenir des données, triées ou non, respectant une ou plusieurs conditions;
-  spécifier les contraintes d'intégrités : clés primaires, clés étrangères, domaine de valeurs;
-  sécuriser et pérenniser les données ;
-  gérer les droits, permissions, des utilisateurs de la base de données.

Contraintes d'intégrité
-----------------------

Une caractéristique importante des SGBD est la vérification de la cohérence des données dans les tables d'une base de données. Un modèle relationnel bien construit va imposer des contraintes d'intégrité que le SGBD doit pouvoir vérifier. On redonne quelques contraintes d'intégrité qu'un SGBD doit vérifier pour assurer la cohérence des données d'une base de données.

.. rubric:: Contrainte d'intégrité de relation

Toute relation doit posséder une **clé primaire**. Cette clé primaire garantit l'unicité des enregistrements (p-uplet) dans la table.

Un attribut (ou plusieurs) est une clé primaire s'il est renseigné et de valeur unique dans la table.

.. rubric:: Contrainte d'intégrité de référencement

Les tables sont liées entre elles. Cette liaison est assurée par la présence d'une clé étrangère.

Une **clé étrangère** est un attribut d'une table dont les valeurs sont celles d'une clé primaire d'une autre table.

Un enregistrement (p-uplet) d'une table avec une clé étrangère respècte la contrainte d'intégrité si:

- la clé étrangère est vide, sans valeur (pas de lien pour l'enregistrement);
- la clé étrangère possède une valeur associée à la valeur d'une clé primaire de la table qu'elle référence.

La contrainte d'intégrité est rompue si la clé étrangère contient une valeur qui n'existe pas comme clé primaire de la table qu'elle référence.

.. rubric:: Contrainte d'intégrité de domaine

Chaque attribut d'une relation est défini pour un domaine de valeurs. Par exemple, un attribut peut être de type **entier**. Toute valeur autre que nombre **entier** ne respecte pas la contrainte d'intégrité.

Modèle client - serveur
------------------------

.. figure:: ../img/client_serveur.png
    :align: center

Un SGBD est un logiciel installé sur un serveur. Dans ce mode de fonctionnement, l'accès aux données à plusieurs utilisateurs est possible.

Cela implique que le SGBD permette :

-  de créer, supprimer des utilisateurs, gérer l'authentification (login, mot de passe) pour la connexion à une base de données;
-  de gérer les permissions en lecture et écriture sur les relations de la base de données.
-  de gérer les accès concurrents, c'est à dire autoriser la lecture et l'écriture des données à plusieurs utilisateurs en même temps.

Il existe de nombreux SGBD que l'on peut classer en deux catégories : libre ou propriétaire.

-  Parmi les logiciels libres : MySQL, PostgreSQL, MariaDB;
-  Parmi les logiciels propriétaires : ORACLE et Microsoft SQL Server

Modèle embarqué
---------------

**SQLITE** est un SGBD qui a la particularité de s'installer sur toute plateforme en mode dit embarqué ce qui signifie non serveur. Cela permet de gérer des bases de données sur une machine personnelle, très utile pour le développement.

.. figure:: ../img/sqlite_browser.png
    :align: center
    :width: 100%

.. _sqlite: https://sqlite.org/index.html
.. _sqlitebrowser: https://sqlitebrowser.org/dl/

.. note::

    Le logiciel **SQLITE** peut se télécharger sur le web. Il existe 2 versions de sqlite pour windows:
    
    -   Une version en ligne de commandes disponible sur le site `sqlite`_.
    -   Une version avec interface de gestion disponible sur le site `sqlitebrowser`_.
