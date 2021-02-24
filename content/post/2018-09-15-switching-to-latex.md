---
title: "Switching from Word to latex... a leap in prodcutivity"

date: 2018-09-15
lastmod: 2021-02-16

draft: false
categories: [""]
tags: ["papers"]

summary: "Some notes about how to write a paper using Overleaf."
---

In 2018, I decided to switch from Word to Latex using the Overleaf web site. It took some effort and adjustment, but the effort has really been worthwhile.  All papers written since then have been written using Overleaf and Latex. It drastically decreased the turn around between the different authors allowing people to work in parallel and not in serial manner.  Also it is very satisfying to see your paper nicely formatted.

![](/img/overleaf-interface.png)

### Steps
* Open an Overleaf account
* Create a new project based on the Scientific Reports template or alternate templates for the journal you are targeting.  
* You can also use this [general template](https://daniel-vaulot.fr/files/latex/template_paper.zip) that works well for first submission (see below how to convert from pdf to docx if you really need to)
* Main text is in file **main.tex**
* Begin to fill in the template

### Synchronizing with computer
* Get the link for Git (in the left menu)
* On your computer start a Powershell window 
* Navigate to the directory you want to use (using cd)
* Clone the repository in a subdirectory called `my_paper`
`git clone https://git.overleaf.com/2029559gkypzx my_paper`
* Use GitHub desktop to add this repository to the list of repository
* Now you can very easily synchronize between your computer and Overleaf. Just be careful not to change things in both location at the same time.

### Supplementary material
* The best strategy is to put the supplementary material at the end of the main file and then to split the produced pdf into 2 parts for journals that require the Supplementary to be in a different file

### Figures (directory \fig)
* Do the figures under R (using an Rmd file). The best libraries to use are `ggplot2` and `patchwork` to compose multi-panel figures.
* Save as pdf.  I
* If necessary improve with Corel Draw or Illustrator or best **Affinity Designer**
* Reexport as pdf
* Save as pdf in the directory \fig

### Tables (directory \tables)
* If you are data have been generated outside R:
    * Store tables in Excel file
    * Read Excel file into R e.g. with `rio::import`
* Export as Latex using [kableExtra library](https://haozhu233.github.io/kableExtra/awesome_table_in_pdf.pdf)
  * Choose the option to have the caption on top
  * If the table is too big use `latex_options = c("scale_down")`
  * If the table is too long, use the longtable option `kbl(..., longtable = TRUE)` 

### Bibliography
* Do not use the Overleaf Mendeley or Zotero importer because it will get your all database.
* Export the group you are working with as a bibtex file
  * With Mendeley, run small R routine to change the HTML codes for Italics to the Latex code for italics.
  * With Zotero, using the Better BibTex (BBT) plugin, HTML codes are converted to Latex.
* Place the file into your git directory and push to Overleaf

### Converting to Word (docx)
Some rear guard journals still ask you to convert your papers to Word at least at the final publication stage.  It is not too difficult to convert from pdf to Word. What you should do first is at least to remove line numbering because this will always be a problem.  After that you can:
* Open the pdf directly with Word.  Sometimes some formats are lost. 
* Better, use this free converter which works really well: https://pdf2docx.com/

### Latex Templates
* [Paper](https://daniel-vaulot.fr/files/latex/template_paper.zip)

