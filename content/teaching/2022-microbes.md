---
title: "NTU - R for Microbes on Natural Ecosystems - 2022"

date: 2022-10-20
lastmod: 2022-10-02

draft: false
categories: ["courses"]
tags: ["R", "microbes"]

summary: "Introduction to metabarcoding data analysis"
---

{{< figure src="img/course_microbio_2022.png" title="" lightbox="false" width="600" >}}

__Course__: Microbes on Natural Ecosystems

__Code__: ES2304 & ES7027

__Main instructor__: Adriana Lopes dos Santos

__Academic Year__: 2022-2023 - First semester

__Institution__: Nanyang Technological University, Singapore

__School__: Asian School of the Environment

### Objectives
During the first half of this course, we will walk through some basics concepts in microbiology, the diversity within the three domain of life and how microbes control the chemistry of our planet.  In the second half, we will start by some common techniques used in microbial molecular ecology, and we'll dive deep into real life high throughput sequencing datasets from distinct oceanic regions. With these datasets and some basic tools, we will describe biogeographic and diversity patterns of specific microbial eukaryotes from the marine plankton. 



### Lecture
* [Session 10 - Metabarcode analyses with metapr2](https://daniel-vaulot.fr/html/course-microbes-2022/Metapr2.html) 
* [pdf](https://daniel-vaulot.fr/html/course-microbes-2022/Metapr2.pdf) 


### metapr2

* [Web site](https://shiny.metapr2.org)

Installing as an R package

```
install.packages(devtools)

devtools::install_github("pr2database/metapr2-shiny")
metapr2::metapr2App()
```


