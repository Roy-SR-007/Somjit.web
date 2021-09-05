---
external_link: ""
#image:
#  caption: '**ggplot2**'
#  focal_point: Smart
#links:
#- icon: github-square
#  icon_pack: fab
#  name: Code Reference
#  url: https://github.com/Roy-SR-007/The-Ant-Trajectory---Illustration-Of-Markov-Chains
summary: A very cool problem portraying the application of `Beta - Binomial Integral`.   
tags: 
- ProblemCorner
title: Subsetting with a Probabilistic Notion
---

**The Question** : Let `n` and `k` be fixed positive integers, and `a` be an arbitary non negative integer. Choose a random `k` - component element subset `X` from {1,2,...,k+a} uniformly (i.e., all possible k - elements subsets are chosen with equal probability). And independently of X, choose at random `n` - elements subset `Y` from {1,2,...,k+a+n} uniformly. Prove that P(min Y > max X) does not depend on a.


**Solution** :

Here we are given that `n` and `k` are fixed positive integers. We have to choose a k - element subset denoted by X, from {1,2,...,k+a} uniformly. 
The number of such subsets are ![](https://latex.codecogs.com/gif.latex?%5Cinline%20%5Cbinom%7Bk&plus;a%7D%7Bk%7D)

