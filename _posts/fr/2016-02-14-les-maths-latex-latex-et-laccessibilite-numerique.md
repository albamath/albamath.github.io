---
title: Les maths,  LaTeX et l'accessibilité numérique
ref: latexaccessibiliteatelier
date: 2016-02-14 00:46:18.000000000 +01:00
tags:
- apprentissage
- software
- accesibilite
- handicap
- latex
published: true
---

Je viens aujourd'hui vous raconter une formation sur $$\LaTeX$$ et l'accesibilité numérique que j'ai suivi il y a quelques jours grâce à l'association [BrailleNet](http://www.braillenet.org).

**Pour ceux qui ne connaissent pas**,  $$\LaTeX$$ est LA solution logicielle pour taper du texte mathématique. J'ai appris à l'utiliser il y a dix ans et de poussières. La prise en main n'est pas évidente au premier abord mais il est incontournable lorsqu'on est mathématicien. Un fichier  $$\LaTeX$$ c'est un fichier au format texte qu'on garde avec extension .tex et qu'il faut ensuite compiler pour obtenir un fichier interprétable par une imprimante, comme par exemple pdf.

D'un point de vue numérique, un document **accessible** c'est un fichier tel que tout personne ayant accès au fichier aura accès aux informations y contenues de sorte à pouvoir les interpréter.

Alors comment fait-on pour :

-   qu'un aveugle puissent accéder aux informations données par une image?
    -   On rajoute un texte descriptif détaillé, cette description         pourra être lue par un lecteur d'écran;
    -   on évite de véhiculer une information *uniquement* de façon visuelle.
-   qu'un sourd puissent accéder aux informations contenues dans un podcast?
    -   Le texte descriptif détaillé est une solution possible.
-   qu'un handicapé moteur puisse naviguer dans le texte?
    -   On soigne la structure du texte et on pense à tous ceux pour qui faire un clic de plus est vraiment pénible.
-   qu'un dyslexique lise notre texte sans fatigue?
    -   On évite les polices à empâtement et les espaces variables entre les mots?
-   qu'un malvoyant nous lisent sans problème?
    -   Celle-ci est facile, il suffit d'augmenter la taille du texte.

J'ai préparé un MWE ("minimal working example" c'est à dire petit exemple qui marche)  avec tout ça. Et vous savez quoi? ça m'aide même pour ma propre relecture de moi-même, car sans être malvoyante j'ai un astigmatisme prononcé.

~~~latex
\documentclass[a4paper,17pt]{extarticle}  
%encodage  
\usepackage[utf8]{inputenc}  
\usepackage[T1]{fontenc}  
\usepackage[french]{babel}  
%accessibilité  
\renewcommand{\familydefault}{\sfdefault}  
\renewcommand{\baselinestretch}{1.5}  
\usepackage{hyperref}  
\begin{document}  
\begin{flushleft}  
\section{Exemple de section}  
bla  
\subsection{Exemple de sous-section}  
bla bla  
\end{flushleft}  
\end{document}
~~~

Un exemple de document  $$\LaTeX$$ accessible produit avec ce code :
![Dans cette image, on aperçoit un extrait d&#39;un corrigé d&#39;une feuille d&#39;exercices d&#39;algèbre linéaire. Cette feuille a été produite en suivante diverses recommendations d&#39;accessibilité : police sans empâtements, équations numérotées pour une meilleure navigation, interligne de un et demi, texte non justifié mais aligné à gauche.]({{ site.baseurl }}/assets/exemple-de-latex-accessible.png)

Malheureusement ce code ne permet pas de répondre au soucis des images car  $$\LaTeX$$ n'a pas de moyen de rajouter une "description cachée" aux images. Mais html le permet! Dans html on peut definir une description alternative pour les images on ouvrant la balise comme suit: `<img src="..." alt="..." />` et c'est après `alt` qu'on inscrit la description. Notre formateur était de l'avis que pour un document  $$\LaTeX$$ contenant beaucoup d'images, le mieux est de l'exporter en html et de mettre les descriptions dans le html directement.

Et les formules dans tout ça? Eh, bien c'est le grand flop. Dans un pdf compilé depuis  $$\LaTeX$$ le lecteur d'écran restera muet devant toute formule. Si on arrive à exporter son document en html avec les formules en MathML il existe bien une solution pour lire les formules: [Math Player](http://www.dessci.com/en/products/mathplayer/ 'Math Player'). Mais... il ne marche que sous Internet Explorer (dixit le site officiel); Donc au final apparemment le mieux c'est de compiler son fichier latex avec text4ht (la commande c'est htlatex). Cela transforme toutes les formules en image et ensuite on peut rajouter des descriptions aux images comme expliqué au paragraphe précédent.

En fin, cela n'a pas l'air simple. Mais pour la bonne cause j'essayerai d'améliorer l'accessibilité de mes textes qu'ils soient faits en  $$\LaTeX$$ ou pas. En particulier je me pose beaucoup de questions par rapport à ce blog, il n'a pas l'air très accéssible...

------------------------------------------------------------------------

**Update septembre 2016**

Je travaille aujourd'hui dans un laboratoire spécialisé dans l'accessibilité technologique. J'y donne même un cours de développement pour Wordpress. Beaucoup d'eau a coulé sous les ponts depuis que j'avais posté ce texte.

Si l'accessibilité vous interesse, restez donc à l'affût des nouvelles entrées à ce blog, j'en parlerai souvent dans l'année à venir.

------------------------------------------------------------------------

**Update octobre 2017**

Je travaille aujourd'hui dans le centre de recherche Inria de Paris sur le projet OPALINe et les documents electroniques accessibles sont au coeur de ce projet.
