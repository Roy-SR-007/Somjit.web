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

> install.packages("hexSticker")
> install.packages("ggplot2")

**Step 2** :: **Load the installed packages using the library() command**

> library(hexSticker)
> library(ggplot2)

**Step 3** :: **Creating a subplot for our sticker**

For this step we develop a simple plot that would eventually be placed at the center of the sticker.

![The Subplot](content/posts/example 3/subplot.png)

