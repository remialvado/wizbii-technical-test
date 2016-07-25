Objectifs
========

Le but de cet exercice est de refaire une petite partie de l'API que nous utilisons en interne pour stocker les mesures de type pageview, screenview ou event.
Cette API reprend les principes de l'API de Google Analytics en ajoutant quelques champs customisés nous permettant de meiux analyser le comportement de nos utilisateurs.

Les consignes de cet exercice :
* respecter la doc de l'API présente sur https://analytics.wizbii.com/doc.html 
* stocker les données dans une base NoSQL, MongoDB de préférence
* réaliser le code Backend en PHP
* le code doit être disponible sur github ou bitbucket. Pas besoin d'avoir une version déployée et fonctionnelle, c'est un plus mais l'objectif est de discuter sur le code
* le choix des frameworks, outils, IDE, ... est laissé à ta convenance

Quelques règles métier à implémenter. Pas besoin de toutes les implémenter, le but est de voir comment elles ont été développées, pas de remplacer notre outil existant :)

1. pour éviter qu'une mesure ne soit collectée plusieurs fois par erreur, on estime qu'un évènement ne peut pas se produire plus d'une fois par seconde
2. si les champs mandatory ne sont pas fournis, l'API doit retourner une erreur : à toi de définir le format de cette erreur.
3. si le champs wci référence un utilisateur qui n'existe pas, l'API doit retourner une erreur. Pour cet exercice, cette liste sera mockée
4. si le champs qt est fourni et est supérieur à 3600, l'API doit retourner une erreur. Cette valeur doit être configurable
5. si la valeur du champs v est différente de 1, l'API doit retourner une erreur.
