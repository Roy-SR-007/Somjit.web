---
external_link: ""
image:
  caption: '**YatesAlgo**'
  focal_point: Smart
links:
- icon: github-square
  icon_pack: fab
  name: Code Reference
  url: https://github.com/Roy-SR-007/hexSticker-ggplot2
summary: A description of using `hexSticker` and `ggplot2` to design **Hexagonal Stickers** for R-packages. 
tags: []
title: Designing Hexagonal Stickers in R - Combining hexSticker & ggplot2
---

**25th May, 2021, 02:32 am**

**An Introduction** :: Data Visualization through R is doing wonders because of its diversified applications and the element of ease which it imparts to the users. From Statistics to Data Science, R has marked its significance and position everywhere.

The package `ggplot2` is a widely used package, which through its uncountable components and applications, helps the users to delve deep into the area of data visualization and graphics.

The package named `hexSticker` enables us to develop and design different hexagonal visualizations, especially `hexagonal stickers`.

**Motivation** :: In this write up, a brief introduction to the steps will be provided, in order to create a Hexagonal Sticker using the above two packages.

**Step 1** :: **Installing and loading the required packages for the task**

> install.packages("hexSticker")\
> install.packages("ggplot2")

**Step 2** :: **Load the installed packages using the library() command**

> library(hexSticker)\
> library(ggplot2)

**Step 3** :: **Creating a subplot for our sticker**

For this step we develop a simple plot that would eventually be placed at the center of the sticker. For instance we will be adding the following image at the center of the sticker.

![The Subplot](subplot.png)

**Code for the above plot**

Setting the seed to `20` for uniformity of the diagram generated.

> set.seed(20)

A Function `f()` to generate the (x,y) coordinates for the subplot.

> f = function(n)\
> {\
>   u = runif(n)\
>   v = runif(n)   
>   x = cos(2pi{u})sqrt(-2log(v)) # for representation `*` has been omitted\
>   y = sin(2pi{v})sqrt(-2log(u)) # for representation `*` has been omitted\
>   r = list(x=x, y=y)\
>   return(r)\
> }

Generating `5000` pairs of (x,y) coordinates.

> r = f(5000)

Storing the observations in a data frame - `df()`.

> df = data.frame(x=r$x,y=r$y)

Using four shades of the color `blue` for the subplot.

> col = c("#0047FA","#00B4FA","#00D6FA","#00FAF8")

Generating the plot using the command `ggplot()` in the package `ggplot2`

> q = ggplot(df,aes(x = x, y = y)) +\
> geom_point(alpha=1.2, shape=20, color=rep(col,1250),size=0.01) + theme_void() 

Giving a black background to the plot using the function `theme()`

> q + theme(plot.background = element_rect(fill = "black"))
