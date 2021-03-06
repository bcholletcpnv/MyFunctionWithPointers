# README Projet MA-24

## Introduction

Ce document rédigé dans le cadre du cours "Appui de programmation et outils de développement" dispensé lors du module MA-24, a pour but de présenter et d'analyser une problématique de programmation.

Plus précisemment, ce document va détailler la problématique de l'utilisation des pointeurs en langage C. Quand les utiliser, qu'apportent-ils au langange, etc.

## Analyse de la problématique

Lors de la réalisation du projet "Bataille navale" durant le module MA-20, nous avons pu nous essayer à la réalisation d'une application en C plus ou moins conséquente. Bien que nous disposions des outils amplement nécessaires à la réalisation de ce projet, plusieurs difficultés ont été rencontrées dont certaines pouvant être résolues à l'aide de pointeurs.

Le problème principal et récurrent était l'impossibilité de renvoyer plusieurs valeurs d'une fonction. Souvent, la résolution de cette problématique se résolvait soit dans la création de plusieurs fonctions identiques chacune retournant une valeur unique, soit dans l'utilisation de variable globales.

En parallèle de ce document sera codé une petite application simple mettant en illustration ces différentes alternatives mais également l'usage des pointeurs. Il s'agira d'un "Découpe minutes" devant transformer une valeur entrée par l'utilisateur en nombre d'heure et de minutes.

## Recherches

Jusqu'à maintenant, j'ai toujours réussi à réaliser mes programmes en C en contournant l'utilisation de pointeurs grâce notamment aux variables globales. Cependant, certains enseignants m'ont toujours déconseillé ces dernières. Pourquoi ? C'est donc le sujet de ma première recherche que j'ai naturellement orienté sur "StackOverflow", j'ai aterri sur cette adresse: https://bit.ly/2UgaQa1.
J'y ai donc appris que les variables globales deviennent problématique au fur et à mesure qu'un programme prend de l'ampleur. Une variable globale déclarée implique que je dois regarder chaque fonctions afin de savoir si cette dernière change la valeur de ladite variable. À petite échelle et si je travaille seul, cela reste faisable. Cependant cela devient très vite complexe (voir ingérable) sur un gros projet impliquant plusieurs collaborateurs.

Mais alors, quid des fonctions ? Je peux toujours contourner le problème des pointeurs en déclarant autant de fonction que j'ai besoin de variables retournées. Un des gros avantages des fonctions, c'est qu'elles permettent d'éviter la répétition d'écriture.
À cette adresse sur "Ecomputer Notes": https://bit.ly/2K8ScfT se trouve tous les avantages des fonctions. Toutefois, dans mon exemple, je crée deux fonctions me renvoyant une valeur de type INT. Elles sont redondantes en plus de m'augmenter la taille de mon code et de complexifier sa navigation.

Pour terminer, afin de me renseigner sur la définition des pointeurs, j'ai effectué des recherches sur google. Je suis ainsi tombé sur l'adresse suivante de "Open Classroom": https://bit.ly/2K31JVy.
Non seulement cette source m'a permi de développer mes connaissances sur le sujet (définition, utilisation, etc...), mais elle m'a égalment mis à dispostion un exemple de code utilisant les pointeurs. Exemple dont je vais m'inspirer pour développer mon projet.

## Implémentation

Par mes différentes versions, je vais montrer le même programme codé différemment, cela me permettra d'avoir un retour visuel afin de pouvoir porter un regard plus critiques sur l'optimisation des différentes façons de faire. J'aurai ainsi les versions suivantes:

* Un modèle de ce que j'essaie d'obtenir sans pointeur (Cette version ne fonctionnera donc pas)
* Une version utilisant les variables globales
* Une version dédoublant la fonction _void_ en 2 _int_ afin d'avoir des valeurs _return_
* Une version utilisant les pointeurs

La dernière version sera en vue de gérer les erreurs éventuelles.

## Gestion des erreurs

Puisque mon programme demande une entrée à l'utilisateur, il faut s'assurer de plusieurs chose:

* L'utilisateur entre un entier et __uniquement__ un entier.
* L'utilisateur entre un entier __positif__.
* L'utilisateur ne dépasse pas __la valeur extrême__ d'un entier.

Ces erreurs sont gérées dans la dernières version du programme. Par défaut, j'ai défini la valeur maximale comme étant égale à 1'000'000.
