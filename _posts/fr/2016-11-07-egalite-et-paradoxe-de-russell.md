---
title: Égalité et paradoxe de Russell
ref: egaliteetparadoxederussell
date: 2016-11-07 22:17:55.000000000 +01:00
tags:
- logique et théorie des ensembles
- egalite
- ensembles
- paradoxe
- Russell
published: true
---

Je voudrais vous parler de l'égalité. Je suis complètement claquée – c'est le type de choses auxquelles je pense quand je suis très fatiguée.

Bon, voyons l'égalité. L'égalité est une relation, en quelque sorte, universelle – deux choses sont égales ou ne sont pas égales. Mais ça veut dire quoi égales ?

En première approche, on pourrait dire que deux choses sont égales si et seulement si elles ont exactement les mêmes caractéristiques. Ok, cette définition est cohérente, mais a un grand défaut : elle est complètement inutile. En effet, si on considère être soi-même comme une caractéristique, alors avec cette définition une chose ne pourrait être égale qu'à elle même.

En pratique – aussi bien en mathématiques qu'en informatique – ce ne sont pas toutes les caractéristiques des choses qui nous intéresse. Par exemple on considère souvent les noms des choses comme superflus.

En règle générale, quand on écrit $$x = y$$ cela ne veut absolument pas dire que $$x$$ et $$y$$ sont devenues une seule et mème lettre de l'alphabet. Ça veut juste dire que les choses nommées $$x$$ et $$y$$ ont suffisemment de caractéristiques communes pour qu'en pratique on les considère comme identiques.

Un exemple fondamental est celui de l'égalité entre ensembles. Dans la théorie axiomatique de Zermelo-Fraenkel, l'axiome d'extensionnalité dit qu'un ensemble est determiné par ses éléments. Autrement dit, deux ensembles sont égaux si, et seulement si, ils possèdent les mêmes éléments.

L'ensemble vide est égal à l'ensemble de tous les lutins irlandais qui habitent sur la lune – peu importe que j'aie utilisée une description beaucoup plus longue pour le deuxième ensemble.

L'ensemble des nombres divisibles par trois est égal à l'ensemble des nombres qui sont multiples de trois.

Notons qu'un ensemble peut à priori être son propre élément. Par exemple, l'ensemble $$U$$ de tous les ensembles appartient forcement à lui même.

Considérons maintenant l'ensemble $$W$$ de tous les ensembles qui, au contraire de $$U$$ n'appartiennent pas à eux-mêmes. Est-ce que $$W$$ appartient à $$W$$ ?

Si $$W\in W$$ alors $$W\not\in W$$ puisque $$W$$ a comme éléments précisement les ensembles qui n'appartiennent pas à eux mêmes.   Si $$W \not\in W$$ alors $$W\in W$$ puisque $$W$$ a comme éléments précisement les ensembles qui n'appartiennent pas à eux mêmes.

Quoi ? Une chose est vraie ( $$W \in W$$ ) si, et seulement si, elle n'est pas vraie ( $$ W\not\in W$$ ) ? C'est quoi ce desordre? Ce bordel ? Ce …paradoxe ?

Ha ha ! Je vois vos têtes là. Ce que je viens d'exposer, c'est le **paradoxe de Russell** dans toute sa splendeur. Si vous ne le connaissiez pas avant, je vous conseille de fouiller un peu, c'est un paradoxe simple mais tentaculaire - vous le retrouverez ailleurs sous d'autres formes.

Le desordre que le paradoxe de Russell pourrait amener dans les maths est bloqué par l'axiome de compréhension de la théorie axiomatique des ensembles de Zermelo-Fraenkel. Cet axiome dit essentiellement qu'à chaque fois qu'on défini un ensemble par les propriétés satisfaites par ces éléments (définition par compréhension) , on a le droit de le faire comme sous-ensemble d'un ensemble existant.

Le paradoxe de Russell est alors évité en montrant que l'ensemble universel n'existe pas. Voyons de plus près :

**Proposition** Dans la théorie axiomatique des ensembles, il ne peut pas y avoir d'ensemble universel, c'est à dire d'ensemble dans lequel tous les autres ensembles seraient inclus ( et qui, par conséquent aurait chaque ensemble, y compris lui-même, comme élément.)

**Preuve** Si un tel ensemble existait, appelons le $$U$$, on pourrait considérer l'ensemble $$W$$ de tous les éléments de $$U$$ qui n'appartient pas à eux-mêmes. Le raisonnement du paradoxe de Russell nous mène alors droit à une contradiction. On conclut donc que $$U$$ n'existe pas.

Et là j'arrête, car j'arrive enfin chez moi. L'égalité en informatique restera comme sujet pour un autre jour…
