Title:	LaTeX support files for peg-multimarkdown  


# Introduction #

[peg-multimarkdown] is a program to convert plain text into HTML or LaTeX.
This project includes some default template files that can be used to create
certain types of documents using LaTeX.

You are not limited to using these classes or templates. You can create your
own template files, or just embed your LaTeX commands within comments in your
MultiMarkdown document itself. If you find yourself creating similar documents
over and over again, however, you may be better off creating a few templates
you can simply call with the `LaTeX Input` metadata fields in MultiMarkdown.

These files were designed to handle some of the common metadata fields in a
consistent way, an to implement some defaults that *should* prevent errors if
you leave out important metadata (substituting `Title`, `Author`, etc).

[peg-multimarkdown]: https://github.com/fletcher/peg-multimarkdown


# Installation #

These files need to go in your `texmf` folder, wherever that may be.

With MacTeX on Mac OS X:

	~/Library/texmf/tex/latex/mmd

On most *nix accounts, you can use:

	~/texmf/tex/latex/mmd

I don't remember off the top of my head where your texmf folder belongs in
Windows.


# Default Metadata Types #

Several MultiMarkdown metadata keys are used in these files, and are fairly
self-explanatory:

* Title				--- Specify the title of the document

* Author			--- Specify the author of the document

* Date				--- Specify a date

* Base Header Level --- Specify the maximum organizational level for the
  document (e.g. part, chapter, section, subsection). You need to choose a
  value for this that fits with the way you organized your document.

Metadata is used in order, so the order and placement of the `LaTeX Input`
metadata fields is important.


# Article #

To create a document using the memoir article class, you need the following
basic metadata:


	latex input:		mmd-article-header
	Title:				Whatever Title You Like 
	Base Header Level:	2  
	LaTeX Mode:			memoir  
	latex input:		mmd-article-begin-doc
	latex footer:		mmd-memoir-footer


# Beamer #

To create a pdf slideshow presentation using beamer:

	latex input:		mmd-beamer-header  
	Title:				Your Title  
	Subtitle:			Some optional subtitle 
	Author:				Your Name  
	Affiliation:		Your institution, web site, whatever
	base header level:	3
	LaTeX Mode:			beamer  
	Theme:				keynote-gradient  
	latex input:		mmd-beamer-begin-doc  
	latex footer:		mmd-beamer-footer  

There are several beamer themes included that are derived from various keynote
themes --- keynote-gradient, keynote-vintage, keynote-portfolio. I tweaked
these themes to work with MultiMarkdown, but they were originally created by
others (see the source files for details).

The header levels are set so that `h1` is a part, `h2` is a section, `h3` is a
slide, and `h4` is used to designate text that will print in a handout, but
not in the actual slideshow.


# Letterhead #

Still in progress.


# Memoir #

To create a "book" using memoir:

	latex input:		mmd-memoir-header
	Title:				Your Title
	Base Header Level:	2
	LaTeX Mode:			memoir  
	latex input:		mmd-memoir-begin-doc
	latex footer:		mmd-memoir-footer

Header levels are: `h1` part, `h2` chapter, `h3` section, `h4` subsection,
`h5` subsection.
