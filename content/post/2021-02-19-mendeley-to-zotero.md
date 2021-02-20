---
title: "Switching from Mendeley to Zotero"

date: 2021-02-19
lastmod: 2021-02-19

draft: false
categories: [""]
tags: ["Mendeley", "Zotero"]

summary: "Since it has been bought back by Elsevier, the performance and capabilities of Mendeley have been going down.  Last straw is the abandon of pad supports (Android, Apple) since March 15 2021. So it is really time to move to something else."
---

My Mendeley database contains about 20,000 references neatly organized in folders and some with notes in the pdf. I do not care too much about the notes but I care about the folder structure especially as I am dealing with taxonomy and have folders for different taxonomy levels.  One key issue is that starting from version 1.19 of the Mendeley desktop manager, Mendeley encrypeted the Mendeley database that resides on your computer and therefore other applications cannot access the SQlite Mendeley database which makes any transfer to another reference manager painful.

{{< figure src="img/mendeley_folder_structure.png" title="Mendeley file structure" >}}

One caveat is that I do not use Word or Google docs to write up papers.  I switched completely to Latex using Oveleaf for collaborative work and have no intent whatsoever to switch back to Word.  So basically, I am exporting references as Bibtex.  

### Alternatives to Mendeley.

I have tried a couple of alternatives:

* **Papers from ReadCube**.  It is owned by a big company related to the Nature group.  I did not like really the interface and it lacked some of capabilities of Mendeley.  Also does not import easily Mendeley folder structure.
* **Paperpile**.  It imports very easily the Mendeley database and data structure by going directly to the Mendeley web interface (it does not read your local Mendeley database) but I do not really like the interface and the search capacities are super limited. It only interface at present with Google docs, not Word nor Overleaf
* **Zotero**. It is open source and has many plugins which add a lot of functions.  It is more complex to master than Mendeley, but finally I decided to switch to Zotero because it has more or less all the functions I need in particular, creating public and private groups.  Moreover it can be linked to Overleaf.

### Steps

* Install [Zotero and Chrome connectro](https://www.zotero.org/download/)
* Install [DOI plugin](https://github.com/bwiernik/zotero-shortdoi) for managing DOIs.
* Install [Zotfile plugin](http://zotfile.com/) to manage file.
* [Configure Zotfile](https://tomsaunders.co.nz/zotero-with-google-drive/#:~:text=Head%20over%20to%20Google%20Drive,to%20be%20on%20your%20PC.) to be link your Zotero pdf with Google drive (this way your files will be synchronized without having to pay for space on Zotero server)

In Mendeley:

* select all your references, left click and press update (see image below). This will use the DOI to update all your Mendeley references.  Zotero lacks this capacity.

{{< figure src="img/mendeley_update.png" title="Mendeley update references" >}}

* synchronize your database including your files to Mendeley server

{{< figure src="img/mendeley_sync.png" title="Mendeley synchronize" >}}