---
title: "Generating a report using Rmd and bookdown"

date: 2018-09-19
lastmod: 2018-09-19

draft: false
categories: [""]
tags: ["papers", "R"]

summary: "A nice way to gain time..."
---

After moving to Latex, probably the next step is to generate the paper directly under R, or at least draft report.

### Steps
* Use R Studio
* Install the bookdown library.
* Generate html version of the Rmd file that has been used to generate the figures.
* Locate in which directory they are (usually File_Name_files/figure-html/)
* In the header of the Rmd file use the following code (YAML) this will use the bookdonw extension and allow to generate both html and

```
---
title: "My title"
author: "Me myself"
date: '`r format(Sys.time(), "%d %m %Y")`'
output:
  bookdown::pdf_document2:
    number_sections: TRUE
    fig_caption: TRUE
    toc: false
    toc_depth: 1
  bookdown::html_document2:
    number_sections: TRUE
    fig_caption: TRUE
    toc: false
---
```

### Figures
* Give a name to each chunk that generate the figures because this name will be given to the png figures (e.g. abundant_species-1.png for a chunk named `r abundant_species`).  It is better to use - than _ because _ will cause problem in Latex
* Use the following code for inserting the figures in the reports

```
{r treemap,  fig.cap="Overall euk composition",  fig.align = "center", out.width ="50%"}
 knitr::include_graphics("Metabarcoding_Singapore_ASV_files/figure-html/treemap-1.png", dpi=72)
```

* Important points
    * `r treemap` - This figure can then be referenced as `(Figure \@ref(fig:treemap))`
    * `fig.cap="Overall euk composition"` - This will the caption of the figure
    * `out.width ="50%"` - This is the best way to control the output and will work both with HTML and pdf
