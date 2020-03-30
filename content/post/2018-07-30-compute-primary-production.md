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

$$P = DIC\cdot\frac{DPM\tiny{measured}}{DPM\tiny{added}}\cdot1.05\cdot1000$$

$P$ = Primary Productivity in $mgC \cdot m^{-3} \cdot d^{-1}$

$DIC$ = Dissolved inorganic carbon in  $mgC \cdot L^{-1}$

$DPM\tiny{measured}$ during 24 h

$DPM\tiny{added}$ = $SA \times 10 \times  V$

$SA$ = Standard activity in 100 µL

$V$ = Volume incubation (mL)

1.05 is to account for differential uptake between $^{14}$C and $^{12}$C

1000 is to go from from $L^{-1}$ to $m^{-3}$ since DIC is in $mgC \cdot L^{-1}$


### For cells sorted by flow cytometry

After doing a bit of maths...

$$P = \frac{DIC}{1000}\cdot\frac{DPM\tiny{measured}}{SA\cdot10}\cdot\frac{1}{N}\cdot\frac{1}{24}$$

$P$ = Primary Productivity per cell in $fgC \cdot cell^{-1} \cdot h^{-1}$

$DIC$ = Dissolved inorganic carbon in  $mgC \cdot L^{-1}$

$DPM\tiny{measured}$ during 24 h for the cells sorted

$SA$ = Standard activity in 100 µL

$N$ = number of cells sorted

---

With contributions from [Adriana Lopes dos Santos](https://adriana.netlify.com/) (ASE, NTU) and Andres Gutierrez-Rodriguez (NIWA)
