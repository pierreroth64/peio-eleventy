---
title: Dev front-end
date: 2016-02-05
tags:
  - code
layout: layouts/post.njk
---

Une petite mise à jour sur mon avancée dans la programmation web: je suis parti à fond les ballons et après avoir dévoré quelques formations en ligne de chez [CodeSchool](https://www.codeschool.com/), je me suis lancé dans la développement d'une petite [SPA](https://fr.wikipedia.org/wiki/Application_web_monopage) permettant de collecter des données [LoRa](https://fr.wikipedia.org/wiki/LoRaWAN) et de les afficher en live. Au passage, j'ai trouvé sympa le service [PubNub](http://www.pubnub.com) (pattern pub/sub) permettant de communiquer d'un bout à l'autre de la planète sans batailler à configurer le NAT des box.

Le résumé ? Et bien cette petite application a pris de l'embonpoint et j'ai pu toucher à plusieurs technos bien sympathiques:

- [backbone.js](http://www.backonejs.org), le framework front-end que j'avais déjà touché en formation chez [Delicious Insights](http://delicious-insights.com/)
- [PubNub](http://www.pubnub.com) qui m'a permis de collecter facilement les données
- [C3js](http://c3js.org/) pour faire de jolis graphes avec les données mises à jour en temps réel
- [Mapbox](https://www.mapbox.com/) pour le tracking de la position des devices sur une carte
- [brunch](http://www.brunch.io) pour tout ce qui est chaîne de build avancée avec tous les plug-ins qui vont bien pour une boucle de feedback ultra-rapide: une petite tuerie cet outil!
- L'écosystème [NPM](https://www.npmjs.com/)...#NoComment #Huge!
- [Mocha](https://mochajs.org/) et [Chai](http://chaijs.com/) pour le test: tout est nickel pour du [TDD](https://fr.wikipedia.org/wiki/Test_driven_development)!

Donc pas mal de boulot et du **code disponible sur Github:** [https://github.com/pierreroth/loraboard](https://github.com/pierreroth/loraboard)

Il reste encore "quelques" trucs à faire...

- Jouer avec un moteur de templates style [Mustache](https://github.com/janl/mustache.js). Ca a l'air tout con (j'avais déjà joué avec [Handlebars](http://handlebarsjs.com/)) mais je n'ai toujours pas compris comment je pouvais importer un template **externe** en js sans avoir à l'insérer de façon bien pourrie dans une balise script...
- Assainir mon environnement de test: pour le moment les libs externes (Backbone, lodash, etc...) dont dépend mon application sont stockés dans mon répertoire _./vendor_ et lorsque je lance mes tests il se réfèrent à l'environnement de Node.js. J'aimerais donc que mon code importe les libs depuis **./node_modules** et virer tout mon _./vendor_ pour ne plus avoir qu'une source de package externes: package.json. Faut que je me penche sur la doc de brunch.
- Voir ce que donne [Marionette](http://marionettejs.com/) pour faire des nested views parce que je n'ai pas tout saisi sur la manière de faire en Backbone.

Voilà, j'ai encore de jolis moments à venir! Assez impatient d'avancer car mon prochain défi c'est de plonger dans l'univers de [Node.js](https://nodejs.org) :)
