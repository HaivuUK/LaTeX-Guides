# Conversion

Occasionally, you may need to convert a LaTeX document to a different format. There are a few tools and ways to do
this, but the most common are:

- [Pandoc](https://pandoc.org/)
- [TeX4ht](https://tug.org/tex4ht/)
- PDF to Word converters

!!! Note
    As documents become more complex, the conversion process becomes more difficult. This is especially true for 
    documents that use a lot of custom packages or custom commands. In these cases, you may need to do some manual 
    editing after the conversion. It is often easier to convert the PDF to the desired format or convince the recipient 
    to accept the PDF/TeX.

## PDF to Word Converters

This is the quick and dirty method of converting a LaTeX document to a Word document. It is not perfect, and you will
likely need to do some manual editing afterward, but it is a good starting point if you need a one-off conversion.

There are a few PDF to Word converters available, but the most popular and widely used is Adobe Acrobat Pro. This is a
paid software, but it is the most reliable and accurate I have used to date. It does offer a free alternative through
a web interface, but this is more limited.

[Adobe PDF to Word Converter](https://www.adobe.com/uk/acrobat/online/pdf-to-word.html)

MS Word (and other word processor alternatives: OpenOffice, LibreOffice, WPS Office) also has a built-in PDF to Word 
converter, but it is not as accurate as Adobe's. It is free, however, so it is worth trying if you do not have access 
to Adobe Acrobat Pro. You can find this feature under the `File` menu, then `Open`, and select the PDF file you want 
to convert. The accuracy of this tool is highly dependent on the complexity of the document, so you may need to do 
some manual editing afterward.

## [Pandoc](https://pandoc.org/)

Pandoc is a universal document converter that can convert between a wide range of formats. It is a command-line tool,
so it is not as user-friendly as some other tools, but it is very powerful and flexible. It can convert between LaTeX,
Word, HTML, Markdown, and many other formats.

Using it can be as simple as running the following command:

```bash
pandoc input.tex -o output.docx
```

Where the document becomes more complex, you may need to provide additional options to get the desired output. The
[Pandoc documentation](https://pandoc.org/MANUAL.html) is very comprehensive and provides a lot of information on how
to use the tool. However, here is a general command that works very well for most complex LaTeX documents:

```bash
pandoc --mathjax --filter pandoc-crossref --toc --citeproc --bibliography "refs.bib" --csl "https://raw.githubusercontent.com/citation-style-language/styles/master/vancouver.csl" -s "input.tex" -o "output.docx" -t docx+native_numbering+smart
```

And if you build a multi-file document, you can use the following command:

```bash
pandoc --mathjax --filter pandoc-crossref --toc --citeproc --bibliography "refs.bib" --csl "https://raw.githubusercontent.com/citation-style-language/styles/master/vancouver.csl" -s "input.tex" --resource-path="folder1" --resource-path="folder2" -o "output.docx" -t docx+native_numbering+smart
```

Where the additions are the `--resource-path` flags, which tell Pandoc where to look for the additional files.

It should be noted that Pandoc does not support all LaTeX packages, specifically TikZ and PGFPlots. If you use these
packages, you will need to convert the TikZ code to an image and include it in the document manually. This can be done
using the `standalone` package and the `convert` option. For example:

```latex
\documentclass[convert={density=300,outext=.png}]{standalone}
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
    \draw (0,0) circle (1in);
\end{tikzpicture}
\end{document}
```

Or there are pandoc filters available that can convert TikZ code to images, but these are not as reliable as the
standalone method.

### Citations styles

Pandoc uses CSL (Citation Style Language) files to format citations and bibliographies. You can find a wide range of
styles on the [CSL repository](https://github.com/citation-style-language/styles). To use a CSL file, you can provide
the URL to the file using the `--csl` flag, as shown in the command above. You can also provide a local file if you
have one.

Ensure that if you are providing a link to the git repository, you use the raw link to the file, not the HTML page.

## [TeX4ht](https://tug.org/tex4ht/) and [make4ht](https://ctan.org/pkg/make4ht)

!!! Note
    make4ht cannot directly convert to docx (word documents), but it can convert to odt (Open Document Text) files,
    which can be opened in Word.

TeX4ht is another LaTeX to HTML converter that can convert LaTeX documents to a wide range of formats, including HTML,
XML, and ePub. It is a very powerful tool, but it is not as user-friendly as Pandoc.

There is an extension to TeX4ht called `make4ht` that provides a more user-friendly interface and additional features.
It is worth looking into if you are interested in using TeX4ht as it is the current best way to use the tool.

Make4ht can natively convert TikZ code to SVG images, which is a big advantage over Pandoc. However, it struggles with
image scaling and positioning which requires you to run an additional command to ensure they are correctly placed in
the document.

The basic command to convert a LaTeX document to odt using make4ht is:

```bash
make4ht -f odt filename.tex
```

Converting more complex documents may require additional options, but the make4ht documentation is very comprehensive
and provides a lot of information on how to use the tool.

