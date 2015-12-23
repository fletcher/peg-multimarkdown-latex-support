# Amsthm Usage #

If both `mmd-load-amsthm` & `amsthm.css` are used, and with the follow code in the md file, both HTML (hence the preview in MMD editors) and LaTeX output will show the correct result. The HTML version won't have auto-numbering:

```
<!--\begin{theorem}--> <div class="theorem">
...
<!--\end{theorem}--> </div>
```

```
<!--\begin{lemma}--> <div class="lemma">
...
<!--\end{lemma}--> </div>
```

```
<!--\begin{proposition}--> <div class="proposition">

<!--\end{proposition}--> </div>
```

```
<!--\begin{corollary}--> <div class="corollary">
...
<!--\end{corollary}--> </div>
```

```
<!--\begin{definition}-->  <div class="definition">
...
<!--\end{definition}--></div>
```

```
<!--\begin{conjecture}-->  <div class="conjecture">
...
<!--\end{conjecture}--></div>
```

```
<!--\begin{example}-->  <div class="example">
...
<!--\end{example}--></div>
```

```
<!--\begin{postulate}-->  <div class="postulate">
...
<!--\end{postulate}--></div>
```

```
<!--\begin{postulate}-->  <div class="postulate">
...
<!--\end{postulate}--></div>
```

```
<!--\begin{problem}-->  <div class="problem">
...
<!--\end{problem}--></div>
```

```
<!--\begin{remark}--> <div class="remark">
...
<!--\end{remark}--> </div>
```

```
<!--\begin{note}--> <div class="note">
...
<!--\end{note}--> </div>
```

```
<!--\begin{case}--> <div class="case">
...
<!--\end{case}--> </div>
```

```
<!--\begin{proof}-->  <div class="proof">
...
<!--\end{proof}--></div>
```
