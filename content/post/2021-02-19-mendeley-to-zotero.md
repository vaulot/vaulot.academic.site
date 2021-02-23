---
title: "Switching from Mendeley to Zotero (Windows)"

date: 2021-02-19
lastmod: 2021-02-19

draft: false
categories: [""]
tags: ["Mendeley", "Zotero"]

summary: "Since it has been bought back by Elsevier, the performance and capabilities of Mendeley have been going down.  Last straw is the abandon of pad supports (Android, Apple) since March 15 2021. So it is really time to move to something else."
---

My Mendeley database contains about 20,000 references neatly organized in folders and some with notes in the pdf. I do not care too much about the notes but I care about the folder structure especially as I am dealing with taxonomy and have folders for different taxonomy levels.  One key issue is that starting from version 1.19 of the Mendeley desktop manager, Mendeley encrypeted the Mendeley database that resides on your computer and therefore other applications cannot access the SQlite Mendeley database which makes any transfer to another reference manager painful.


{{< figure src="img/mendeley_folder_structure.png" title="Mendeley file structure"  height="200px">}}

One caveat is that I do not use Word or Google docs to write up papers.  I switched completely to Latex using Oveleaf for collaborative work and have no intent whatsoever to switch back to Word.  So basically, I am exporting references as Bibtex.  

### Alternatives to Mendeley.

I have tried a couple of alternatives:

* **Papers from ReadCube**.  It is owned by a big company related to the Nature group.  I did not like really the interface and it lacked some of capabilities of Mendeley.  Also does not import easily Mendeley folder structure.
* **Paperpile**.  It imports very easily the Mendeley database and data structure by going directly to the Mendeley web interface (it does not read your local Mendeley database) but I do not really like the interface and the search capacities are super limited. It only interface at present with Google docs, not Word nor Overleaf
* **Zotero**. It is open source and has many plugins which add a lot of functions.  It is more complex to master than Mendeley, but finally I decided to switch to Zotero because it has more or less all the functions I need in particular, creating public and private groups.  Moreover it can be linked to Overleaf.  Some nice tutorials:
    * [Offcial Zotero manual](https://www.zotero.org/support/start)
    * [Extensive tutorial about Zotero](https://guides.library.oregonstate.edu/c.php?g=359201&p=2426080) (a bit outdated for some aspects).
    * [How to make the most of Zotero](https://tomsaunders.co.nz/zotero-guide/).

### Moving from Mendeley 1.19 to Zotero

_The following instructions are valid for Mendeley 1.19.  If you have version 1.18, things will be more easy_

Just as a foreword, it is a very painful process if you have a lot of references and you are bound to loose some references in the process...

[Detailed instructions](https://www.zotero.org/support/kb/mendeley_import) can be found on the Zotero web site.

#### Install and configure Zotero
* Install [Zotero and Chrome connectro](https://www.zotero.org/download/)
* Install [DOI plugin](https://github.com/bwiernik/zotero-shortdoi) for managing DOIs.
* Install [Zotfile plugin](http://zotfile.com/) to manage pdf file storage.  Once you have it installed you can configure Zotfile:
  * to attach the files to the database and synchronize them to the Zotero server.  For a medium size database (about 2500 files) the best Zotero deal is "unlimited storage" which costz is 120US$ per year.
  * [to link your pdf files to a folder on your Google drive](https://tomsaunders.co.nz/zotero-with-google-drive/#:~:text=Head%20over%20to%20Google%20Drive,to%20be%20on%20your%20PC.) (this way your files will be synchronized without having to pay for space on Zotero server)
* Install and configure [Better bibtex plugin](https://retorque.re/zotero-better-bibtex/). This allows to customize bibtex citation keys and drag and drop citations from Zotero to any editor such as overleaf.

{{< figure src="img/zotero_better_bibtext.png" title="Better bibtex define keys">}}

{{< figure src="img/zotero_export.png" title="Zotero quick export" >}}

#### In Mendeley:

* select all your references, left click and press update (see image below). This will use the DOI to update all your Mendeley references.  Zotero lacks this capacity.

{{< figure src="img/mendeley_update.png" title="Mendeley update references" >}}

* synchronize your database including your files to Mendeley server

{{< figure src="img/mendeley_sync.png" title="Mendeley synchronize" >}}

* exit Mendeley

#### Move Mendeley database and install version Mendeley 1.18

* Locate your Mendeley database in directory: Username\AppData\Local\Mendeley Ltd\Mendeley Desktop

{{< figure src="img/mendeley_database.png" title="Mendeley database" >}}

* Move this database to a safe location
* Install [Mendeley 1.18](https://www.zotero.org/support/kb/mendeley_import)
* Resynchronize your entire database with the pdf files. I use the following organization for the file but this really does not matter.  This step may take several hours depending on the size of library and the speed of your connection.

{{< figure src="img/mendeley_folders.png" title="Mendeley database" >}}

* Finally import into Zotero. This took a long time especially with 20,000 references and crashed a few times... In my case it crashed after 5,600 import.  One thing that helped is to move some references that were "Unsorted" to trash. You can recover them later to import them through bibtex.

### Groups

Groups from Mendeley are not imported into Zotero. 
* Save all the pdf from the Group in a directory
* If you have files in subfolders, use tags to mark the subfolders (eg. 18SV4, 18SV9)
* Export as bibtex (making sure that in the Mendeley settings you **do not escape the characters for Latex**)
* Import into Zotero
* Note: files in Groups have to be attached and cannot be linked.  So you if you want to move some references from your Library to a Group Library you will need first to attach them (Menu Tools/Manage attachment/Convert Files to Stored files).

### Conclusion...

What a pain, should have moved to Zotero a few years ago....