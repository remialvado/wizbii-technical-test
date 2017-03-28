Objectifs
========

Le but de cet exercice est de refaire une petite partie du flux d'actualité de Wizbii en se basant sur l'API publique offerte par Wizbii. Un exemple de ce qui est attendu en terme visuel est disponible à l'adresse https://remialvado.github.io/wizbii-technical-test/index.html
Cette API est sécurisée au moyen du protocole oAuth2.0 et est donc facilement compréhensible par tout Développeur Web.

Les consignes de cet exercice :
* ne pas dépasser 2 séances de 2h
* intégrer au minimum le module faisant apparaitre des publications simples.
* ne faire aucun appel au serveur pouvant créer de la donnée. Exemple : l'ajout de thanx ou de publications doit être mocké
* les technos et outils utilisés ne sont pas imposées.
* le compte à utiliser : decouverte@wizbii.com / decouvertewizbii
* le code doit être disponible sur github ou bitbucket. A toi de faire tes choix mais on veut voir du code :)

API
===

Authenticate
------------

L'API d'authentification suit les normes oAuth2.0. Il faut faire un appel POST sur le endpoint /v1/account/validate avec les paramètres suivants :
* *grant_type* : seul le grant_type "password" est supporté pour le moment
* *username* : le mail de la personne qui souhaite se logger
* *password* : le password de la personne qui soihaite se logger
* *client_id* : l'identifiant du client. Dans ce cas : _test_

Si tout se passe bien, ce service répond avec une 200 contenant le access-token à fournir avec toutes les requêtes suivantes ainsi que le profile courant.
Exemple  :

```shell
curl -X POST -H "Content-Type: application/x-www-form-urlencoded" \
-d 'username=decouverte%40wizbii.com&password=decouvertewizbii&client_id=test&grant_type=password' \
'https://api.wizbii.com/v1/account/validate'
```

En cas de problème à faire fonctionner cette API dans le navigateur, une version mockée des données pourra être utilisée pour accélérer le développement de cet exercice

Dashboard
---------

L'API pour accéder au dashboard nécessite l'envoi du access-token dans les Headers de la requête. En réponse, il retourne une liste de FeedItems qui sont à afficher. Attention : ce service peut mettre quelques secondes à répondre.

Exemple :

```shell
curl -v -X POST -H "Authorization: Bearer 8edjjh0jsggscgoscokk8ok0gc40ss0" \
'https://api.wizbii.com/v2/dashboard/?direction=newest'
```
