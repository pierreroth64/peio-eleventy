---
title: Application fullstack
date: 2016-12-23
tags:
  - code
layout: layouts/post.njk
---

Mon dernier post date de plus de 9 mois ! Je profite d'un peu de calme en cette fin d'année (\*) pour faire un petit point... parce qu'il s'en est passé des choses côté dev ! Je vais donc présenter ici l'ensemble des technos que j'ai mises en oeuvre sur un projet réel dont les sources resteront confidentielles... loyauté envers mon ancien employeur - [Legrand](http://www.legrand.com) - oblige.

## Le sujet et son historique

J'ai participé en 2012 à la définition d'une API REST permettant aux appareils connectés installés chez le client de s'enregistrer sur un portail et de récupérer une mise à jour logicielle. J'étais [Product owner](<https://fr.wikipedia.org/wiki/Scrum_(m%C3%A9thode)#Propri.C3.A9taire_du_produit>) du produit, un prestataire de service a implémenté une première solution basée sur Drupal/MySQL. Le service ayant été très peu sollicité jusqu'en 2015, les problèmes de performance sont apparus en juin 2016 avec un nombre croissant d'appareils se présentant sur le portail. Je vous évite les détails mais en gros, le bousin ne tenait que 3 produits par minute... et encore si les 3 séquences de requêtes ne s'entrelaçaient pas! **La cata**. Note pour plus tard: les tests de performance sont à intégrer dès le début dans l'intégration continue.

En juin, pendant que la hiérarchie se débat avec des meetings à 16 personnes sur le comment on pourrait s'y prendre, on décide avec mon collègue et ami [Fabien](https://github.com/fribes) de ré-implémenter le tout en Node.js. Je vais donc présenter les différentes technos mises en oeuvre.

## Node.js, ExpressJS, MongoDB

Côté backend, je n'ai pas hésité longtemps: [ExpressJS](http://www.expressjs.com) bien entendu et **direct de chez direct mise en place des tests**. Dès le 2ième commit - sur un total de 687 à la 1ière mise en production - setup pour faire du TDD, cf. _44a1df4_ :

<div class="flex justify-center">
  <img class="max-w-3xl post-img" src="/static/img/smartool-git-log.png">
</div>

Pour la bdd, le modèle de données étant assez simple et se prêtant très bien au modèle document (c'est à dire sans x jointures), le choix s'est porté sur MongoDB et son driver pour JS [Mongoose](http://mongoosejs.com/)

## Testing

Pour le test du backend écrit en Node.js (ExpressJS), utilisation de [Mocha](https://mochajs.org/) pour le runner, de [supertest](https://github.com/visionmedia/supertest) pour les assertions sur les retours de l'API HTTP et de [chaijs](http://chaijs.com/) pour les assertions simples.

Le démarrage et l'arrêt propre du runner de test et de la base de données a été scripté en bash... puis j'ai vite utilisé [pm2](https://github.com/Unitech/pm2) derrière un script NPM.

<div class="flex justify-center">
  <img class="max-w-3xl post-img" src="/static/img/smartool-testing.gif">
</div>

## Frontend with React

Après avoir pas mal travaillé sur le backend, il ne restait qu'un pas pour fournir un front digne de 2016 (je ne vous montrerai pas les copies d'écran old-school de la version drupal). [React](https://github.com/facebook/react) s'est imposé naturellement. "Petite" librairie de rendering développé par une "petite" société américaine connue sous le nom de... facebook ;-). Bon ben là, re-claque avec cette petite tuerie pour faire des pages ultra-classes. Moi qui ai souvent souffert sur les interfaces graphiques, c'est passé tout seul avec une prise en main très rapide. Pour ceux qui font du react, je ne peux que conseiller [Material UI](http://www.material-ui.com/) qui propose une liste de composants de super qualité. Au final, une Single Page App dont je suis assez fier pour un débutant avec utilisation des [JWT](https://jwt.io/) pour sécuriser le tout.

## Webpack

Côté front, pour faire ça bien j'ai utilisé [webpack](https://webpack.github.io/). Pas facile à mettre en oeuvre mais on trouve des boilerplates assez facilement. Il parse, transpile (via plugin Babel), crée un joli bundle, etc... il fait tout ce truc. Dingue mais documentation de merde. Heureuseuement que la communauté semble prendre le sujet à bras le corps. Et vous savez quoi ? Il dispose d'un petit server web de dev qui fait du hot-reload sur changement de code. Plus besoin de faire un refresh de la page... #SoCooooool !

## Conclusion

La solution mise en production tient ~ 6000 appareils à la minute (soit un gain d'un facteur 2000 par rapport à la solution précédente) et j'ai énormément appris. La suite ? Utiliser [ReduxJS](http://redux.js.org/) pour la gestion de l'état. Ecrit par [Dan Abramov](https://twitter.com/dan_abramov), ce truc est fabuleux et s'inspire de la programmaton fonctionnelle pour maîtriser les changements d'état (immutabilité). La doc est vraiment chouette et cette machine à produire qu'est Dan met aussi à disposition des tutos vidéos sur [egghead.io](http://www.egghead.io).

(\*) Et oui, fin 2016 j'ai eu quelques changements importants: naissance de mon deuxième fiston et changement de job (J'ai quitté [Legrand](http://www.legrand.com) pour une plus petite structure: [Eove](http://www.eove.fr))
