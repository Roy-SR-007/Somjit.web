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

Here we are given that `n` and `k` are fixed positive integers. 

We have to choose a k - element subset denoted by X, from {1,2,...,k+a} uniformly. 

The number of such subsets are ![](https://latex.codecogs.com/gif.latex?%5Cbinom%7Bk&plus;a%7D%7Bk%7D)

Similarly, we are choosing a n - element subset denoted by Y from {1,2,...,n+k+a} uniformly.

The number of such subsets are
![](https://latex.codecogs.com/gif.latex?%5Cbinom%7Bn&plus;k&plus;a%7D%7Bn%7D)

Now we need to find the following probability,

![](https://latex.codecogs.com/gif.latex?%5Cmathbb%7BP%7D%28min%28Y%29%20%3E%20max%28X%29%29%20%3D%20%5Csum_%7Bm%3Dk%7D%5E%7Bk&plus;a%7D%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%2Cmax%28X%29%3Dm%29)

> **We note that, here the range of the variable `m` controlling X is from `k` to `k+a`**.

> We use the following, 

> ![](https://latex.codecogs.com/gif.latex?%5Cmathbb%7BP%7D%28A%5Ccap%20B%29%20%3D%20%5Cmathbb%7BP%7D%28A%7CB%29%5Cmathbb%7BP%7D%28B%29)

>

Hence, we get,

![](https://latex.codecogs.com/gif.latex?%5CRightarrow%20%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%29%3D%5Csum_%7Bm%3Dk%7D%5E%7Bk&plus;a%7D%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%7Cmax%28X%29%3Dm%29%5Cmathbb%7BP%7D%28max%28X%29%3Dm%29)

![](https://latex.codecogs.com/gif.latex?%5CRightarrow%20%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%29%3D%5Csum_%7Bm%3Dk%7D%5E%7Bk&plus;a%7D%5Cmathbb%7BP%7D%28min%28Y%29%3Em%29%5Cmathbb%7BP%7D%28max%28X%29%3Dm%29)

Now, we can easily observe that, P(max(X) = m) implies that, P{m is in the randomly chosen subset X and the rest `k-1` many elements that is there in the subset X are chosen from (1,2,...,m-1)}, hence,

![](https://latex.codecogs.com/gif.latex?%5CRightarrow%20%5Cmathbb%7BP%7D%28max%28X%29%3Dm%29%3D%5Cfrac%7B%5Cbinom%7Bm-1%7D%7Bk-1%7D%7D%7B%5Cbinom%7Bk&plus;a%7D%7Bk%7D%7D)

Following a very similar logic, we can clearly observe that, P(min(Y) > m) implies that, P{all the elements in the subset Y are from (m+1,...,n+k+a)}, hence, 

![](https://latex.codecogs.com/gif.latex?%5CRightarrow%20%5Cmathbb%7BP%7D%28min%28Y%29%3Em%29%3D%5Cfrac%7B%5Cbinom%7Bn&plus;k&plus;a-m%7D%7Bn%7D%7D%7B%5Cbinom%7Bn&plus;k&plus;a%7D%7Bn%7D%7D)

![](https://latex.codecogs.com/gif.latex?%5Ctherefore%20%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%29%3D%5Csum_%7Bm%3Dk%7D%5E%7Bk&plus;a%7D%5Cfrac%7B%5Cbinom%7Bn&plus;k&plus;a-m%7D%7Bn%7D%7D%7B%5Cbinom%7Bn&plus;k&plus;a%7D%7Bn%7D%7D.%5Cfrac%7B%5Cbinom%7Bm-1%7D%7Bk-1%7D%7D%7B%5Cbinom%7Bk&plus;a%7D%7Bk%7D%7D)

Expanding the combinatorial identities inside the summation and simplifying, we get,

![]()

Let us take `m - k = i`. Then,

![](https://latex.codecogs.com/gif.latex?%5CRightarrow%20%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%29%3Dk%5Csum_%7Bi%3D0%7D%5E%7Ba%7D%5Cfrac%7B%28i&plus;k-1%29%21%28n&plus;a-i%29%21%7D%7Bi%21%28a-i%29%21%7D.%5Cfrac%7Ba%21%7D%7B%28n&plus;k&plus;a%29%21%7D)

![](https://latex.codecogs.com/gif.latex?%5CRightarrow%20%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%29%3Dk%5Csum_%7Bi%3D0%7D%5E%7Ba%7D%5Cbinom%7Ba%7D%7Bi%7D%5Cfrac%7B%28i&plus;k-1%29%21%28n&plus;a-i%29%21%7D%7B%28n&plus;k&plus;a%29%21%7D)

> We know that, for `n` being a natural number, we have,

> ![](https://latex.codecogs.com/gif.latex?%5CGamma%20%28n%29%20%3D%20%28n-1%29%21)
>

Using the above form of the gamma function, we get,

![](https://latex.codecogs.com/gif.latex?%5CRightarrow%20%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%29%3Dk%5Csum_%7Bi%3D0%7D%5E%7Ba%7D%5Cbinom%7Ba%7D%7Bi%7D%5Cfrac%7B%5CGamma%7B%28i&plus;k%29%7D%5CGamma%7B%28n&plus;a-i&plus;1%29%7D%7D%7B%5CGamma%7B%28n&plus;k&plus;a&plus;1%29%7D%7D)

> From the Beta Function, we know that,

> ![](https://latex.codecogs.com/gif.latex?B%28m%2Cn%29%20%3D%20%5Cfrac%7B%5CGamma%7B%28m%29%5CGamma%7B%28n%29%7D%7D%7D%7B%5CGamma%7B%28m&plus;n%29%7D%7D)
>

Hence, we get,

![](https://latex.codecogs.com/gif.latex?%5CRightarrow%20%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%29%3Dk%5Csum_%7Bi%3D0%7D%5E%7Ba%7D%5Cbinom%7Ba%7D%7Bi%7DB%28i&plus;k%2Cn&plus;a-i&plus;1%29)

> Also the Beta Integral of the First Kind is given by,

> ![](https://latex.codecogs.com/gif.latex?B%28m%2Cn%29%20%3D%20%5Cint_%7B0%7D%5E%7B1%7Dx%5E%7Bm-1%7D%281-x%29%5E%7Bn-1%7Ddx)
>

![](https://latex.codecogs.com/gif.latex?%5CRightarrow%20%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%29%3Dk%5Csum_%7Bi%3D0%7D%5E%7Ba%7D%5Cbinom%7Ba%7D%7Bi%7D%5Cint_%7B0%7D%5E%7B1%7Dx%5E%7Bi&plus;k-1%7D%281-x%29%5E%7Bn&plus;a-i%7Ddx)

**We can interchange the sum and the integral, as the terms are `non-negative`.**

![](https://latex.codecogs.com/gif.latex?%5CRightarrow%20%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%29%3Dk%5Cint_%7B0%7D%5E%7B1%7D%5Csum_%7Bi%3D0%7D%5E%7Ba%7D%5Cbinom%7Ba%7D%7Bi%7Dx%5E%7Bi&plus;k-1%7D%281-x%29%5E%7Bn&plus;a-i%7Ddx)

![](https://latex.codecogs.com/gif.latex?%5CRightarrow%20%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%29%3Dk%5Cint_%7B0%7D%5E%7B1%7Dx%5E%7Bk-1%7D%281-x%29%5E%7Bn%7D%5Csum_%7Bi%3D0%7D%5E%7Ba%7D%5Cbinom%7Ba%7D%7Bi%7Dx%5E%7Bi%7D%281-x%29%5E%7Ba-i%7Ddx)

> Note that, 

> ![](https://latex.codecogs.com/gif.latex?%5Csum_%7Bi%3D0%7D%5E%7Ba%7D%5Cbinom%7Ba%7D%7Bi%7Dx%5E%7Bi%7D%281-x%29%5E%7Ba-i%7D%20%3D%20%28x&plus;1-x%29%5Ea%20%3D%201)

> The above is a **Binomial Coefficient**.
>

Hence, we finally obtain,

![](https://latex.codecogs.com/gif.latex?%5CRightarrow%20%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%29%3Dk%5Cint_%7B0%7D%5E%7B1%7Dx%5E%7Bk-1%7D%281-x%29%5E%7Bn%7Ddx%3DkB%28k-1%2Cn&plus;1%29)

![](https://latex.codecogs.com/gif.latex?%5Ctherefore%20%5Cmathbb%7BP%7D%28min%28Y%29%3Emax%28X%29%29%3D%5Cfrac%7B1%7D%7B%5Cbinom%7Bn&plus;k%7D%7Bk%7D%7D)

**Therefore, the above probability is independent of a, and hence the proof.**







