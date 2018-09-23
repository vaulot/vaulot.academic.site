---
title: "Finally switching from Word to latex... Should have done years ago"

date: 2018-09-15
lastmod: 2018-09-15

draft: false
categories: [""]
tags: ["papers"]

summary: "Some notes about how to write a paper for Scientific Reports using Overleaf."
---

For the last paper of Margot thesis on the diversity of Mamiellophyceae in the OSD dataset I decided to switch from Word to Latex using the Overleaf web site. It took some effort and adjustment, but the effort might be really worthwhile.

### Steps
* Open an Overleaf account
* Swtich to Overleaf 1 (Overleaf 2 misses some of the necessary feature and has not such a nice interface)
* Create a new project based on the Scientific Reports template
* Main text is in file **main.tex**
* Begin to fill in the template
* Get the link for Git (in the share menu) - see here: https://www.overleaf.com/blog/195-new-collaborate-online-and-offline-with-overleaf-and-git-beta#.W51LHM4zaUk)
* On your computer using git clone the repository in a directory
* Use GitHub desktop to add this repository to the list of repository
`git clone https://git.overleaf.com/2029559gkypzx`
* Now you can very easily synchronize between your computer and Overleaf. Just be careful not to change things in both location at the same time.

### Supplementary material
* Create a new file called **main-sup.etx** which contains all the Supplementary
* Need to change the name of the Figures and tables
* Cannot use \maketitle because it requires abstract
* In order to be able to reference the figures and tables from the supplementary material, you need to put some helper code in the main document (main.tex - see code below), reference the Supplementary file in main.tex and refresh the Supplementary file each time you restart the Overleaf session.

### Figures (directory \fig)
* Do the figures under R (using an Rmd file) and save as pdf
* If necessary improve with Corel Draw or Illustrator
* Reexport as pdf
* Open pdf and select area of figures
* Save as png in the directory \fig

### Tables (directory \tables)
* Store tables in Excel file
* Read Excel in R and export as Latex using xtable library
* Choose the option to have the caption on top
* If the table is too big use `scalebox = 0.75`
* If the table is too long, use the longtable option `tabular.environment = "longtable", floating=FALSE` (note: floating must be set to FALSE in this case)
* File is stored in \table

### Bibliography
* Do not use the Overleaf Mendeley importer because it does not handle the italics (coded in HTML in Mendeley <i>Micromonas</i>)
* Export the group you are working in as a bib file
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
