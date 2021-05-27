---
external_link: ""
image:
  caption: '**The Imitation Game (2014)**'
  focal_point: Smart
#links:
#- icon: github-square
#  icon_pack: fab
#  name: Code Reference
#  url: https://github.com/Roy-SR-007/hexSticker-ggplot2
summary: Inter conversions of **number systems**. Taking a number from the given base to a desired base, i.e., for instance `binary` to `decimal` or vice versa.
tags:
- R
title: Coverting Number Systems in R - From one base to the other
---

**27th May, 2021, 02:48 am**

**Motivation** :: This stretches back to the school days, when in the computer science classes we used to get questions in the examination about number system conversions, from one base to the other. It was actually fun.

With R, Python, J and other software, these conversions are performed in a jiffy nowadays.

**An Introduction** :: Number System Conversion has a great deal of application in various interdisciplinary fields like,

* **Computer Hardwares**
* **Network Security**
* **Cryptography and Cryptanalysis**, etc..

In this write up, we will briefly show the conversions from one base to the other, but through a programming approach in R. 

Most of us are familiar with the different common bases available, i.e., 

* **Base 2** - `Binary`
* **Base 10** - `Decimal`
* **Base 8** - `Octal`, and 
* **Base 16** - `HexaDecimal`

There are readily available packages, which would do this task for you. To name a few packages, they are, 

* **DescTools in R** - [DescTools : Tools for Descriptive Statistics](https://cran.r-project.org/package=DescTools) 

* **numbersystem in Python** - [numbersystem : Number System Converter](https://pypi.org/project/numbersystem/#:~:text=numbersystem%20is%20a%20Python%203.7,like%20binary%2C%20decimal%2C%20etc.) 

But its quite interesting to learn the code and algorithm that possible went behind in the development of the above two packages.

**The Algorithm** :: The basic idea is to convert a given number in a particular base to the corresponding `decimal base`, and from the decimal base, we finally revert to the desired base.

{{% callout note %}}
If you are not familiar with basic rules of conversion of numbers from one base to the other, it would be good if you visit this link and once go through. 
[Click here to read rules of conversions](https://www3.ntu.edu.sg/home/ehchua/programming/java/datarepresentation.html)
{{% /callout %}}

**The Coding** :: 