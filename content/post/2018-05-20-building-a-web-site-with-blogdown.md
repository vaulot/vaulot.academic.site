---
title: "New web site..."

date: 2018-05-20
lastmod: 2018-05-20

draft: false
categories: ["R"]
tags: ["R"]

summary: "Notes to create Blogdown website."
---
* Use Academic template : https://sourcethemes.com/academic/
* Use Netlifly : https://app.netlify.com/sites/vaulot/overview
* If there are errors, run on command line `hugo -v` in the root of the web site
* Images for project vignettes are 150 px high
* For bibliography from Mendeley
     * In Mendeley export using bibtex style (do not use the bibtex export because this will result in escaped caracters that do not work)
     * Use function from [Lorenzo](https://lbusett.netlify.com/post/automatically-importing-publications-from-bibtex-to-a-hugo-academic-blog/) to import the bibtex file and trasnform to MD files.
     * Must correct quite a few things before however
        1. change bibtex reference name that may contain space or other characters causing problems for import
        1. change accentuated characters
        1. remove {} that are around composite names
        1. In the bibtex_2academic comment out lines that correspond to field that do not exist (e.g. for submitted)
        1. Add tags and projects
        1. Add abstracts and short abstracts (short abstracts are need for the home page)
        1. Add images
* There is definite problem with Rmd files.  
        1. Include in the header
        2. They need to be knitted to an html file
        3. At each knitting iteration the yaml header is added again and again....
        1. Still not working... so stick with md files...
```r
        output:
           blogdown::html_page
```
