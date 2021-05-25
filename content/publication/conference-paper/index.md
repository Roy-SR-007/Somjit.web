---
abstract: To study the effect and influence of **two or more** factors on a **response/study** variable, generally experiments are used, which are termed as `Factorial Experiments`. The term **Factorial Experiments** is coined by **R.A Fisher**. Considering a symmetric `2^n` Factorial Experiment, we determine the sum of squares of the required `Factorial Effects` in the concerned experiment, through the implementation of `Yates' Algorithm`, developed by **Frank Yates**.
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
  url: https://cran.r-project.org/package=YatesAlgo.FactorialExp.SR
publication: In *Comprehensive R-Archive Network*
publication_short: In *CRAN*
#publication_types:
#- "0"
publishDate: "2021-04-28T00:00:00Z"
#slides: example
summary: Implementation of Yates' Algorithm to determine the Sum of Squares of the `(2^n) - 1` Factorial Effects in a `2^n` symmetric Factorial Experiment. 
tags:
- Publications
title: YatesAlgo.FactorialExp.SR - Yates' Algorithm in 2^n Factorial Experiment
#url_code: '#'
#url_dataset: '#'
#url_pdf: http://eprints.soton.ac.uk/352095/1/Cushen-IMV2013.pdf
#url_poster: '#'
#url_project: ""
#url_slides: ""
#url_source: '#'
#url_video: '#'
---

**Summary of the Package and its Working** 

The package `YatesAlgo.FactorialExp.SR` comprises of a function `run.yates.algo`, which takes in user inputs for the following, 

* `trt.combo` :: A factor type array, listing down the **Treatment Combinations** in a 2^n Factorial Experiment, in their standard order. For instance, if we are dealing with a 2^3 Factorial Experiment, i.e., there are 3 factors involved in the experiment, namely, factors **A**, **B** and **C**. The 8 treatment combinations listed in their standard order are `1,a,b,ab,c,ac,bc,abc`. Therefore the input should be as follows,

> trt.combo = c(1,a,b,ab,c,ac,bc,abc) # For a 2^3 Factorial Experiment.

* `trt.total` :: A numeric vector storing the **totals/sum** of each treatment combination involved in the design, i.e., in a 2^3 Factorial Experiment, the corresponding treatment totals are `[1],[a],[b],[ab],[c],[ac],[bc],[abc]`. Hence the input will be, 

> trt.total = c(...) # A Numeric Vector comprising of the corresponding Treatment Totals.

* `n` :: A numeric value indicating the number of **factors** involved in a 2^n Factorial Experiment. For instance, in a 2^3 Factorial Experiment, `n = 3`.

> n = 3 # For a 2^3 Factorial Experiment.

* `r` :: A numeric value signifying the number of **replicates** used for a **CRD**, or the number of **blocks** used in case of an **RBD**. Conducting a 2^3 Factorial experiment in 3 blocks using an RBD, would make `r=3`.

> r = 3 # Conducting 2^3 Factorial Experiment using an RBD with 3 blocks.

With these above mentioned inputs from the user, the function performs the Yates' Algorithm, in order to return a numeric vector comprising of the Sum of Squares of the (2^n) - 1 [`(2^3) - 1 = 7`] **Factorial Effects**, which are further utilized in the analysis of the design.

**The Yates' Algorithm**

The Algorithm was developed by **Frank Yates**. Let us consider a `2^n` Factorial Experiment, i.e., there are `n` respective factors involved in the experiment. Hence the total number of **treatment combinations** are `2^n` and the total number of **factorial effects** are `(2^n) - 1`.

The Algorithm comprises of the following steps.

* **Step 1** :: In the first column of the Yates' Table, list down all the possible `2^n` treatment combinations, in their respective **standard order**.

* **Step 2** :: In the second column of the Yates' Table, write down the treatment combination totals, starting from **[1]**, right till the end.

* **Step 3** :: In the third column of the Yates' Table, make the entries as described.
Divide the second column into **pairs** of consecutive treatment combination totals. Thereby putting in the **first half** of the third column, **sum of the consecutive pairs of treatment combinations**, and putting in the **second half** of the third column, **differences of the first element of every treatment combination total pair from its second element**.

* **Step 4** :: From columns `4` to `n+2` of the Yates' Table, repeat the process as discussed in Step 3, i.e., dividing the previous column into pairs of treatment combination totals, then inserting the sum of the consecutive pairs formed into the first half of the present column and inserting the differences of the first element from the second element of the pair formed, into the second half of the present column.

From the **second element** in the **last column** of the Yates' Table, we would obtain the numerator of the Sum of Squares' expression for the Factorial Effects, i.e., if we are dealing with a `2^3` Factorial Experiment, then the Yates' Table will look somewhat like this,

![The Yates' Table](YatesTable.JPG)

Therefore, the required **Sum of Squares of the Factorial Effects**, in a `2^n` Factorial Experiment, will then be given by,

![Sum of Squares](SS.JPG)

**Demonstration of `run.yates.algo()`**

The values of the response variable in the experiment under consideration, stored in the vector `y()`.

> y = c(90,74,81,83,77,81,88,73,
93,78,85,80,78,80,82,70,
98,85,88,84,82,85,88,79,
98,72,87,85,99,79,87,80,
95,76,83,86,90,75,84,80,
100,82,91,86,98,81,86,85)

The number of replicates/blocks used in the Factorial Experiment.

> r = 3

Total number of factors in the 2^n Factorial Experiment under consideration, i.e., taking an instance of `2^4` Factorial Experiment.

> n = 4

The Treatment Allocation as mentioned in a factor type character vector.

> trt = as.factor(c(rep(1:8,each=1,times=3),rep(9:16,each=1,times=3)))

The Relevant Treatment Combinations in the 2^n Factorial Experiment in their standard order.

> trt.combo = as.factor(c('1','a','b','ab','c','ac','bc','abc',
                       'd','ad','bd','abd','cd','acd','bcd','abcd'))

Determining the Treatment Totals using the `aggregate()` function.

> trt.total = aggregate(y,by = list(trt),sum)$x

Finally calling the function `run.yates.algo()` to get the desired Sum of Squares of the `(2^4) - 1 = 15` Factorial Effects.

> SS.factorial.effects = run.yates.algo(trt.combo,trt.total,n,r)

Now you are ready to construct the **ANOVA Table** and proceed further with your analysis.  



{{% callout note %}}
You can click the *Cite* button above, to enable import publication metadata into your reference management software, i.e., to make a citation of the above publication.
{{% /callout %}}

