# Preambles

In LaTeX, the preamble is the part of the document before the `\begin{document}` command. It is used to define the 
document class, load packages, and set up the document layout.

These can be as short as a single line or as long as several pages. Longer where you may be using custom commands or
a large number of packages.

In cases where you are loading a large number of packages, it is often a good idea to create a preamble file that you
can input into your document. This can help keep your document clean and make it easier to reuse the same preamble in
multiple documents. (Although some packages handle this for you. See [Multi-file Documents](multifile-docs.md).)

## Basic Preamble

A basic preamble might look like this:

```latex
\documentclass{article}
\usepackage{graphicx}
\usepackage[2.5cm, 2.5cm]{geometry} % Set margins
```

At a minimum, you need to specify the document class. The `article` class is a good choice for most documents.
While the `report` and `book` classes are also common, they are more suited to longer documents as they include the
additional header of chapter.

## Complex Preamble

A more complex preamble might look like this:

!!! Note
    This is a random preamble, it is not meant to be used as is. It is just an example of what a more complex preamble
    might look like.

```latex
\documentclass{article}
\usepackage{graphicx}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{hyperref}
\usepackage{cleveref}
\usepackage{tabularray}
\usepackage{tikz}
\usepackage{pgfplots}
\usepackage{siunitx}
\usepackage{booktabs}
\usepackage{enumitem}
\usepackage{minted}

\pgfplotsset{compat=1.18}
\usetikzlibrary{arrows.meta}
\usetikzlibrary{calc}
\usetikzlibrary{positioning}
\usetikzlibrary{shapes.geometric}
\usetikzlibrary{shapes.misc}
\usetikzlibrary{shapes.symbols}
\usetikzlibrary{statistics}

\hypersetup{
    colorlinks=true,
    linkcolor=blue,
    filecolor=magenta,
    urlcolor=cyan,
}

\makeatletter
\newcommand{\crefrangeconjunction}{--}
\makeatother
```

As you can see, this preamble loads a large number of packages and sets up some custom settings for those packages, in
addition to specifying a custom command. To make this more manageable, it is normally reccomended to save this as a
separate `tex` file and then input it into your document.

e.g. if you save the above preamble as `preamble.tex`, minus the `\documentclass{}`, you can then include it in your 
document like this:

```latex
\documentclass{article}

\input{preamble}
```

This will be functionally equivalent to having the entire preamble in your document.

![Preamble Meme](images/g7mjxh2y68481.jpg)