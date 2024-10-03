# Quickstart

If you want to jump right in to using LaTeX here is a quick summation of the basics you need to know.

Trust LaTeX to do the formatting for you. You just need to focus on the content. This is the principal that LaTeX is
built on.

## Creating a Document

To create a document you need to start with a preamble. This is where you define the type of document you are creating 
and any packages you want to use. Here is an example of a simple preamble:

```latex
\documentclass{article}
```

This preamble tells LaTeX that you are creating an article. You can also create other types of documents such as books, 
reports.

## Adding Content

Once you have your preamble you can start adding content to your document. Here is an example of a simple document:

```latex
\documentclass{article}

\begin{document}

Hello, world!

\end{document}
```

This will create a document with the text "Hello, world!".

## Adding Sections

You can add sections to your document using the `\section` command. Here is an example:

```latex
\documentclass{article}

\begin{document}

\section{Introduction}

Hello, world!

\end{document}
```

This will create a document with a section titled "Introduction" and the text "Hello, world!".

You can also add subsections using the `\subsection` command, and subsubsections using the `\subsubsection` command.

## Adding Lists

You can add lists to your document using the `itemize` and `enumerate` environments. Itemized lists are bullet points,
and enumerated lists are numbered. Here is an example of an itemized list:

```latex
\documentclass{article}

\begin{document}

\begin{itemize}
    \item Item 1
    \item Item 2
    \item Item 3
\end{itemize}

\end{document}
```

This will create a document with an itemized list with three items.

## Adding Math

You can add math to your document using the `\[` and `\]` delimiters. Here is an example:

```latex
\documentclass{article}

\begin{document}

\[ f(x) = x^2 \]

\end{document}
```

This will create a document with the math equation $f(x) = x^2$.

## Figure, Tables, and Equation environments

You can add figures, tables, and equations to your document using the `figure`, `table`, and `equation` environments.
Here is an example of a figure:

```latex
\documentclass{article}

\begin{document}

\begin{figure}
    \centering
    \includegraphics{example-image-a}
    \caption{An example image}
\end{figure}

\begin{table}
    \centering
    \begin{tabular}{|c|c|c|}
        \hline
        A & B & C \\
        \hline
        1 & 2 & 3 \\
        \hline
    \end{tabular}
    \caption{An example table}
\end{table}

\begin{equation}
    f(x) = x^2
\end{equation}

\end{document}
```
