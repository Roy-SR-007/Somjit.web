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

The package `YatesAlgo.FactorialExp.SR` comprises of a function `run.yates.algo`, which takes in user inputs for the following, 

* `trt.combo` :: A factor type array, listing down the **Treatment Combinations** in a 2^n Factorial Experiment, in their standard order. For instance, if we are dealing with a 2^3 Factorial Experiment, i.e., there are 3 factors involved in the experiment, namely, factors **A**, **B** and **C**. The 8 treatment combinations listed in their standard order are `1,a,b,ab,c,ac,bc,abc`. Therefore the input should be as follows,

> trt.combo = c(1,a,b,ab,c,ac,bc,abc) # For a 2^3 Factorial Experiment.

* `trt.total` :: A numeric vector storing the **totals/sum** of each treatment combination involved in the design, i.e., in a 2^3 Factorial Experiment, the corresponding treatment totals are `[1],[a],[b],[ab],[c],[ac],[bc],[abc]`. Hence the input will be, 

> trt.total = c(...) # A Numeric Vector comprising of the corresponding Treatment Totals.

* `n` :: A numeric value indicating the number of **factors** involved in a 2^n Factorial Experiment. For instance, in a 2^3 Factorial Experiment, `n = 3`.

> n = 3 # For a 2^3 Factorial Experiment.

* `r` :: A numeric value signifying the number of **replicates** used for a **CRD**, or the number of **blocks** used in case of an **RBD**. Conducting a 2^3 Factorial experiment in 3 blocks using an RBD, would make `r=3`.

> r = 3 # Conducting 2^3 Factorial Experiment using an RBD with 3 blocks.



{{% callout note %}}
You can click the *Cite* button above, to enable import publication metadata into your reference management software, i.e., to make a citation of the above publication.
{{% /callout %}}

