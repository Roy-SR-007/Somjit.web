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

> set.seed(20) # Setting the seed to 20 for uniformity of the diagram generated\
> \
> f = function(n) # A Function to develop the (x,y) coordinates for the subplot\
> {\
>   u = runif(n)\  
>   v = runif(n)\   
>   x = cos(2*pi*u)*sqrt(-2*log(v))\ 
>   y = sin(2*pi*v)*sqrt(-2*log(u))\
>   r = list(x=x, y=y)\
>   return(r)\
> }\
> \
> r = f(5000) # Generating 5000 pairs of (x,y) coordinates\ 
> \
> df = data.frame(x=r$x,y=r$y)\
> \
> # chosing four different shades of blue\
> col = c("#0047FA","#00B4FA","#00D6FA","#00FAF8")\
> \
> # Creating the plot using the ggplot() command and replicating the 4 shades of blue\ 
> # chosen for 1250 times each for the corresponding 5000 pair of points generated\
> \
> q = ggplot(df,aes(x = x, y = y)) +\
> geom_point(alpha=1.2, shape=20, color=rep(col,1250),size=0.01) + theme_void()\
> \
> q + theme(plot.background = element_rect(fill = "black")) # Adding a black background\

