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
CSS:	https://github.com/KolenCheung/peg-multimarkdown-latex-support/raw/master/Grump.css
HTML Header:	<div id="wrapper">
HTML Header Level:	1
LaTeX Header Level:	2
LaTeX Input:	mmd-article-header
LaTeX input:	mmd-natbib-plain
LaTeX Input:	mmd-load-physics-related
LaTeX Input:	mmd-load-tables-related
LaTeX Input:	mmd-load-pdfpages
LaTeX Input:	mmd-load-headings
CSS:	https://github.com/KolenCheung/peg-multimarkdown-latex-support/raw/master/amsthm.css
thmd:	chapter
LaTeX Input:	mmd-load-amsthm
Title:	Temp Title
Subtitle:	Temp Subtitle
Keywords:	Temp Keyword
Revision:	0.1
Language:	English
Author:	Temp
Email:	Temp
Affiliation:	Temp
Copyright:	2015 temp
	All Rights Reserved.
LaTeX Mode:	memoir
LaTeX Input:	mmd-article-begin-doc
tocd:	5
secd:	5
LaTeX Input:	mmd-load-toc-setcounter
LaTeX Input:	mmd-load-toc
LaTeX Footer:	mmd-memoir-footer

<!--\begin{comment}-->
**Table of Contents**

{{TOC}}
<!--\end{comment}-->

Testing