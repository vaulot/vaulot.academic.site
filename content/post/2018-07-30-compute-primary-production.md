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

$$Pvol = DIC \cdot \frac{DPMvol}{DPMadded} \cdot 1.05 \cdot 1000$$

and plugging the value for $DPMadded$ (see below):

$$Pvol = DIC \cdot \frac{DPMvol}{SA \cdot  V} \cdot 1.05 \cdot 1000$$

where:

* $Pvol$ = Primary Productivity per unit volume in $mgC \cdot m^{-3} \cdot d^{-1}$

* $DIC$ = Dissolved inorganic carbon in  $mgC \cdot L^{-1}$

* $DPMvol$ = DPM measured during 24 h for volume $V$ (filtered)

* $DPMadded$ = $SA \cdot  V$

* $SA$ = Standard activity in 1 mL (DPM per mL)

* $V$ = Volume of incubation (mL)

* 1.05 is to account for differential uptake between $^{14}$C and $^{12}$C

* 1000 is to go from from $L^{-1}$ to $m^{-3}$ since DIC is in $mgC \cdot L^{-1}$


### For cells sorted by flow cytometry

Let us define:

* $DPMcells$ = DPM measured  during 24 h for $N$ cells

* $N$ = number of cells sorted

* $C$ = cell concentration per mL

* $Pcell$ = Primary productivity per cell ($fgC \cdot cell^{-1} \cdot h^{-1}$)

$$Pcell = Pvol \cdot \frac{1}{C \cdot 10^{6} } \cdot \frac{1}{24} \cdot 10^{12}$$

Which simplifies

$$Pcell = Pvol \cdot \frac{1}{C} \cdot \frac{1}{24}\cdot 10^{6}$$

* $10^{12}$ is to convert from milligrams to femtograms

* ${24}$ is to convert from day to hours

* $C \cdot 10^{6}$ is the number of cells per  $m^{-3}$

Using the formula for $Pvol$ at the top :

$$Pcell = DIC \cdot \frac{DPMvol}{SA \cdot  V} \cdot 1.05 \cdot 1000 \cdot \frac{1}{C} \cdot \frac{1}{24} \cdot 10^{6}$$

Simplifies to :

$$Pcell = DIC \cdot \frac{DPMvol}{SA \cdot  V \cdot  C} \cdot 1.05 \cdot \frac{1}{24} \cdot 10^{9}$$

$DPMvol$ can be computed from the individual DPM in cells ($DPMcells$) as:

$$DPMvol = \frac{DPMcells \cdot C  \cdot V }{N}$$

So that:

$$Pcell = DIC \cdot \frac{DPMcells \cdot C  \cdot V}{SA \cdot  V \cdot  C  \cdot  N} \cdot 1.05 \cdot \frac{1}{24} \cdot 10^{9}$$


which simplifies finally to:

$$Pcell = DIC \cdot \frac{DPMcells}{SA \cdot N \cdot 24} \cdot 1.05 \cdot 10^{9}$$


---

With contributions from [Adriana Lopes dos Santos](https://adriana.netlify.com/) (ASE, NTU) and Andres Gutierrez-Rodriguez (NIWA)
