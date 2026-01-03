---
title: Un bon développeur ?
date: 2026-01-03
tags:
  - code
layout: layouts/post.njk
---

_J'ai pris conscience récemment que je n'avais jamais réellement participé à un recrutement "from scratch" (J'entends par là recruter une personne totalement inconnue).
Je me suis décidé à poser quelques réflexions dans ce post.
Je me suis aussi donné un petit défi: donner en une seule phrase ma définition du bon développeur._

## 🤝 Un jour ou l'autre, il faut recruter...

La boîte grossit ou alors quelqu'un part, il faut alors accueillir dans l'équipe une nouvelle recrue.

Mon parcours a fait que j'ai rarement eu à recruter une personne nouvelle.
J'ai toujours fait jouer le réseau.
Dans ma [boîte actuelle](https://www.eove.fr), j'ai eu la chance de faire venir d'excellents développeurs connus d'expériences professionnelles précédentes.
Travailler avec quelqu'un en prestation longue a aussi été l'occasion de "valider le profil" comme disent si bien les RH.
Le recrutement a alors été sans douleur après avoir travaillé plusieurs mois ensemble.

### ...une personne nouvelle

Recruter une personne avec qui on a pu faire connaissance et travailler sur le moyen/long terme, c'est facile.
🔥 Recruter une personne totalement inconnue, c'est... **ultra chaud** ! (en tout cas pour moi 😅)

Car un.e futur.e collègue, ce n'est pas rien: c'est quelqu'un que l'on va côtoyer tous les jours.
Le sujet est délicat car il faut chercher une certaine compatibilité sans toute fois rechercher un semblable car ce serait se priver d'un nouveau regard, de nouvelles approches.
Et le tout en un temps record car la partie cruciale du recrutement, c'est à dire se faire un avis sur le candidat, a lieu lors des entretiens et cette période ne peut pas s'éterniser (notamment pour le bien-être des candidats).

## 📝 Quoi "évaluer" ?

Ca peut paraître évident mais c'est mieux en le disant: un CV c'est nécessaire mais c'est clairement le moins important à mon sens.
Pour ma part, les valeurs sont fondamentales.
Ensuite, le savoir-faire sera le socle sur lequel nous pourrons bâtir ensemble.
J'exclus totalement l'aspect technico-technique (language, framework, etc...) de l'évaluation du candidat: si le savoir-faire logiciel est là, le technique n'est qu'un "détail" car la montée en compétence sur la stack choisie par l'équipe sera une question de semaines (voire de mois) mais elle n'a aucun impact sur mon jugement lors du recrutement.

## 💚 La bonne personne ?

En premier lieu donc, évidemment, des **valeurs** communes.
Sans ça, le mur très rapidement.
Je suis heureux que nous ayons travaillé sur ces valeurs dans notre équipe.
Nous les avons matérialisées sur un [dessin](https://github.com/eove/.github/blob/98b90d781f6bb4dd8038c007e21e40d238018bb2/profile/img/eove-valeurs.png): _"Créativité", "Rigueur", "Engagement", "Respect" et "Entraide"_.
Les valeurs sont très utiles par temps de tempête.
Exemple évident: sur une période de forte charge, l'_entraide_ joue un rôle central chez nous.
Un dev qui n'adhèrerait pas à cette valeur aurait un impact ultra négatif sur le moral de l'équipe.
Il pourrait même participer à déstabiliser la solidarité qui fait notre force.

Et, malheureusement, faute d'avoir un temps conséquent avec le candidat, il est quasi impossible de vérifier à coup sûr que les valeurs sont totalement partagées.

Je suis ~~assez~~ très mauvais dans ce domaine.
Sans être totalement un lapin de 6 semaines, j'ai tout de même du mal à me faire **une idée juste** de l'individu en face de moi en si peu de temps.
J'ai la chance de travailler avec des personnes dont l'intuition est beaucoup plus performante.


## 🛠️ Le bon savoir-faire ?

Comment évaluer le savoir-faire ?

Je n'aime pas du tout le live-coding lors d'un recrutement car il génère trop d'effets de bord indésirables: 
 - quoi coder ensemble en si peu de temps ? Un algo ? -> c'est du technique pur, inutile à mon sens. Un kata ? no comment, un candidat ayant bien répété peut enfumer tout le monde.
 - certains candidats un peu émotifs peuvent perdre leurs moyens devant un parterre de barbus alors que ce sont des gens délicieusement intelligents et capables lors d'interactions plus personnelles (pair-programming par exemple, ou simples discussions autour de sujets concrets)

Nous avons basé nos derniers recrutements sur une session de présentation de code qui m'a bien plu: le candidat choisit une base de code qu'il maîtrise et qu'il apprécie **en amont de l'entretien**. Il a ainsi le temps de se remettre le code en tête, de prendre du recul et d'analyser les forces et faiblesses de son design.

Dans une première partie, il présente sereinement sans être interrompu.
Dans la seconde partie, les devs qui assistent à la présentation peuvent poser des questions.

Il y aurait beaucoup d'aspects à aborder sur le savoir-faire.
Je vais m'attarder sur trois points sur lesquels je suis extrêment vigilant: la **sémantique**, le **découplage** et les **abstractions**.
J'aborderai ensuite ce que j'appelle **"l'accessibilité"**, point de vigilance nouveau qui m'est apparu très récemment.

### La sémantique

Je crois que tout le monde est d'accord sur ce point: bien nommer les choses est crucial.
Et les ratés sur ce plan sont très coûteux.
Donc, à la poubelle les termes de softeux technico-techniques décorellés du métier: les experts du domaine métier connaissent les vrais termes, précis, non ambigüs.
Il faut donc les retrouver dans le code, tout simplement.
Pour chaque terme, bien réfléchir à une définition partagée et devenir un ayatollah pour son utilisation exclusive par la suite sans s'interdire de le changer si sa propagation au sein de l'équipe est chaotique ou poussive: c'est sans doute un signe qu'il n'est pas assez pertinent.

_🕵️ Comment répérer ça dans une base de code d'un candidat ?_
Aucune idée.
Mais, choisir un terme et demander sa définition précise et le lien avec le domaine métier me semble un bon début.

### Le découplage

Nous sommes bien d'accord qu'un code spaghettis 🍝 mêlant technique et métier est rédibitoire.
La séparation du métier (domaine(s)) **essentiel** et de la technique (infra, outillage) **mal nécessaire** est un pré-requis pour le candidat qui me présente son code.
Nous devons nous retrouver autour du découpage _stratégique_ qu'il aura retenu ainsi que sur certains aspects _tactitques_ qu'il aura choisis (architecture hexagonale, clean architecture, etc...) car la bible de notre équipe c'est le [Domain Driven Design (ou DDD)](https://en.wikipedia.org/wiki/Domain-driven_design).

_🕵️ Comment répérer ça dans une base de code d'un candidat ?_
Facile.
Tout effet de bord (persistance sur disque, requête réseau, affichage) devrait être cantonné dans l'infrastructure et injecté dans le métier au runtime.

### Les abstractions

Des objets qui ont trop de responsabilités, c'est ma hantise car ma cervelle est limitée.
Choisir de bonnes abstractions et répartir les responsabilités est essentiel.
Au début c'est facile.
Mais qu'une classe glisse d'un bout de code clair et concis vers un bousin qui fait **beaucoup trop de trucs** est chose courante.

_🕵️ Comment répérer ça dans une base de code d'un candidat ?_
J'ai tendance à penser que: soit il est très soucieux de ces problèmes et si nous tombons sur un tel cas, il précisera rapidement qu'un [refactoring](https://refactoring.com/) est nécessaire sur cette partie de code (en expliquant le pourquoi); soit ce sujet n'est pas suffisamment important à ses yeux et en quelques clics, nous devrions tomber sur une classe un peu trop copieuse.

Me concernant, c'est la raison principale pour laquelle j'apprécie le [Test Driven Development (ou TDD)](https://en.wikipedia.org/wiki/Test-driven_development) qui n'est pas pour moi une méthode pour tester mais bien une aide au design. Lorsque le nouveau cas de test s'aventure sur une responsabilité nouvelle, ça me saute aux yeux.

Comme j'aime écrire de la doc (bizarre le mec...) car c'est une de mes façons d'apprendre, ça fait quelque temps que je fais du `"RDD"` ☺️... du `"README Driven Development"`.
En gros, avant d'attaquer l'implémentation, j'écris le `README` avec un exemple de code présentant l'API que je souhaite exposer via ma nouvelle lib.
J'essaie (non sans mal) de propager ce concept un peu rigolo de `"RDD"` depuis quelque temps... et l'arrivée de Rust dans notre équipe avec sa doc exécutable (et donc à jour !) pourrait m'aider... 😈 

J'ai un concurrent sérieux qui propose du `"CDD"` dans l'équipe 😉 (`"CHANGELOG Driven Development"`)

### L'accessibilité du code métier

J'ai pris conscience récemment que les points mentionnés ci-dessus (sémantique, découplage, abstractions) étaient nécessaires mais pas suffisants.

On peut tout à fait adhérer totalement à ces pratiques tout en écrivant un code qui ne me convienne toujours pas 🙃.

Je n'ai pas trouvé d'autre terme pour parler de cette caractéristique du code qui m'est essentielle: **son accessibilité** (je suis preneur de tout terme plus pertinent).

**Pour faire simple: à quel point le code métier est-il lisible par une personne du métier qui n'est PAS développeur ?**

La _sémantique_ héritée du métier facilite la compréhension, les bonnes _abstractions_ permettent d'organiser les concepts pour ne pas mêler le détail et le général, les aspects techniques masqués assurés par le _découplage_ du métier et de l'infra réduisent fortement le bruit subi par le relecteur du code.

Cependant, malgré ça, il reste des façons de programmer qui complexifient la compréhension du code métier par le spécialiste métier. 

_🕵️ Comment répérer ça dans une base de code d'un candidat ?_
Si toutes les cases sont cochées (sur le DDD notamment) mais que le code reste difficilement compréhensible alors il y a encore quelque chose qui cloche. 
Trop d'indirections, de génériques, de tripaille de softeux ? 
Je suis preneur de retours d'expérience sur ces couacs que vous avez peut-être rencontrés dans du code qui avait pourtant toutes les caractéristiques pour vous séduire.

💡 Une proposition que j'aurai en tout cas lors de notre prochaine session de présentation de code d'un candidat: embarquer une personne non technique qui pourrait avoir un avis pertinent sur la clarté du code métier.


## MA définition du "bon développeur"

J'ai itéré plusieurs fois pour finalement converger vers cette définition.
Je me suis contraint à une seule phrase en essayant d'éviter les termes techniques du monde du logiciel.

_"Un bon développeur adhère furieusement aux valeurs de son équipe et écrit du code évolutif qui peut être massif et dont la partie métier reste facilement compréhensible par un expert du domaine"_


Allez hop je file !
En ce début d'année 2026, j'ai du Rust 🦀 `no-std` à digérer 😅... 
La prochaine session de recrutement pourrait débuter en 2027 ([stay tuned](https://www.linkedin.com/company/eove/))🥳
