# MultiFile Documents in LaTeX

One of the very fun features of LaTeX is the ability to split your document into multiple files and work on each of
them separately or even include them in multiple documents. This is particularly useful when you are working on a large
document, such as a book or a thesis, and you want to keep your files organized or use certain chapters/sections for 
other things.

There are a few ways to do this in LaTeX, with two in built methods (using `\input` and `\include`) and a few package
based methods (such as `subfiles` and `standalone`).

The in-built methods are simpler and work well for most cases, but lack the elegance and flexibility of the package
based methods. The package based methods are more powerful and provide additional features, such as the ability to
handle folder structures and preamble sharing for you.

!!! Note
    The `standalone` and `subfiles` packages should work together but may sometimes have issues. Make sure the
    `standalone` package is loaded before the `subfiles` package. And you need to call the standalone files with
    `\subfile` or `\subfileinclude` instead of `\input` or `\include`.

## Using the `subfiles` Package

!!! Note
    `subfiles` sometimes seems to struggle when you have your preamble in a `.sty` file. If you are having trouble
    with this, try saving your preamble as a `.tex` file instead.

The `subfiles` package is a popular choice for creating multi-file documents in LaTeX. It allows you to create a main
document that includes multiple subfiles, each of which can be compiled independently, and pull their preamble from the
main document. This makes it easy to work on different parts of a document separately and combine them later maintaining
only one preamble.

To use the `subfiles` package, you need to include it in your main document and use the `\subfile` command in each of
your subfiles. Here is an example of how to use the `subfiles` package if you have the following file structure:

```tree
├─ main.tex                                 # Main document
├─ chapter1/                                # Subfolder for chapter 1
│   └─ chapter1.tex                         # Subfile for chapter 1
```

```latex
% main.tex
\documentclass{article}
\usepackage{subfiles}

\begin{document}
\subfile{chapter1}
\subfile{chapter2}
\end{document}
```

```latex
% chapter1.tex
\documentclass[../main.tex]{subfiles} % Note the path to the main document ../ takes you up one level
\begin{document}
\chapter{Chapter 1}
This is chapter 1.
\end{document}
```

The `subfiles` package provides the `\subfile` command, which is used to include a subfile in the main document. The
subfile should be a standalone LaTeX document that can be compiled on its own. When you compile the main document, the
contents of the subfiles will be included in the output. It additionally provides the `\subfileinclude` which behave
similar to `\include` but with the added benefit of being able to compile the subfile independently.

If using a bibliography or some other external files, you may need to place them inside a special command in the main
document to ensure they are included in the subfiles. This can be done using the `\subfix` and 
`ifSubfilesClassLoaded` commands as follows:

```latex
% main.tex
\documentclass{article}
\usepackage{biblatex}
\usepackage{subfiles}
\ifSubfilesClassLoaded{%
	\addbibresource{\subfix{references.bib}}    % True case
	}{%
	\addbibresource{references.bib}             % False case
	}
```

This should allow all child documents to access the bibliography file and maintains autocomplete functionality.
The `\subfix` command alone will also work. However, this has a tendency to break autocomplete functionality in some
editors so play with it and find what works for your case.

Or for example if you have a central data folder and want to access it from subfiles. For example if you had the
following file structure:

```tree
├─ main.tex                                 # Main document
├─ preamble.tex                             # Preamble file
├─ data/                                    # Subfolder for data
│   └─ data.csv                             # Data file
├─ chapter1/                                # Subfolder for chapter 1
│   ├─ chapter1.tex                         # Subfile for chapter 1
│   ├─ digarams/                            # Subfolder for diagrams for chapter 1
│   │   └─ diagram1.tex                     # Subfile for diagram 1
```

You can access the data file from the subfiles by using the `\subfix` command as follows:

```latex
% diagram1.tex
\documentclass[../../main.tex]{subfiles}    % Note the path to the main document ../../ takes you up two levels
\begin{document}

\def\datafile{\subfix{../../data/data.csv}} % Defines the path as a command so we only need to subfix once

\pgfplotstableread[col sep=comma]{\datafile}\data   % Reads the data file into a table

\begin{tikzpicture}

\begin{axis}
\addplot table {\data};                     % Plots the data
\end{axis}

\end{tikzpicture}

\end{document}
```

If you wanted to make your diagram using the subfile package you would want to keep the formatting of the diagram
document the same including the use of `\subfix` but you would need to change the preamble and class to the following:

```latex
% diagram1.tex
\documentclass[tikz,crop]{standalone}

\input{../../preamble.tex}                  % Include the preamble from the main document
....Rest of the document....
```

For more information on the `subfiles` package, see the [documentation](https://ctan.org/pkg/subfiles).

## Using the `standalone` Package

The `standalone` package is another popular choice for creating multi-file documents in LaTeX. It allows you to create
standalone versions of your subfiles that can be compiled independently and included in the main document. I find the
focus of `standalone` to be on creating images and figures that can be included in multiple documents, but it can be
used for other things as well.

To use the `standalone` package, you need to include it in your main document and use the `\input` command to include
the standalone versions of your subfiles. Here is an example of how to use the `standalone` package:

```latex
% main.tex
\documentclass{article}
\usepackage{standalone}

\begin{document}
\input{chapter1}
\input{diagram1}
\input{chapter2}
\end{document}
```

```latex
% chapter1.tex
\documentclass[class=article]{standalone}
\begin{document}
\chapter{Chapter 1}
This is chapter 1.
\end{document}
```

```latex
% diagram1.tex
\documentclass[class=article,crop,tikz]{standalone}
\begin{document}
\begin{tikzpicture}
\draw (0,0) -- (1,1);
\end{tikzpicture}
\end{document}
```

The `standalone` package provides the `standalone` document class, which is used to create standalone versions of your
subfiles. The `class` option is used to specify the class of the main document, and the `crop` option is used to crop the
output to the size of the content. The `tikz` option is used to load the `tikz` package, which is commonly used for
creating diagrams and figures.

You may want to look at using the `import` package if you have a more complex file structure that has multiple levels of
folders. Or you can use the `subfiles` package in conjunction with the `standalone` package to get the best of both
worlds.

For more information on the `standalone` package, see the [documentation](https://ctan.org/pkg/standalone).

!!! Note
    For the methods listed below you will need to make sure the document preamble is included in each file. This is
    because each file is compiled separately and does not have access to the preamble of the main document.
    The main document should also contain any packages that are used in the included files.

## Using `\input`

The `\input` command is the simplest way to include another file in your document. It is used as follows:

```latex
\input{filename}
```

This will include the contents of `filename.tex` in your document at the point where the command is called. The file
extension (`.tex`) is optional, and if not provided, LaTeX will look for a file with the given name and a `.tex` 
extension.

The `\input` command is useful when you want to include the contents of another file as is, without any additional
formatting or separation. It is commonly used to include chapters or sections of a larger document.

## Using `\include`

The `\include` command is similar to `\input` but provides some additional features. It is used as follows:

```latex
\include{filename}
```

The main difference between `\input` and `\include` is that `\include` forces a page break before and after the included
file. This can be useful when you want to include chapters or sections that should start on a new page, but can sometimes
be undesirable if you want to include smaller snippets of text.

Another feature of `\include` is that it allows you to use the `\includeonly` command to include only specific files in
your document. This can be useful when working on a large document, and you only want to compile certain parts.

