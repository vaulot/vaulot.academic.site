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

$$P\tiny{vol} = \textstyle DIC \cdot \frac{DPM\tiny{vol}}{DPM\tiny{added}} \cdot 1.05 \cdot 1000$$

which simplifies to:

$$P\tiny{vol} = DIC \cdot \frac{DPM\tiny{vol}}{SA \cdot  V} \cdot 1.05 \cdot 100$$

where:

* $P\tiny{vol}$ = Primary Productivity in $mgC \cdot m^{-3} \cdot d^{-1}$

* $DIC$ = Dissolved inorganic carbon in  $mgC \cdot L^{-1}$

* $DPM\tiny{vol}$ = DPM measured during 24 h for volume $V$ (filtered)

* $DPM\tiny{added}$ = $SA \cdot 10 \cdot  V$

* $SA$ = Standard activity in 100 µL

* $V$ = Volume incubation (mL)

* 1.05 is to account for differential uptake between $^{14}$C and $^{12}$C

* 1000 is to go from from $L^{-1}$ to $m^{-3}$ since DIC is in $mgC \cdot L^{-1}$


### For cells sorted by flow cytometry

Let us define:

* $DPM\tiny{cells}$ = DPM measured  during 24 h for $N$ cells

* $N$ = number of cells sorted

* $C$ = cell concentration per mL

* $P\tiny{cell}$ = Primary productivity per cell ($fgC \cdot cell^{-1} \cdot h^{-1}$)

$$P\tiny{cell} = P\tiny{vol} \cdot \frac{1}{C \cdot 10^{6} } \cdot \frac{1}{24} \cdot 10^{12}$$

Which simplifies

$$P\tiny{cell} = P\tiny{vol} \cdot \frac{1}{C} \cdot \frac{1}{24}\cdot 10^{6}$$

* $10^{12}$ is to convert from milligrams to femtograms

* $\frac{1}{24}$ is to convert from day to hours

* $\frac{1}{C \cdot10^{6} }$ is to compute the number of cells per  $m^{-3}$

Using the formula for $P\tiny{vol}$ at the top :

$$P\tiny{cell} = DIC \cdot \frac{DPM\tiny{vol}}{SA \cdot  V} \cdot 1.05 \cdot 100 \cdot \frac{1}{C} \cdot \frac{1}{24} \cdot 10^{6}$$

Simplifies to :

$$P\tiny{cell} = DIC \cdot \frac{DPM\tiny{vol}}{SA \cdot  V \cdot  C} \cdot 1.05 \cdot \cdot \frac{1}{24} \cdot 10^{8}$$

DPM\tiny{vol} can be computed from the individual DPM in cells ($DPM\tiny{cell}$) as:

DPM\tiny{vol} = \frac{DPM\tiny{cells} \cdot C  \cdot V }{N}

So that:

$$P\tiny{cell} = DIC \cdot \frac{DPM\tiny{cells} \cdot C  \cdot V}{SA \cdot  V \cdot  C  \cdot  N} \cdot 1.05 \cdot \cdot \frac{1}{24} \cdot 10^{8}$$


which simplifies to

$$P\tiny{cell} = \frac{DIC \cdot\ DPM\tiny{cell}}{SA \cdot N \cdot 24}} \cdot 10^{8}\cdot1.05$$





---

With contributions from [Adriana Lopes dos Santos](https://adriana.netlify.com/) (ASE, NTU) and Andres Gutierrez-Rodriguez (NIWA)
