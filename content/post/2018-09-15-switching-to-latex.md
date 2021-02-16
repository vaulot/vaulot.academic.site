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
* You can also use this [general template](https://daniel-vaulot.fr/files/latex/paper_template.zip)
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

### Latex Code
#### Main document - header
```latex
\documentclass[fleqn,12pt]{wlscirep}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}

\usepackage{setspace} % for spacing of paragraphs
\usepackage{lineno} % for line numbers
\usepackage{gensymb} % for degree sign \degree

%%% HELPER CODE FOR DEALING WITH EXTERNAL REFERENCES
% (See http://tex.stackexchange.com/a/69832/226)
%%%
\usepackage{xcite}
\usepackage{xr}
\makeatletter
\newcommand*{\addFileDependency}[1]{% argument=file name and extension
  \typeout{(#1)}
  \@addtofilelist{#1}
  \IfFileExists{#1}{}{\typeout{No file #1.}}
}
\makeatother

\newcommand*{\myexternaldocument}[1]{%
    \externaldocument{#1}%
    \addFileDependency{#1.tex}%
    \addFileDependency{#1.aux}%
}
%%% END HELPER CODE
\externaldocument{main_sup} % This is the supplementary material

% Title and authors
\title{Novel diversity within GOT Mamiellophyceae }
\author[1]{Jon Snow}
\author[1,*]{Daniel Vaulot}
\affil[1]{Landfall}
\affil[*]{Corresponding author: (ORCID 0000-0002-0717-5685) vaulot@landfall.got}
\keywords{phytoplankton, xxx}

\begin{document}
```
#### Supplementary - header

```latex
\documentclass[fleqn,12pt]{wlscirep}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}

\usepackage{setspace} % for spacing of paragraphs
\usepackage{lineno} % for line numbers
\usepackage{gensymb} % for degree  \degree
\usepackage{longtable} % for long tables
\usepackage{hanging} % for hanging indents

% To change the name of the Figure to Fig. S1 etc...
\DeclareCaptionLabelFormat{addS}{#1 S#2}
\captionsetup[table]{labelformat=addS}
\captionsetup[figure]{labelformat=addS}

\begin{document}
```
