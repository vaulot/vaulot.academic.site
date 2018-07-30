---
title: "Compute primary production based on single cell C14 uptake"

date: 2018-05-20
lastmod: 2018-05-20

draft: false
categories: ["phytoplankton"]
tags: ["phytoplankton"]

summary: "After fighting a bit with maths..."
---

### Classical formula for filtered samples

The classical formula can be found [here](http://hahana.soest.hawaii.edu/hot/protocols/chap14.html) or [here](http://www.montana.edu/priscu/documents/LTER-methods-web-page/Method_Manual_AC_22_Feb_2017.pdf)

$$P = DIC \cdot \frac{DPM_{measured}}{DPM_{added}} \cdot 1.05  \cdot 1000$$

$P$ = Primary Productivity in $mgC \cdot m^{-3} \cdot d^{-1}$

$DIC$ = Dissolved inorganic carbon in  $mg \cdot L\{-1}$

$DPM_{measured}$

$DPM_{added} = SA \times 10 \times  V$

$SA$ = Standard activity in 100 µL

$V$ = Volume incubation (mL)

1.05 is to account for differential uptake between $C_1_4$ and $C_{12}$

1000 is to go from from L_{-1}$ to $m^{-3}$ since DIC is in $mg \cdot L_{-1}$

$$\text{softmax}(z)_j = \frac{e^{z_j}}{\sum_i^{\text{dim}(z)}e^{z_i}}$$

$\frac{x}{1}$
