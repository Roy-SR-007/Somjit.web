---
external_link: ""
image:
  caption: '**YatesAlgo**'
  focal_point: Smart
#links:
#- icon: github-square
#  icon_pack: fab
#  name: Code Reference
#  url: https://github.com/Roy-SR-007/hexSticker-ggplot2
summary: A description of using `hexSticker` and `ggplot2` to design **Hexagonal Stickers** for R-packages. 
tags:
- R
title: Designing Hexagonal Stickers in R - Combining hexSticker & ggplot2
---

**25th May, 2021, 02:32 am**

**An Introduction** :: Data Visualization through R is doing wonders because of its diversified applications and the element of ease which it imparts to the users. From Statistics to Data Science, R has marked its significance and position everywhere.

![first equation](https://latex.codecogs.com/gif.latex?%5Cint%20%5Cint_%7B%7D%5E%7B%7D)

The package `ggplot2` is a widely used package, which through its uncountable components and applications, helps the users to delve deep into the area of data visualization and graphics.

The package named `hexSticker` enables us to develop and design different hexagonal visualizations, especially `hexagonal stickers`, which in turn are used as a `logo` to the developed `R-Packages`. Not only it used to represent a particular R-package but also sometimes used for generating emblems for events, conferences, business organizations, etc.

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
>   x = cos(2pi{u})sqrt(-2log(v)) # for representation `*` is omitted\
>   y = sin(2pi{v})sqrt(-2log(u)) # for representation `*` is omitted\
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

**Step 4** :: **Creating the hexagonal sticker using the above subplot**

Now, once the subplot to be placed in the sticker has been figured out and developed, the function `sticker()` is used for generating the desired hexagonal sticker.

> sticker(q, package="YatesAlgo.FactorialExp.SR", p_size=6, \
    s_x=1.0, s_y=0.9, s_width=1.7, s_height=1.3, p_x = 1.0, \
    p_y = 1.6,\
    url = "https://cran.r-project.org/package=YatesAlgo.FactorialExp.SR", \
    u_color = "white", u_size = 2.6,\
    h_fill="black", h_color="grey",dpi=300,h_size=0.5)
    
The function `sticker()` has distinct parameters to alter which modifies the sticker created as per one's need. Few of the parameters are,

* `s_x`, `s_y` :: which controls the x and y positions of the subplot.
* `p_x`, `p_y` :: which controls the x and y positions of the package name displayed.
* `h_fill`     :: which controls the color with which the hexagon is to be filled, etc...

It is recommended that the documentation of the function should be thoroughly followed and read. Find the documentation here {{< icon name="download" pack="fas" >}}{{< staticref "media/hexSticker.pdf" "newtab" >}}hexSticker{{< /staticref >}}.

That's it! Your hex sticker is ready to be used and shared.

Hence we could be following these above mentioned steps to develop and generate multipurpose hexagonal stickers according to our own choice and need, using R.  

**Errors to look out for while developing the sticker**

While making the hexagonal sticker, I personally faced some errors as shown by R. The error pertains to the generation of subplot. At first I was trying to use a subplot which was made out of the function `plot()`. In the process, the following was displayed.

> Error in geom_subview(subview = subplot, x = s_x, y = s_y, width = s_width,  : 
                          subview must be provided
                          
The above error got debugged, as soon as I used a `ggplot` object. Any insights as to why this happens will be highly appreciated. 


