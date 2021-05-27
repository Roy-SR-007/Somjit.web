---
abstract: The package development aims in generating the required `2^n` treatment combinations in a `2^n` Factorial Experiment, where each factor is at **two** levels each. The treatment combinations are generated in an order known as the  **standard order of treatment combinations**.
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
  url: https://cran.r-project.org/package=TrtCombo.FactorialExp.SR
publication: In *Comprehensive R-Archive Network*
publication_short: In *CRAN*
#publication_types:
#- "0"
publishDate: "2021-05-03T00:00:00Z"
#slides: example
summary: Gives the required `2^n` **treatment combinations** in a `2^n` symmetric **factorial** experiment in their respective **standard order**.
tags:
- Publications
title: TrtCombo.FactorialExp.SR - Generation of Treatment Combination (in Standard Order) in 2^n Factorial Experiment
#url_code: '#'
#url_dataset: '#'
#url_pdf: http://eprints.soton.ac.uk/352095/1/Cushen-IMV2013.pdf
#url_poster: '#'
#url_project: ""
#url_slides: ""
#url_source: '#'
#url_video: '#'
---

**Definition of Treatment Combinations in a Factorial Experiment**

In a `2^n` Factorial Experiment, the `n` member sequence of `0's` and `1's` are regarded as the treatment combinations. For instance in a `2^2` factorial experiment, the treatment combinations are `1,a,b,ab`, where the **higher level/presence** of a factor, i.e., A(and B) is denoted by the letter **a(and b)**, and the **lower level/absence** of a factor is denoted by the absence of the corresponding letter. The treatment combination labeled as **'1'** denotes that particular combination, where both the factors A and B are at their lower levels or absent, and thereby it is regarded as the **Control Group**.

**The Algorithm of generating treatment combinations in Standard Order**

In order to list down the `2^n` treatment combinations in a `2^n` factorial experiment, in an arranged manner, i.e., in the **standard order**, the control group labeled as `1` is introduced first in the list. Then a new letter is introduced chronologically and its combination with every other previously introduced treatment combinations is listed down. This is repeated until all the `n` letters gets exhausted in the set of `n` factors involved in the experiment.

**NOTE** :: When combining a particular treatment combination with the previously introduced treatment combinations, avoid or omit the letters appearing `twice` in the combination, i.e. the combination of `ac` and `bc` is `abcc`, which is eventually reported as `ab`.

**Summary of the Package and its Working** 

The package `TrtCombo.FactorialExp.SR` comprises of a function `trtcombo.std.order`, which takes in user input for the following, 

* `n` :: A numerical input, which accounts for the number of factors involved in the `2^n` factorial experiment, i.e., for a `2^3` factorial experiment, the user must input `n` as `3`.

> n = 3 # For a 2^3 Factorial Experiment.

The function `trtcombo.std.order(n)`, will generate the treatment combinations in the standard order in case of a `2^n` factorial experiment, i.e., for instance if the user input for `n` is `3`, then the standard order of treatment combinations generated for a `2^3` factorial experiment is,
`1,a,b,ab,c,ac,bc,abc`, the `8` total combinations involved in the `2^3` experiment.


**Demonstration of `trtcombo.std.order()`**

Let us consider a `2^5` factorial experiment.

> n = 5

Running the function `trtcombo.std.order()` for `n = 5`.

> trtcombo.std.order(n)

The required `2^5 = 32` treatment combinations generated in their standard order are as follows.

> 1, a, b, ab, c, ac, bc, abc, d, ad, bd, abd, cd, acd, bcd, abcd, e, ae, be, abe, ce, ace, bce, abce, de, ade, bde, abde, cde, acde, bcde, abcde 

{{% callout note %}}
You can click the *Cite* button above, to import publication metadata into your reference management software, i.e., to make a citation of the above publication.
{{% /callout %}}

