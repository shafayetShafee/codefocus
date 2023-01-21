# Need help

I would like to know whether it is useful as custom format. If not, I need help to convert this as a revealjs plugin quarto extension.

You can view live demo of rendered document [here](https://shafayetshafee.github.io/codeFocus/template.html) 

- Firstly, I have tried to implement [`reveal-code-focus`](https://github.com/bnjmnt4n/reveal-code-focus) as a [plugin](https://quarto.org/docs/extensions/revealjs.html), but sadly enough (I tried for hours (actually the whole day)) but my newbie rusty javascript knowledge would not allow me to convert the actual [`reveal-code-focus.js`](https://github.com/bnjmnt4n/reveal-code-focus/blob/master/reveal-code-focus.js) file as a plugin (could not change that `iife` function to [the form](https://quarto.org/docs/extensions/revealjs.html#example-attribution) similar to the form shown in the case of [`attribution.js` in the docs](https://quarto.org/docs/extensions/formats.html#example-revealjs))

- So then, I resorted to implement this as a custom format.

## changes I have made mainly

- One important thing, even though in the [`reveal-code-focus`](https://github.com/bnjmnt4n/reveal-code-focus) docs, original [highlight.js](https://highlightjs.org/) is suggested to use, I have not used that. Instead changed the code in `reveal-code-focus.js`, so that it works with the `highlight.js` file shipped with quarto.

- commented the line 60 and changed a bit in line 253 of `reveal-code-focus.js` (I think the `hljs` argument can be discarded for good).

- There was some problem with source code line numbers. Because since an extra `span` with class `line` gets added, existing css for showing line number was not working. So I have changed that a bit `in custom.scss`.

## Ongoing problem

- This existing custom format installs fine. But the could not compile the template file provided with installed template. The whole things runs fine and generates the temporary md file, but then getting the error (`system could not find the template.html file`). So for now to test this, I would request to clone this repo and render the `template.qmd` directly in the cloned directory.

(Got the idea how to solve this problem. See the issue [#1](https://github.com/shafayetShafee/codeFocus/issues/1))

**Thanks.**


# `codeFocus-revealjs` Format

## Installing

**Do not install this now.**

```bash
quarto use template shafayetShafee/codeFocus
```

This will install the extension and create an example qmd file that you can use as a starting place for your article.


