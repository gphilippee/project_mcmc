# Project MCMC

Authors : Gabriel Escomel, Raphael Walker, Lucas Duchassin, Guillaume Philippe

## Paper

[https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4066005](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4066005)

## Instructions

Répliquer certains de leurs résultats, en utilisant les mêmes données (SP500, faciles à trouver sur internet). Vous pouvez notamment :

1. implémenter un bootstrap filter pour le modèle considéré (en fixant le vecteur theta des paramètres à une valeur raisonnable);

2. implémenter un algorithme de type PMMH pour estimer le paramètre theta; l'article parle d'une version "adaptive", où on apprend progressivement la matrice de covariance de la loi de proposition (une marche aléatoire gaussienne); notez que c'est déjà implémenté dans particles, si vous voulez l'utiliser.

3. Si vous avez le temps, comparez la performance de ce PMMH à l'approche proposée dans cet article (orthogonal MCMC); vous pouvez aussi ajouter $$SMC^2$$ à la comparaison (encore une fois si vous avez le temps).

Pour vous simplifier la tâche, n'hésitez à procéder par étapes, par exemple en fixant certains paramètres pour commencer (dans l'étape 2, pour réduire le nombre de paramètres à estimer). Si vous avez des questions, n'hésitez pas à me contacter. Je mets ci-dessous des consignes générales.

## General recommendations

Try to form groups of 4. You are expected to write a small report of about 5 pages (excluding the appendix) on your findings; please attach your programs to this report. Please send the report no later than 2 Jan 2023 by e-mail. (Any later sending will be penalised.) You are also expected to do a 15 minute oral presentation during the lecture on Fri 6 January. Whatever you do, please show some common sense. By construction, the results of a Monte Carlo algorithm are random, and it is important to evaluate what is the variability of your results. For instance, you may run 10 times a given algorithm, and report some measure of variability of certain results. Please explain carefully your results. Plots are always clearer to read than tables. As I told you during the course, my own Python package for particle filtering is on Github: https://github.com/nchopin/particles. It is really up to you whether you use it or not for your project; i.e. you may ignore it completely, look at it to take some inspiration and/or copy/paste certain parts, or even submit your project by doing a "pull request" on Github.
