Obectifs
========

Le but de cet exercice est de refaire une petite partie du flux d'actualité de Wizbii en se basant sur l'API publique offerte par Wizbii. Un exemple de ce qui est attendu en terme visuel est disponible à l'adresse https://remialvado.githib.io/wizbii-technical-test/index.html
Cette API est sécurisée au moyen du protocole oAuth2.0 et est donc facilement compréhensible par tout Développeur Web.

Les consignes de cet exercice :
* ne pas dépasser 2 séances de 2h
* intégrer au minimum le module faisant apparaitre des publications simples.
* ne faire aucun appel au serveur pouvant créer de la donnée. Exemple : l'ajout de thanx ou de publications doit être mocké
* les technos et outils utilisés ne sont pas imposées.
* le compte à utiliser : remi.alvado+wizbii-technical-test@gmail.com / wizbii

API
===

Authenticate
------------

L'API d'authentification suit les normes oAuth2.0. Il faut faire un appel POST sur le endpoint /v1/account/validate avec les paramètres suivants :
* *grant_type* : seul le grant_type "password" est supporté pour le moment
* *username* : le mail de la personne qui souhaite se logger
* *password* : le password de la personne qui soihaite se logger
* *client_id* : l'identifiant du client. Dans ce cas : _test_ 
