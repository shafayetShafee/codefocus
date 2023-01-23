# `codefocus-revealjs` format

This custom format only extends the default [revealjs](https://quarto.org/docs/presentations/revealjs/) format with the revealjs plugin [`reveal-code-focus`](https://github.com/bnjmnt4n/reveal-code-focus). That's it.

## Installing

```bash
quarto use template shafayetShafee/codefocus
```

This will install the extension and create an example qmd file that you can use as a starting place for your slides.  It’s also possible to install only the format if you working with an existing project,

```bash
quarto add shafayetShafee/codefocus
```

This will install the extension within a `_extensions` folder in your working project directory. See [here](https://quarto.org/docs/extensions/formats.html#distributing-formats) for details.


## Usage

To know how to specify the format along with two options `bgcolor` and `scrollToFocused`, see the source code, [template.qmd](https://github.com/shafayetShafee/codefocus/blob/main/template.qmd).

With this custom format, it is possible to highlight a line of code in code-chunk and add some discussion (i.e. text) below the code chunk for that highlighted line of code using [fragments](https://quarto.org/docs/presentations/revealjs/advanced.html#fragments).


### Basic use

~~~
```{r}
# this is some comment
# this is more comment
```

::: {.fragment data-code-focus="1"}
When this fragment is shown, the first line of code will have the `focus` class added to it and it gets highlighted.
:::

::: {.fragment data-code-focus="1-2"}
 Another fragment. This time, both lines will now have the `focus` class.
:::
~~~

Here the first fragment highlights first line (using `data-code-focus="1"`) along with the text within the fragment and the second fragment corresponds to highlighting both line 1 and 2 (using `data-code-focus="1-2"`)

### Multiple code blocks

For slides with multiple code blocks, the `data-code-block` attribute can be used to focus on lines from a particular code block. By default, all fragments will focus on the first code block, unless otherwise specified. For example, 

~~~
```{r}
a <- 1
b <- 2
c <- 1 + 2
```
and, 

```{r}
print(c)
```

::: {.fragment data-code-focus="1-2"}
Here we have declared two variables
:::

::: {.fragment data-code-focus="3"}
Then added them and passed them to c
:::

::: {.fragment data-code-focus="1" data-code-block="2"}
Then print the c
:::
~~~

So here the first two fragment corresponds to first code chunk by default and the second one corresponds to second code chunk (using `data-code-block="2"`).

### Demo

[View the live demo of the above examples here](https://shafayetshafee.github.io/codefocus/template.html)

### Options

Its possible to add these following options under the format,

- [`scorllToFocused`](https://github.com/bnjmnt4n/reveal-code-focus#scrolltofocused): `true` or `false` (default is `true`).

- `bgcolor`: "#color". Its possible to define what will be the background color of the highlighted code line using this option.


<hr>

## Help me to Improve this Extension

[need-help.md](https://github.com/shafayetShafee/codefocus/blob/main/need-help.md)

