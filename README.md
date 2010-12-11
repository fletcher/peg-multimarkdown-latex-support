Title:	LaTeX support files for peg-multimarkdown  


# Introduction #

[peg-multimarkdown] is a program to convert plain text into HTML or LaTeX.
This project includes some default template files that can be used to create
certain types of documents using LaTeX.

These files are designed to serve as a template for you to customize to your
own needs. I encourage creativity and sharing!

[peg-multimarkdown]: https://github.com/fletcher/peg-multimarkdown


# Default Metadata Types #

Several MultiMarkdown metadata keys are used in these files, and are fairly
self-explanatory:

* Title				--- Specify the title of the document

* Author			--- Specify the author of the document

* Date				--- Specify a date

* Base Header Level --- Specify the maximum organizational level for the
  document (e.g. part, chapter, section, subsection)

Metadata is used in order, so the order and placement of the `LaTeX Input`
metadata fields is important.


# Article #

To create a document using the memoir article class, you need the following
basic metadata:


	latex input:		mmd-article-header
	Title:				Whatever Title You Like 
	Base Header Level:	2  
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
	latex input:		mmd-memoir-begin-doc
	latex footer:		mmd-memoir-footer

Header levels are: `h1` part, `h2` chapter, `h3` section, `h4` subsection,
`h5` subsection.
