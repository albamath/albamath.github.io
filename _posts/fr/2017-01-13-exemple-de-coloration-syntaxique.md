---
layout: post
title: 'Proof  of concept : exemple de coloration syntaxique'
ref: colorationsyntaxique
date: 2017-01-13 16:05:55.000000000 +01:00
tags:
- web
- coloration-syntaxique
- css
- wordpress
author: 'Alba Marina MÁLAGA SABOGAL'
lang: fr
published: true
---

J'ai donné en devoir de mon cours de WordPress de rajouter la coloration syntaxique en utilisant le fichier `style.css` d'un thème et non pas un plug-in. Je viens de le faire sur mon propre blog - dont voici un exemple d'utilisation. Je devrai mettre en ligne une explication plus complète quand mes étudiants m'auront rendu leurs mini-projets.

Exemple de code Java coloré et commenté :

Plutôt que d'utiliser des branchements `if-else` imbriqués, je préfère utiliser un `switch`.

~~~java
switch(choixDuProgramme)
{
    case 0:
        //instructions du premier programme
        break;
    case 1:
        //instructions du deuxième programme
        break;
    case 2:
        //instructions du troisième programme
}
~~~

**Remarque :** Dans ce code il n'y a pas de cas `default` car on s'assure de façon anticipé que la variable `choixDuProgramme` ne prenne que les valeurs `0`, `1` ou `2`.   Normalement il faudrait capturer une `exception` et la traiter mais nous n'avons pas encore travaillé cela en cours.
