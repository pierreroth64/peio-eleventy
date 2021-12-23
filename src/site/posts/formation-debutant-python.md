---
title: Formation Python Débutants
date: 2016-02-29
tags:
  - code
layout: layouts/post.njk
---

Aujourd'hui, petit retour sur la formation Python que j'ai dispensée à l'entreprise [Eove](http://www.eove.fr).

## Les apprenants

Le challenge était de tailler une formation sur mesure pour deux profils "débutants" un peu différents:

- Un systémier, expert dans son métier (la ventilation respiratoire) ayant déjà codé ou assisté un développeur C pour injecter des algorthimes dans l'application.
- Un ingé de validation, déjà sensibilisé au langage C et responsable de la validation _manuelle_ du système

Tous les deux débutants et très avides d'apprendre les bases de Python.

## L'objectif

La validation du produit est une tâche fastidieuse et non reproductible car manuelle. Pour capitaliser et être capable de jouer une campagne de test de manière complètement automatique, ils ont l'ambition de produires des scripts de tests et de les faire jouer à leur intégration continue (basée sur Jenkins).

Le framework de test envisagé est [Robotframework](http://www.robotframework.org) et cet outil étant facilement interfacçable avec du Python, ils se sont naturellement tourné vers ce langage.

Mon but était donc de leur dispenser une formation Python ciblée, sur deux jours, permettant de prendre en main Python et d'aller un peu plus loin sur certain sujet dont le Clean Code pour ne pas produire des kilos de code de test inmaintenables.

## La présentation

La _présentation_ est disponible [ici](http://slides.com/pierreroth64/python-startup) et le _code_ des exemples associés [là](https://github.com/pierreroth64/python-startup).

<div class="flex justify-center">
  <iframe src="//slides.com/pierreroth64/python-startup/embed" width="576" height="420" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>
</div>

## Le bilan

Je ne sais pas (encore) si les apprenants ont été satisfaits. Pendant un jour et demi, on a parlé des bases de Python et la dernière demi-journée a été consacrée au refactoring total de l'application développée avec ajout des tests et autre choses _i.n.d.i.s.p.e.n.s.a.b.l.e.s !_

