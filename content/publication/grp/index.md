---
abstract: The Gambler's Ruin Problem relates to some of the most beautiful applications in the field of Statistics namely, **Stochastic Processes**, **Random Walks** and **Markov Chains**. The R-Package `gamblers.ruin.gameplay` has been developed for the live visualizations of these concepts through graphical illustrations.

authors:
- admin
date: "2021-04-28T00:00:00Z"
doi: ""
featured: true
image:
  caption: '**CRAN**'
  focal_point: ""
  preview_only: false
links:
- name: CRAN Link
  url: https://cran.r-project.org/package=gamblers.ruin.gameplay
publication: In *Comprehensive R-Archive Network*
publication_short: In *CRAN*
#publication_types:
#- "0"
publishDate: "2021-05-12T00:00:00Z"
#slides: example
summary: Simulates a gambling game under the **gambler's ruin setup**, after asking for the `money you have` and the `money you want to win`, along with your `win probability` in each round of the game.
tags:
- Publications
title: One-Dimensional Random Walks Through Simulation of the Gambler's Ruin Problem using gamblers.ruin.gameplay
#url_code: '#'
#url_dataset: '#'
#url_pdf: http://eprints.soton.ac.uk/352095/1/Cushen-IMV2013.pdf
#url_poster: '#'
#url_project: ""
#url_slides: ""
#url_source: '#'
#url_video: '#'
---

**Beginning with the Gambler's Ruin Problem**

This package development is actually a part of my undergraduate dissertation paper which was concerned to `The Gambler's Ruin Problem - Introducing Games of Chance`. During the course of my research, I came across many real life practical examples of the gambler's ruin problem, which seem to get illustrated and applied in situations apart from gambling. Some of it's dynamic applications are as follows:

* **Google's PageRank Algorithm**
* **Stock Markets and Investment sectors**
* **The SIR and SIS Pandemic Models**
* **Roulette Simulations** and many more...

**What is the Gambler's Ruin Problem ? - Discussing the set up**

Consider a mature man named `Tishyo Chakaraborty`, who enters into a casino one fine day with `x` units of money at his disposal. Because of his close-fisted nature, he agrees to play a game which is structured as follows:

He enters into the game as decided, with `x` units of money to spare. Each round offers him an associated **win probability** of `p` [0 < p < 1], i.e., he wins every round with probability `p`. On winning each round he wins `1 unit` of money, which in turn gets added to his existing sum of capital, and on losing a round with an associated probability of `1-p`, he loses out on `1 unit` of money, which in turn gets deducted from his existing capital.

Tishyo is a very busy person, so he is always in a hurry, as a result of which he decides to quit the game on reaching a capital of worth `x*` units of money, where `x* > x`, and also he has to customarily leave the game if he gets totally ruined or bankrupted, losing out on all his capital. These two junctures are referred to as the **absorbed states** of the game, where the game stops.

The question is **What is the probability that Tishyo will win the entire game ?**. Thus you have the **Gambler's Ruin Problem**.


**The R-Package gamblers.ruin.gameplay**

The package developed, comprises of a function `grp.gameplay()` simulates a game of gambling under the gambler's ruin setup as discussed above, henceforth providing us with a graphical representation of the **trajectory of the gambler's capital at each round of the game**, along with **the number of rounds played and the long-run win probability**.

The user-inputs accepted by the function `grp.gameplay()` is as follows ::

* `ini.stake` :: The initial amount of money with which the gambler enters the game.

* `p` :: A fraction representing the win probability of the gambler in each round of the game.

* `win.amt` :: The amount of money, the gambler wants to reach or win from this game being played or simulated.

Taking inputs for the above defined parameters, the function `grp.gameplay()`, returns the graphical representation of the **One Dimensional** Random Walk made by the gambler during the game trajectory.

**Demonstration of `grp.gameplay()`**

Let us consider that Tishyo enters the game with `40` units of money in his pocket, playing a fair game game, i.e., `p = 0.50` and because of his greedy nature he wants to earn `5000` units of money from the game. Let's see the consequences as it gets simulated.

We run the following code:

> install.packages("gamblers.ruin.gameplay") # Installing the package from CRAN.

> library(gamblers.ruin.gameplay) # Loading the installed package.

> grp.gameplay(40,0.50,5000)

{{< video src="GRP Simulation.mp4" controls="yes" >}}

In the above simulation we can see Tishyo had a hard luck, eventually losing the game. The animation also illustrates Tishyo's **One Dimensional Random Walk** during the course of the game being played by him.

That's it ! Folllowing the similar lines, we can perform many more simulations under this set up, just by altering the parameters involved in the `grp.gameplay()` function. 

{{% callout note %}}
You can click the *Cite* button above, to import publication metadata into your reference management software, i.e., to make a citation of the above publication.

For delving deep into the problem, you can consider reading the paper written on this topic. {{< icon name="semantic-scholar" pack="ai" >}}{{< staticref "media/Somjit Roy_402_HSTDS6043D.pdf" "newtab" >}}Read paper{{< /staticref >}}.

{{% /callout %}}

