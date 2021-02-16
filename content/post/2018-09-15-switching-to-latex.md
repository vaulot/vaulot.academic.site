---
title: "Switching from Word to latex... a leap in prodcutivity"

date: 2018-09-15
lastmod: 2021-02-16

draft: false
categories: [""]
tags: ["papers"]

summary: "Some notes about how to write a paper using Overleaf."
---

For the last paper of Margot thesis on the diversity of Mamiellophyceae in the OSD dataset in 2018, I decided to switch from Word to Latex using the Overleaf web site. It took some effort and adjustment, but the effort might be really worthwhile.  All papers written since then have been written using Overleaf and Latex.

![](/img/overleaf-interface.png)

### Steps
* Open an Overleaf account
* Create a new project based on the Scientific Reports template or alternate template for the journal you are targeting.  
* You can also use this [general template](https://daniel-vaulot.fr/files/latex/template_paper.zip)
* Main text is in file **main.tex**
* Begin to fill in the template

### Synchronizing with computer
* Get the link for Git (in the left menu) - see here
* On your computer start git in the commande window 
* Navigate to the directory you want to use
* Clone the repository in a subdirectory called `my_paper`
`git clone https://git.overleaf.com/2029559gkypzx my_paper`
* Use GitHub desktop to add this repository to the list of repository
* Now you can very easily synchronize between your computer and Overleaf. Just be careful not to change things in both location at the same time.

### Supplementary material
* The best strategy is to put the supplementary material at the end of the main file and then to split the produced pdf into 2 parts for journals that require the Supplementary to be in a different file

### Figures (directory \fig)
* Do the figures under R (using an Rmd file) and save as pdf
* If necessary improve with Corel Draw or Illustrator or best **Affinity Designer**
* Reexport as pdf
* Save as pdf in the directory \fig

### Tables (directory \tables)
* Store tables in Excel file
* Read Excel in R and export as Latex using kableExtra library
* Choose the option to have the caption on top
* If the table is too big use `latex_options = c("scale_down")`
* If the table is too long, use the longtable option `kbl(..., longtable = TRUE)` 
* File is stored in \table

### Bibliography
* Do not use the Overleaf Mendeley importer because it does not handle the italics (coded in HTML in Mendeley <i>Micromonas</i>)
* Export the group you are working with as a bib file
* Run small R routine to change the HTML codes for Italics to the Latex code for italics.
* Place the file into your git directory and push to Overleaf

### Latex Templates
* [Paper](https://daniel-vaulot.fr/files/latex/template_paper.zip)
