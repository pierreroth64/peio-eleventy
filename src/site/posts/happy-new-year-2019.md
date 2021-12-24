---
title: Happy new year 2019!
date: 2019-01-03
tags:
  - code
layout: layouts/post.njk
---

## Bona annada / Happy new year / Bonne année !

<div class="flex justify-center">
  <img class="max-w-xl post-img" src="/static/img/bona-annada.jpg">
</div>

Pfiou !!! ça fait un bon bout de temps que je n'ai rien écrit ici: depuis fin 2016, la vie a été mouvementée ;) avec la naissance de mon second fiston (2 garçons à la maison, ça booste! :rocket: ), un changement de boîte ([Legrand](http://www.legrand.fr) => [Eove](http://www.eove.fr)) et donc de nouveaux challenges humains et techniques. Je ne vais pas trop rentrer dans les détails mais voici les grandes lignes pour rattraper mon retard sur presque 2 années silencieuses sur ce blog.

## Une rencontre

Au printemps 2017, je ne sais pas ce qui m'a pris mais j'ai osé. J'ai appelé [Arpinum](https://www.arpinum.fr/) à la rescousse. Certainement un peu inquiet face à l'immensité des choses à faire, à l'état du legacy, au changement de stack technique (étant le seul à la connaître un peu), à la culture un peu "bricolo", je me suis décidé. Depuis longtemps déjà je connaissais ces "énergumènes" via quelques talks dans des agiles tours.

Rencontre chez eux à Bordeaux pour parler de notre produit à venir. Dès le début, **gros coup de coeur me concernant** :heart_eyes:.Excellence technique radicale et forte orientation métier avec du [DDD](https://en.wikipedia.org/wiki/Domain-driven_design) omniprésent. Je profite de ce modeste post pour remercier [Michael](https://michaelborde.fr) qui nous a accompagnés pendant près d'un an et pris les rôles simultanés de développeur et de CTO. Bienveillance, compétence, transmission. Michael si tu tombes par hasard sur ces quelques lignes, j'espère avoir la chance de travailler à nouveau avec toi, c'était chouette ;)

Au passage, chers lecteurs, n'hésitez pas à suivre les 3 autres compères: [Charles](https://twitter.com/charlesco), [Jean-Baptiste, aka @BodySplash](https://twitter.com/BodySplash) et [Arnaud, aka @Lilobase](https://twitter.com/Lilobase) notamment pour ses talks brillants. J'aime particulièrement _"Et si on redémarrait l'agile?"_ ([vidéo ici](https://www.facebook.com/Agiletourbordeaux/videos/263415924530627/))

## L'écosystème technique

Nous sommes une toute petite équipe de dev [@eove](https://www.eove.fr) et les besoins sont multiples pour bâtir de toutes pièces des [respirateurs artificiels](http://eove.fr/cms/produits-et-support/eo-150-ventilator/) pour personnes ventilo-dépendantes. Face cette variété de besoins, notre équipe a fait le choix d'investir sur une techno qui permet d'appréhender quasiment l'ensemble des sujets: le **Javascript** avec:

- pour le dev sur tablette et mobile pour l'interface utilisateur: [React Native](https://facebook.github.io/react-native/)
- pour le dev d'outils desktops: [Electron](http://www.electronjs.org) et [React](https://reactjs.org/)
- pour le dev de scripts en CLI: [Node.js](http://www.nodejs.org)
- pour le dev d'interface web et backend associé [React](https://reactjs.org/) et [Node.js](http://www.nodejs.org)

Le seul développement qui reste en Language C est le firmware du module de ventilation qui tourne sur une petite architecture 16 bits de ST Micro Electronics.

**Mon nouvel écosystème de prédilection est donc maintenant le Javascript** et je dois avouer que je me régale. La productivité est énorme et la qualité peut être là si on suit le bon chemin: [DDD](https://en.wikipedia.org/wiki/Domain-driven_design) et pratiques d'[XP](https://en.wikipedia.org/wiki/Extreme_programming) ([TDD](https://en.wikipedia.org/wiki/Test-driven_development) notamment,....oui je sais je rabâche mais c'est l'âge)

## Mes réalisations

Me concernant, j'ai pas mal bossé sur une **application desktop destinée à parler aux différents modules de ventilation** via USB. Elle permet aux gars du système de mettre au point la ventilation et de batailler sur les courbes de pression, volume, débit.

Modules utilisés: _electronjs, react, react-redux, redux, redux-sagas, rxjs, serialport_

Comme d'habitude, bien entendu: **test first**

<div class="flex justify-center">
  <img class="max-w-3xl post-img" src="/static/img/test-toolkit.gif">
</div>

J'ai aussi réécrit **une application de test de cartes électroniques en CLI** utilisée par les hardeux et nos sous-traitants électroniques pour le test de fin de ligne. Un petit soft embarqué (Merci Manu) propose une API via USB et les tests s'appuient sur cette interface pour diagnostiquer le bon câblage des composants.

Modules utilisés: _node, inquirer, commander, rxjs, serialport, puppeteer_

Enfin, j'ai pris ma part au sein de l'équipe dans le développement de **l'application tablette pour notre nouveau produit**: un assistant de toux. Beaucoup de React Native (JS) et un peu de natif (Java Android) pour quelques parties d'accès au système.

Modules utilisés: _react native, react, react-redux, redux, redux-sagas, rxjs, serialport_

Ouf ! Du taf, beaucoup de taf. Mais tout de même extrêment facilité par le choix d'un écosystème technique commun.

## La suite ?

### L'apprentissage... toujours et encore !

C'est mon quotidien, le quotidien de tout développeur passionné qui ne se résigne pas à son état d'expert beginner (lire ["Les phases du programmeur"](https://www.arpinum.fr/2014/04/08/les-phases-du-programmeur/) de Jean-Baptiste).

Donc au programme de cette année (ça risque de changer dans les semaines à venir):

  - Approfondir DDD: je vais me tenter une petite formation chez [Arolla](http://www.arolla.fr/) ou [Zenika](https://www.zenika.com/) ?
  - Une petite conf pour s'aérer, s'inspirer: [dotJS](https://www.dotjs.io/) ?
  - Et du purement technique:
    - [typescript](https://www.typescriptlang.org/) parce que "les types c'est super pratique"
    - [rxjs](http://reactivex.io/) parce que c'est trop puissant ce truc là

### Les softs à écrire / maintenir

Je vais bien entendu continuer sur l'appli React Native pour l'assistant de toux avec de nouvelles fonctionnalités sympas à venir.

Les sujets de ce début d'année seront cependant le développement d'une stack de communication avec des analyseurs de gaz (air, O2, etc...) de chez IMT Medical pour intégration à nos outils de tests et de mise au point. Le tout en open source et première lib en typescript.

Voici les dépôts concernés:

- [flow-analyzer-com](https://github.com/eove/flow-analyzer-com): lib de communication avec les analyseurs citrex et pf300
- [talk-to-analyzer](https://github.com/eove/talk-to-analyzer): CLI se basant sur la lib précédente

Vous l'avez compris, une année bien "épaisse" à venir !
