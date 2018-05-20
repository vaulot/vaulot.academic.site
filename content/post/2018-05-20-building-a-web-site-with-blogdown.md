---
title: Building a web site with Blogdown
author: Daniel Vaulot
date: '2018-05-20'
slug: building-a-web-site-with-blogdown
categories:
  - R
tags: ["private"]
header:
  caption: ''
  image: ''
---

# Academic web site

* Use Academic template : https://sourcethemes.com/academic/
* Use Netlifly : https://app.netlify.com/sites/vaulot/overview
* If there are errors, run on command line `hugo -v` within the root of the web site
* For bibliography
     * Use function from : 
     * In Mendeley export using bibtex style (do not use the bibtex export because this will result in escaped caracters that do not work)
     * Must correct quite a few things
        1. change bibtex reference name that may contain space or other characters causing problems for import
        1. change accentuated characters
        1. remove {} that are around composite names
        1. In the bibtex_2academic comment out lines that correspond to field that do not exist (e.g. for submitted)
        1. Add tags and projects
        1. Add abstracts and short abstracts
