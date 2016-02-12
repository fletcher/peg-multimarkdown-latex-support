---
HTML Header:	<script type="text/x-mathjax-config">MathJax.Ajax.config.path.Contrib="https://cdn.mathjax.org/mathjax/contrib",MathJax.Hub.Register.StartupHook("TeX Jax Ready",function(){MathJax.Hub.Insert(MathJax.InputJax.TeX.Definitions.macros,{cancel:["Extension","cancel"],bcancel:["Extension","cancel"],xcancel:["Extension","cancel"],cancelto:["Extension","cancel"]})}),MathJax.Hub.Config({TeX:{equationNumbers:{autoNumber:"AMS"},extensions:["[Contrib]/physics/physics.js"]}});</script><script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_CHTML-full"></script>
CSS:	https://ickc.github.io/multimarkdown-latex-css/combined-css/multimarkdown-latex.css
HTML Header Level:	1
LaTeX Header Level:	2
LaTeX Input:	mmd-article-header
LaTeX input:	mmd-natbib-plain
LaTeX Input:	mmd-load-physics-related
LaTeX Input:	mmd-load-tables-related
LaTeX Input:	mmd-load-pdfpages
LaTeX Input:	mmd-load-headings
thmd:	chapter
LaTeX Input:	mmd-load-amsthm
Title:	Temp Title
Subtitle:	Temp Subtitle
Keywords:	Temp Keyword
Revision:	0.1
Language:	English
Author:	Kolen Cheung
Email:	khcheung@berkeley.edu
Affiliation:	University of California, Berkeley
Copyright:	2016 Kolen Cheung  
 	All Rights Reserved.
LaTeX Mode:	memoir
LaTeX Input:	mmd-article-begin-doc
tocd:	5
secd:	5
LaTeX Input:	mmd-load-toc-setcounter
LaTeX Input:	mmd-load-toc
LaTeX Footer:	mmd-memoir-footer
---
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.1.0/styles/default.min.css"><script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.1.0/highlight.min.js"></script><script>hljs.initHighlightingOnLoad();</script>
<!-- \begin{comment} -->
**Table of Contents**

{{TOC}}
<!-- \end{comment} -->

# Testing #

## MathJax and Physics ##

Physics:

\\[\begin{equation}
\ket{\upsilon}
\end{equation}\\]

Cancel:

\\[\begin{equation}
\cancel{p}
\end{equation}\\]

Also see the equation numbering above.

## Highlight ##

```bash
#!/bin/bash
while IFS='' read -r line || [[ -n "$line" ]]; do
	iconv -f big5-2003 -t utf-8 "$line" > temp
	sed -i '' s/big5/utf-8/ temp
	mv -f temp "$line"
done < "$1"
```

## Amsthm ##

<!--\begin{conjecture}-->  <div class="conjecture">
1+1=2
<!--\end{conjecture}--></div>

## List ##

### Unordered ###

1. testing
2. testing
	1. testing
	2. testing
		1. testing
		2. testing
			1. testing
			2. testing

### Ordered ###


- testing
- testing
	- testing
	- testing
		- testing
		- testing
			- testing
			- testing

## Heading ##

See the heading numbering above