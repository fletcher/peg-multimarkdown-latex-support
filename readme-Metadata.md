HTML Header:	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.1.0/styles/default.min.css">
	<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.1.0/highlight.min.js"></script>
	<script>hljs.initHighlightingOnLoad();</script>  

# Example Metadata Setup in MMD #

The goals of the metadata setup are:

- Include Physics and Math support, including the `amsthm` mentioned above
- Both HTML (hence MMD editor preview) and LaTeX output are as close as possible

See [Example here](https://ickc.github.io/peg-multimarkdown-latex-support/index.md).


## Header ##


### MathJax ###

This is more complicated than usual MathJax setup to include the Physics package, and other goodies.

```html
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
		src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_CHTML">
	</script>
```


### Highlight.js ###

```html
HTML Header:	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.1.0/styles/default.min.css">
	<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.1.0/highlight.min.js"></script>
	<script>hljs.initHighlightingOnLoad();</script>  
```

### Custom CSS for HTML Output ###

```yaml
CSS:	https://ickc.github.io/peg-multimarkdown-latex-support/Grump.css
HTML Header:	<div id="wrapper">
HTML Header Level:	1
```

Other choices are `antique.css` & `swiss.css`.

### Document Class Setup And Other Packages ###

|	|Article	| Memoir	| Beamer	|  
| ------	| ------	| ------	| ---	|  
| `LaTeX Header Level:`	| `2`	| `1`	| [^ The documentation suggests `3` here, but it didn't work, and the sample provided didn't include this metadata too.]	|  
|Add This Metadata	|`LaTeX Input:	mmd-article-header`	| `LaTeX Input:	mmd-memoir-header`	| `LaTeX Input:	mmd-beamer-header`	|  

```yaml
LaTeX input:	mmd-natbib-plain
LaTeX Input:	mmd-load-physics-related
LaTeX Input:	mmd-load-tables-related
LaTeX Input:	mmd-load-pdfpages
```


### Article ###

Add

```yaml
LaTeX Input:	mmd-load-headings
```


### XeLaTeX and Unicode Support ###

Add

```yaml
LaTeX Input:	mmd-load-unicode-related  
Use XeLaTeX:	true  
```


### `amsthm` ###

Add (see [LaTeX Document Sectioning][] for section name):

```yaml
CSS:	https://ickc.github.io/peg-multimarkdown-latex-support/amsthm.css
thmd:	chapter
LaTeX Input:	mmd-load-amsthm
```

See [amsthm usage](readme-amsthm.md) for details.

## Document Related ##

```yaml
Title:	Temp Title
Subtitle:	Temp Subtitle
Keywords:	Temp Keyword
Revision:	0.1
Language:	English
```

No `date` means date of compilation.


### Beamer ###

```yaml
Event:	Temp Event
Date:	Event Date
```


## Author Related ##

```yaml
Author:	
Email:	
Affiliation:	
Copyright:	2015 temp  
	All Rights Reserved.
```


### Other ###

```yaml
Address:	
Phone:	
Web:	
```


## Footer ##


### Article ###

(see [LaTeX Document Sectioning][] for depth):

```yaml
LaTeX Mode:	memoir
LaTeX Input:	mmd-article-begin-doc
tocd:	5
secd:	5
LaTeX Input:	mmd-load-toc-setcounter
LaTeX Input:	mmd-load-toc
LaTeX Footer:	mmd-memoir-footer
```


### Memoir ###

```yaml
LaTeX Mode:	memoir
LaTeX Input:	mmd-memoir-begin-doc
LaTeX Footer:	mmd-memoir-footer
```


### Beamer ###

```yaml
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

```yaml
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
