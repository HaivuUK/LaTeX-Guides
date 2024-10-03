# Cross-referencing

!!! Note
    It is recommended to use all these packages together to get the best cross-referencing experience in LaTeX.

## zref

zref provides flexible and extensible cross-referencing capabilities in LaTeX. It allows you to create custom labels 
and references, and provides better support for complex cross-referencing in your document. It also provides better 
support for custom reference styles, allowing you to easily create your own reference styles. It provides the base 
for two more advanced packages, `zref-xr` and `zref-clever`.

## zref-xr

zref-xr provides better support for cross-referencing between multiple documents. It allows you to easily reference
labels in other documents, and provides better support for complex cross-referencing between multiple documents. This
is fundamental for creating complex documents with multiple parts, chapters, or sections that need to reference each
other.

To set up cross document cross-referencing it is recommended to create a document list file that contains the paths to
the documents you want to cross-reference. The code to include in your document is as follows:

```latex
\ProvidesPackage{doc-list}

\RequirePackage{zref-xr}
\RequirePackage{hyperref}

\zexternaldocument{chapter1}
\zexternaldocument{chapter2}
\zexternaldocument{section1}
\zexternaldocument{appendix}
\zexternaldocument{conclusion}
\zexternaldocument{chapter3}
```

In this example, the `doc-list` package is created to include the documents you want to cross-reference. The
`\zexternaldocument` command is used to include the paths to the documents you want to cross-reference. This file would
need to be saved as `doc-list.sty` and included in all your documents that you want to cross-reference.

## zref-clever

zref-clever provides better support for clever cross-referencing in LaTeX. It allows you to easily reference labels
with additional information, such as the page number, section number, or chapter number. This allows you to keep your
cross-references consistent and informative, and removes the need to manually think about the formatting of your
cross-references.

To use zref-clever, you need to include the following code in your preamble:

```latex
\usepackage{zref-clever}
```

This will load the zref-clever package and provide you with the additional cross-referencing capabilities it offers.

You will then be able to use the `\zcref` command to reference labels with additional information. For example,
`\zcref{label}` will reference the label with the page number, section number, or chapter number, depending on the
context of the reference. If you need to capitalize the reference you can use `\zcref[S]{label}`.

## Calling cross-references

To be able to cross-reference back to an item you need to have a label on the item you want to reference. When using
`zref` you can use the `\zlabel` command to create a label. For example:

```latex
\begin{figure}
    \centering
    \includegraphics{example.png}
    \caption{An example image}
    \zlabel{fig:example}
\end{figure}

As seen in Figure \zcref{fig:example}, this is an example image.
```

In this example, the `\zlabel` command is used to create a label for the figure. The `\zcref` command is then used to
reference the label in the text. This will automatically insert the correct reference information, in this case it
would insert $\text{Figure 1}$ into the text.

It is generally good practice to use a consistent naming convention for your labels to make it easier to remember and
reference them. For example, using `fig:` for figures, `tab:` for tables, `sec:` for sections, `ch:` for chapters, 
`eq:` for equations, etc.


