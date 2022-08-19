+++
# Date this page was created.
date = 2016-04-27T00:00:00

# Weight
weight = 9

# Project title.
title = "metaPR2"

# Project summary to display on homepage.
summary = "18S rRNA metabarcode database"

# Optional image to display on homepage (relative to `static/img/` folder).
image_preview = "metapr2_logo_small.png"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["database", "current_projects", "18S rRNA", "metabarcoding"]

# Optional external URL for project (replaces project detail page).
# external_link = "https://github.com/pr2database/pr2database"

# Does the project detail page use math formatting?
math = false

[header]
image = "metapr2_shiny_map.png"
caption = "Current coverage of metapr2"

+++

The aim of this project is to make publicly available a database of curated metabarcodes processed with [dada2](https://benjjneb.github.io/dada2/tutorial.html) and for which taxonomy is assigned with [PR2](https://github.com/pr2database/pr2database).

We have developed an interactive web site (https://shiny.metapr2.org) which allows to visualize, analyze and download the processed data.  This includes treemaps of taxonomy, barplots as a function of environmental variables, abundance maps as well as alpha and beta diversity analyses.


Please cite: Vaulot, D., Sim, C.W.H., Ong, D., Teo, B., Biwer, C., Jamy, M., Lopes dos Santos, A., 2022. metaPR2: a database of eukaryotic 18S rRNA metabarcodes with an emphasis on protists. Molecular Ecology Resources. https://doi.org/10.1111/1755-0998.13674


The latest version of the database (1.1) has been released in Spring 2022 and contains 41 public data sets including:

* Biomarks
* Blanes Time Series - 2004-2013
* Malaspina - 2010-2011
* Ocean Sampling Day - 2014 and 2015
* Tara Oceans - V4 and V9 - 2009-2012 - The Tara V4 data have been reprocessed with dada2
* Tara Arctic - V4
* Many Arctic datasets

The database contains also other non-public data sets from our own work, in particular in the Arctic (Green Edge, MicroPolar). If you are interested please [contact me](mailto:vaulot@gmail.com).

### Related projects
* [Ocean Barcode Atlas](http://oba.mio.osupytheas.fr/ocean-atlas/OBA_analyse)
