---
title: Tester avec robotframework
date: 2016-03-03
tags:
  - code
layout: layouts/post.njk
---

# Tester ?

"Ah le test... on devrait tous... ah si j'avais le temps..." non mais _vous rigolez là_ j'espère!

Le test c'est OBLIGATOIRE en 2016 et je vous signale juste que l'intégration continue c'est maintenant acté depuis des années et qu'on est maintenant à l'heure du déploiement continu ! Bon, faut donc faire du test. Je dirais même qu'il faut l'écrire avant même votre première ligne de code.

Mais c'est surtout pas évident à mettre en oeuvre et à maintenir. J'ai publié sur github un petit template/skeleton permettant de démarrer rapidement avec l'outil [robotframework](http://www.robotframework.org). Désolé pour les djeun's, j'ai pas pu m'empêcher d'encapsuler les commandes de base dans un bon vieux makefile... oui je sais... mais j'aime bien.

# Le code

Il est ici: [https://github.com/pierreroth64/robotframework-template](https://github.com/pierreroth64/robotframework-template)

Je ne m'étendrai pas sur une description parce que RTFM et Pull Request si pas content mais j'ai même pensé à mes collègues de l'embarqué qui pourront mettre dans le script _01_setup..._ leur code de mise à jour des firmwares du SUT (System Under Test) avant de lancer leur campagne.

Dernière précision, le launcher python sous-jacent n'est là que pour parer aux petites limitations des options _--exclude_ et _--include_ de la commande _pybot_ (CLI robotframework)
