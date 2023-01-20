# Need help

I would like to know whether it is useful as custom format. If not, I need help to convert this as a revealjs plugin quarto extension.

- Firstly, I have tried to implement [`reveal-code-focus`](https://github.com/bnjmnt4n/reveal-code-focus) as a [plugin](https://quarto.org/docs/extensions/revealjs.html), but sadly enough (I tried for hours (actually the whole day)) but my newbie rusty javascript knowledge would not allow me to convert the actual [`reveal-code-focus.js`](https://github.com/bnjmnt4n/reveal-code-focus/blob/master/reveal-code-focus.js) file as a plugin (could not change that `iife` function to [the form](https://quarto.org/docs/extensions/revealjs.html#example-attribution) similar to the form shown in the case of [`attribution.js` in the docs](https://quarto.org/docs/extensions/formats.html#example-revealjs))

- So then, I resorted to implement this as a custom format.

## changes I have made mainly

- One important thing, even though in the [`reveal-code-focus`](https://github.com/bnjmnt4n/reveal-code-focus) docs, original [highlight.js](https://highlightjs.org/) is suggested to use, I have not used that. Instead changed the code in `reveal-code-focus.js`, so that it works with the `highlight.js` file shipped with quarto.

- commented the line 60 and changed a bit in line 253 of `reveal-code-focus.js` (I think the `hljs` argument can be discarded for good).

- There was some problem with source code line numbers. Because since an extra `span` with class `line` gets added, existing css for showing line number was not working. So I have changed that a bit `in custom.scss`.


# `codeFocus-revealjs` Format

## Installing


```bash
quarto use template shafayetShafee/codeFocus
```

This will install the extension and create an example qmd file that you can use as a starting place for your article.


You can view live demo of rendered document [here](https://shafayetshafee.github.io/line-highlight/template.html) 

