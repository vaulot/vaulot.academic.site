---
title: "Building an academic web site with Hugo"
slug: "web-site"

date: 2018-05-20
lastmod: 2018-05-20

draft: false
categories: ["website"]
tags: ["R"]

summary: "Notes to create Blogdown website."
---

### Academic template
* Follow Quintana blog
  * https://www.dsquintana.blog/free-website-in-r-easy/
* Academic template help
  * https://sourcethemes.com/academic/
  * https://themes.gohugo.io/theme/academic/post/getting-started/

### Steps:
* Open R studio
  * `install.packages("blogdown")`
  * Create a new project following
  ![](/img/hugo_create_project.png)
  * `library(blogdown)`
  * `blogdown::install_hugo(force = TRUE)`

```console
The latest Hugo version is 0.59.1
trying URL 'https://github.com/gohugoio/hugo/releases/download/v0.59.1/hugo_extended_0.59.1_Windows-64bit.zip'
 length 29627443 bytes (28.3 MB)
downloaded 28.3 MB
Hugo has been installed to C:\Users\vaulot\AppData\Roaming\Hugo
```

  * `blogdown::serve_site()`

  ```console
  Rendering content/post/2015-07-23-r-rmarkdown.Rmd
  Building sites â€¦
                     | EN  
  +------------------+----+
    Pages            | 85  
    Paginator pages  |  0  
    Non-page files   | 21  
    Static files     |  9  
    Processed images | 31  
    Aliases          | 18  
    Sitemaps         |  1  
    Cleaned          |  0  

  Total in 15387 ms
  To stop the server, run servr::daemon_stop(1) or restart your R session
  Serving the directory C:\daniel.vaulot@gmail.com\Databases\_PR2\pr2_website at http://127.0.0.1:4321
  ```

  * Drag and drop into Netifly new project
    ![](/img/hugo_deploy_simple.png)
  * Change the name
    ![](/img/hugo_change_name.png)

  * On the long run better to link to GitHub
  1. Link to GitHUb from netifly
  2. If error this can be due to HUGO version that can be changed in the site settings
  ![](/img/hugo_version.png)
  ![](/img/hugo_add_name_server_goddy.png)
  ![](/img/hugo_add_name_server_netifly.png)
  ![](/img/hugo_add_name_server_netifly_success.png)  

### Netifly
  * https://app.netlify.com/sites/vaulot/overview
  * https://www.netlify.com/blog/2016/09/29/a-step-by-step-guide-deploying-on-netlify/
  * https://docs.netlify.com/domains-https/custom-domains/#assign-a-domain-to-a-site

* Purchase domain name with GoDaddy and set up DNS on goDaddy side - works fine

![](/img/dns-setup-1.png)

### Find errors
If there are errors, run on command line `hugo -v` in the root of the web site
![](/img/hugo_v.png)
* If there is no error, the site should compile and give the stats of the site
![](/img/hugo_valid.png)
* If there is an error then hugo will point to the file that causes problem (and the line) with a description (sometimes cryptic) of the error
 ![](/img/hugo_error.png)
* In this case, the error was caused by a missing comma between two tags (keywords)
 ![](/img/hugo_error_file.png)


### Images
* Images for project vignettes are 150 px high

* Customize the header image size to 800 px by using the a [custom css](https://sourcethemes.com/academic/docs/customization/#customize-style-css) copied to /static/css/ and modifying the config.toml. This template needs only to contain the code that has been changed in my [case](https://github.com/gcushen/hugo-academic/issues/84):
```console
img,
video {
  height: auto;
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
  display: block;
}
```

### Adding permanent links

* Add these lines to config.toml

```console
[permalinks]
  post = "/:year/:month/:day/:slug"
```

 * Add at top of blog entry (change web-site to whatever)

 ```console
 slug: "web-site"
 ```

### Internal links
With the new Academic template version, one can had internal links but it is a bit a pain to figure out.  

Here are examples for the home directory (`ref "home#team.md" `) and another directory (`ref "eukref/about.md"` ) which must be enclosed by double braces (`{`) and `<`


### Bibliography imported from Mendeley

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

* There is also a special library recently developped for R `devtools::install_github("petzi53/bib2academic", build_vignettes = TRUE)` - See https://github.com/gcushen/hugo-academic/issues/146

### Rmd files

There is definite problem with Rmd files.   

    1. Include in the header the R code below

    2. They need to be knitted to an html file  

    3. At each knitting iteration the yaml header is added again and again....

    4. Still not working... so stick with md files...  

```r
        output:
           blogdown::html_page
```
