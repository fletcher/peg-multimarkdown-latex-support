# Introduction #

This is folk from Fletcher's [peg-multimarkdown-latex-support](https://github.com/fletcher/peg-multimarkdown-latex-support).


## What's Modified ##

- `mmd-article-header.tex` added an optional choice to use `twopage` instead
- all `*-begin-doc.tex` are modified such that all links will appears blue
- all `*-begin-doc.tex` added a ``*-begin-doc-bidi.tex` variants. This added right to left language support in XeLaTeX (e.g. Hebrew, Arabic). `bidi` has to be used immediately before the `\begin{document}`, so this is the only way to make it work


## What's New ##


### `mmd-load-unicode-related` ###

NOTE: the following doesn't work for me anymore. This use `ucharclasses`, but it doesn't work on my Mac anymore, which has OS X El Capitan and the latest MacTex in 2015. Note that my original implementation in `mmd-load-unicode-related` only included Chinese, Greek, Hebrew, although should be extendable to anything `ucharclasses` support. In the next section I include an alternative way to include Greek and Chinese.

Provide Automated unicode support in XeLaTeX, see comments in the file.

This load the package `xltxtra`, which loads the `fontspec`, which

> pro­vides an au­to­matic and uni­fied in­ter­face to fea­ture-rich AAT and OpenType fonts through the NFSS in ... XeLaTeX [^ <http://ctan.org/pkg/fontspec>]

The rest of the file is to set things up such that font transitions between the followings are automated:

- Latin (include English...)
- Greek (include `unicode-math` where some of us like to use unicode Greek letters rather than say `\alpha`)
- Hebrew (Right to left language, hence the `bidi` used above)
- CJK (Chinese, Japanese, Korean)

These are all languages I need to use. Few free to expand this to support other languages.

I am very inexperienced in how LaTeX handle this (via `fontspec`), so I have a lot of trials and errors. So my file has a lot of comments. Feel free to clean things out and put more explanation there.

### `mmd-load-greek-chinese` ###

This one use `CMU` and `XeCJK` to support Greek and Chinese respectively.

The fonts CMU stands for Computer Modern Unicode and is intended to replicate the default font LaTeX used, Computer Modern, and adding unicode support. However it isn't a complete project. In my experience it misses some character like `<>`.

The fonts I picked for CJK is for Chinese only. Feel free to substitute any other CJK fonts there.

### `mmd-load-amsthm` & `amsthm.css` ###

It loads the `amsthm` package with some predefines theorem style

 The `thmd` metadata variables (which should be defined before you use `mmd-load-amsthm`) defines the section that the theorem count resets. e.g. `thmd: chapter`

The `amsthm.css` mimics this in HTML version of the document. See how it's done in [amsthm usage](readme-amsthm.md).

### `mmd-load-pdfpages` ###

Make `![](*.pdf)` possible in LaTeX too.


### `mmd-load-toc-setcounter` & `mmd-load-toc` ###

`mmd-memoir-begin-doc.tex` already has TOC loaded, but some others doesn't (e.g. article). Use this to add TOC after the `*-begin-doc` metadata in your md file.

`mmd-load-toc-setcounter` should be used before `mmd-memoir-begin-doc.tex` or `mmd-load-toc`. You also need to define metadata variables `tocd` & `secd` before `mmd-load-toc-setcounter`. It sets `secnumdepth` and `tocdepth`. I personally use 5 for both of them.


### `mmd-load-physics-related` ###

This loads Physics related packages, including those within `mmd-load-ams.tex`.


### `mmd-load-tables-related` ###

This included many tables related packages. See the comments in the files.

Some are helpful when your table is too big. Some are helpful if you need to rotate the table direction (and you need to include raw LaTeX in your md file).


### `mmd-load-headings` ###

Use headings as `pagestyle`


### `mmd-load-theme` ###

Use another theme in beamer class. The default example is `Berkeley`.

# Examples #

See [Example Metadata Setup in MMD](readme-Metadata.md).