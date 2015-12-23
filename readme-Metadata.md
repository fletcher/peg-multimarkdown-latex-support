# Example Metadata Setup in MMD #

The goals of the metadata setup are:

- Include Physics and Math support, including the `amsthm` mentioned above
- Both HTML (hence MMD editor preview) and LaTeX output are as close as possible


## Header ##


### MathJax ###

This is more complicated than usual MathJax setup to include the Physics package, and other goodies. It uses the MathJax beta which support the CHTML option which is faster than others. Change `beta` to `cdn` for non-beta version.

```
HTML Header:	<script type="text/x-mathjax-config">
		MathJax.Ajax.config.path["Contrib"] = "https://cdn.mathjax.org/mathjax/contrib";
		MathJax.Hub.Register.StartupHook("TeX Jax Ready",function () {
			MathJax.Hub.Insert(MathJax.InputJax.TeX.Definitions.macros,{
				cancel: ["Extension","cancel"],
				bcancel: ["Extension","cancel"],
				xcancel: ["Extension","cancel"],
				cancelto: ["Extension","cancel"]
			});
		});
		MathJax.Hub.Config({
			TeX: {
				equationNumbers: { autoNumber: "AMS"},
				extensions: ["[Contrib]/physics/physics.js"]
			}
		});
	</script>
	<script type="text/javascript"
		src="https://beta.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_CHTML">
	</script>
```


### Custom CSS for HTML Output ###

```
CSS:	https://github.com/KolenCheung/peg-multimarkdown-latex-support/raw/master/Grump.css
HTML Header:	<div id="wrapper">
HTML Header Level:	1
```


### Document Class Setup And Other Packages ###

|	|Article	| Memoir	| Beamer	|  
| ------	| ------	| ------	| ---	|  
| `LaTeX Header Level:`	| `2`	| `1`	| [^ The documentation suggests `3` here, but it didn't work, and the sample provided didn't include this metadata too.]	|  
|Add This Metadata	|`LaTeX Input:	mmd-article-header`	| `LaTeX Input:	mmd-memoir-header`	| `LaTeX Input:	mmd-beamer-header`	|  

```
LaTeX input:	mmd-natbib-plain
LaTeX Input:	mmd-load-physics-related
LaTeX Input:	mmd-load-tables-related
LaTeX Input:	mmd-load-pdfpages
```


### Article ###

Add `LaTeX Input:	mmd-load-headings`


### XeLaTeX and Unicode Support ###

Add `LaTeX Input:	mmd-load-unicode-related`


### `amsthm` ###

Add (see [LaTeX Document Sectioning][] for section name):

```
CSS:	https://github.com/KolenCheung/peg-multimarkdown-latex-support/raw/master/amsthm.css
thmd:	chapter
LaTeX Input:	mmd-load-amsthm
```

See [amsthm usage](readme-amsthm.md) for details.

## Document Related ##

```
Title:	Temp Title
Subtitle:	Temp Subtitle
Keywords:	Temp Keyword
Revision:	0.1
Language:	English
```

No `date` means date of compilation.


### Beamer ###

```
Event:	Temp Event
Date:	Event Date
```


## Author Related ##

```
Author:	
Email:	
Affiliation:	
Copyright:	2015 temp  
	All Rights Reserved.
```


### Other ###

```
Address:	
Phone:	
Web:	
```


## Footer ##


### Article ###

(see [LaTeX Document Sectioning][] for depth):

```
LaTeX Mode:	memoir
LaTeX Input:	mmd-article-begin-doc
tocd:	5
secd:	5
LaTeX Input:	mmd-load-toc-setcounter
LaTeX Input:	mmd-load-toc
LaTeX Footer:	mmd-memoir-footer
```


### Memoir ###

```
LaTeX Mode:	memoir
LaTeX Input:	mmd-memoir-begin-doc
LaTeX Footer:	mmd-memoir-footer
```


### Beamer ###

```
LaTeX Mode:	beamer
LaTeX XSLT:	beamer
Theme:	keynote-gradient
LaTeX Input:	mmd-beamer-begin-doc
LaTeX Footer:	mmd-beamer-footer
```


### Right To Left Language Support ###

Add a `bidi` suffix to `*-begin-doc`

***Warning***: `\usepackage{bidi}` has some crash with Beamer. If Hebrew is not needed, don't use it.


## ToC ##

In the main document of the md file, use this so that the HTML ToC won't show up in the LaTeX file:

```
<!--\begin{comment}-->
**Table of Contents**

{{TOC}}
<!--\end{comment}-->
```


## Appendix: LaTeX Document Sectioning ##

|Depth	| Section	|  
| ------	| ------	|  
|-1	|\part{part}	|  
|0	|\chapter{chapter}	|  
|1	|\section{section}	|  
|2	|\subsection{subsection}	|  
|3	|\subsubsection{subsubsection}	|  
|4	|\paragraph{paragraph}	|  
|5	|\subparagraph{subparagraph}	|  
