---
layout: post
title: Le côté texte du format svg
ref: lecotetextedusvg
date: 2017-05-03 14:48:43.000000000 +02:00
categories:
- fr
tags:
- blog
- software
- web
- basic
- standards
- svg
- wysiwyg
author: 'Alba Marina MÁLAGA SABOGAL'
lang: fr
published: true
---

SVG, c'est un format d'images vectorielles léger et utilisé un peu
partout sur le net. En plus de ses qualités pour le web, c'est un format
accepté par beaucoup de découpeuses laser.

C'est justement en travaillant avec un collègue sur la préparation des
fichiers pour la découpe que j'ai compris qu'il s'agissait d'un format
textuel. A vrai dire je n'avais jamais creusé le sujet auparavant. Je
prenais pour évident que si tout le monde travaillait le svg avec des
interfaces graphiques, c'est que c'était la bonne façon de faire.

Travailler en  interface graphique  sur des fichiers qui sont nativement
dans un format de texte pose problème car on ne garde pas la main sur
tout ce que le fichier contient. A force de faire du WYSIWYG (*what you
see is what you get*), on peut se leurrer et penser WYSIWAG (*what you
see is all you get*).

SVG n'est pas un format WYSIWAG. Par exemple le texte des trois fichiers
SVG suivants qui seront affichés exactement de la même façon laisse voir
que l'un de ces trois exemples est très différent des autres.

\[code language="xml" title="chemin\_absolu.svg"\]  
&lt;?xml version="1.0"?&gt;  
&lt;!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN"  
"http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd"&gt;  
&lt;svg version="1.1" viewBox="-10 -10 280 250"  
xmlns="http://www.w3.org/2000/svg"&gt;  
&lt;path fill="none" stroke="red" d="M 0, 0  
C 0,0 0,100 0,100 C 0,100 30,100 30,100  
C 30,100 30,200 30,200 C 30,200 30,230 30,230  
C 30,230 130,230 130,230 C 130,230 130,200 130,200  
C 130,200 230,200 230,200 C 230,200 260,200 260,200  
C 260,200 260,100 260,100 C 260,100 230,100 230,100  
C 230,100 230, 0 230, 0 z"/&gt;&lt;/svg&gt;  
\[/code\]

[<img src="{{ site.baseurl }}/assets/img/chemin_absolu.svg" alt="Chemin absolu en SVG" class="alignnone size-full wp-image-832" />](http://albamath.com/wp-content/uploads/2017/05/chemin_absolu.svg)

\[code language="xml" title="chemin\_relatif.svg"\]  
&lt;?xml version="1.0"?&gt;  
&lt;!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "h  
ttp://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd"&gt;  
&lt;svg version="1.1" viewBox="-10 -10 280 250"  
xmlns="http://www.w3.org/2000/svg"&gt;  
&lt;path fill="none" stroke="red" d= "M 0, 0  
c 0,0 0, 100 0, 100 c 0,0 30, 0 30, 0  
c 0,0 0, 100 0, 100 c 0,0 0, 30 0, 30  
c 0,0 100, 0 100, 0 c 0,0 0,-30 0,-30  
c 0,0 100, 0 100, 0 c 0,0 30, 0 30, 0  
c 0,0 0,-100 0,-100 c 0,0 -30, 0 -30, 0  
c 0,0 0,-100 0,-100 z" /&gt;  
&lt;/svg&gt;  
\[/code\]

[<img src="{{ site.baseurl }}/assets/img/chemin_relatif.svg" alt="Chemin relatif en SVG" class="alignnone size-full wp-image-831" />](http://albamath.com/wp-content/uploads/2017/05/chemin_relatif.svg)

\[code language="xml" title="polyligne.svg"\]  
&lt;?xml version="1.0"?&gt;  
&lt;!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "h  
ttp://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd"&gt;  
&lt;svg version="1.1" viewBox="-10 -10 280 250"  
xmlns="http://www.w3.org/2000/svg"&gt;  
&lt;polyline fill="none" stroke="red"  
points=" 0, 0  
0,100 30,100  
30,200 30,230  
130,230 130,200  
230,200 260,200  
260,100 230,100  
230, 0 0, 0" /&gt;  
&lt;/svg&gt;  
\[/code\]

[<img src="{{ site.baseurl }}/assets/img/polyligne.svg" alt="Polyligne au format SVG" class="alignnone size-full wp-image-830" />](http://albamath.com/wp-content/uploads/2017/05/polyligne.svg)

En effet la figure dans `polyline.svg` est faite de "vrais" segments de droite, alors que dans les deux autres exemples les pièces dont la figure est construite sont des splines. On a tout fait pour que ces splines aillent tout droit, du coup l'image obtenu a la même tête dans les trois exemples. Mais moralement ce n'EST pas la même image.
