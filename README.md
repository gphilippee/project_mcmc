# Project MCMC

Authors : Gabriel Escomel, Raphael Walker, Lucas Duchassin, Guillaume Philippe

## Paper

[https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4066005](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4066005)

### Data

> S&P500 returns and option prices for the period January 1, 1996 to December 31, 2015, a total of 5031 trading days.
> [...]. We obtain index returns and risk-free rates from CRSP, and option prices, zero coupon yields, and dividend yields from OptionMetrics.

https://optionmetrics.com/

https://www.crsp.org/products/research-products/crsp-us-stock-databases

### Model

> Our methodology relies on the particle MCMC framework [...] This approach reduces the dimensionality of the MCMC algorithm by using MCMC for parameter inference, while applying particle filter to filter the latent states

### SSMs

> The state-space representation applies regardless of whether we observe returns, options, or both. When returns are the observables, f1 refers to equation (6); when options are the observables, f1 is given by equation (8). For the persistent latent variance Vt, f2 represents equation (7); for the non-persistent jump variable, f2 is simply a random draw from the corresponding distribution. [...] We start with the simplest model, the
Heston (1993) stochastic volatility model (SV). We then discuss the model with return jumps (SVJR), the model with variance jumps (SVJV), and the model with correlated return and variance jumps (SVCJ).

Transition density :
$$f_2(L_{t+1}|L_t)$$

Measurement density :
$$f_1(Y_{t+1}|L_{t+1})$$

### Results of the paper

> Our empirical implementation focuses on joint estimation with returns and option data


## Data



## Instructions

Répliquer certains de leurs résultats, en utilisant les mêmes données (SP500, faciles à trouver sur internet). Vous pouvez notamment :

1. implémenter un bootstrap filter pour le modèle considéré (en fixant le vecteur theta des paramètres à une valeur raisonnable);

2. implémenter un algorithme de type PMMH pour estimer le paramètre theta; l'article parle d'une version "adaptive", où on apprend progressivement la matrice de covariance de la loi de proposition (une marche aléatoire gaussienne); notez que c'est déjà implémenté dans particles, si vous voulez l'utiliser.

3. Si vous avez le temps, comparez la performance de ce PMMH à l'approche proposée dans cet article (orthogonal MCMC); vous pouvez aussi ajouter $$SMC^2$$ à la comparaison (encore une fois si vous avez le temps).

Pour vous simplifier la tâche, n'hésitez à procéder par étapes, par exemple en fixant certains paramètres pour commencer (dans l'étape 2, pour réduire le nombre de paramètres à estimer). Si vous avez des questions, n'hésitez pas à me contacter. Je mets ci-dessous des consignes générales.

## General recommendations

Try to form groups of 4. You are expected to write a small report of about 5 pages (excluding the appendix) on your findings; please attach your programs to this report. Please send the report no later than 2 Jan 2023 by e-mail. (Any later sending will be penalised.) You are also expected to do a 15 minute oral presentation during the lecture on Fri 6 January. Whatever you do, please show some common sense. By construction, the results of a Monte Carlo algorithm are random, and it is important to evaluate what is the variability of your results. For instance, you may run 10 times a given algorithm, and report some measure of variability of certain results. Please explain carefully your results. Plots are always clearer to read than tables. As I told you during the course, my own Python package for particle filtering is on Github: https://github.com/nchopin/particles. It is really up to you whether you use it or not for your project; i.e. you may ignore it completely, look at it to take some inspiration and/or copy/paste certain parts, or even submit your project by doing a "pull request" on Github.
