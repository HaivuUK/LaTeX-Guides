# Accessibility in LaTeX

!!! note
    Accessibility in LaTeX is an ongoing project. The information in this section was last updated in November 2024.

LaTeX is a typesetting system first and foremost. This means that during its development, there was not a focus on 
accessibility. However, since the development of LaTeX3 there has been a focus on improving the accessibility of LaTeX
documents. This has been done through development from Ulrike Fischer and the LaTeX3 team.

To see the status of accessibility in LaTeX, you can visit the 
[LaTeX3 GitHub page](https://latex3.github.io/tagging-project/tagging-status/).

For further information on the how-to setup accessibility in LaTeX, you can visit the 
[Accessibility Usage Instruction](https://latex3.github.io/tagging-project/documentation/prototype-usage-instructions.html)
page.

The majority of packages in LaTeX are accessibility friendly with a few exceptions. There are five document classes that
are fully compatible. These are:

- `article`
- `report`
- `book`
- `ltugboat`
- `proc`

Implementing accessibility in LaTeX is done through the basic addition of a document metadata class at the start of the
document before the `\documentclass`.

```latex
\DocumentMetadata{
  lang        = en,
  pdfversion  = 2.0,
  pdfstandard = ua-2,
  pdfstandard = a-4f, %or a-4
  testphase   = 
   {phase-III,
    title,
    table,
    math,
    firstaid}  
}
\documentclass{....}
```

This makes short document metadata performs a lot of work in the background to make the document accessible. This
redefines a number of commands to ensure that the document is accessible. This is a great first start to making an
accessible document. However, there are additional steps that can be taken to improve the accessibility of a document.

For images that are being loaded through the `\includegraphics` command, the new `alt` key can be used to add 
alternative text to the image.

```latex
\includegraphics[alt={This is an image}]{example-image}
```

If there is not a suitable alternative text to be added the image can be marked as decorative by declaring it as an
artifact.

```latex
\includegraphics[artifact]{example-image}
```

Unfortunately there is no way to add alternative text to tikz images or float environments such as tables and figures.
This is a limitation of LaTeX and is something that is being worked on by the LaTeX3 team.

For more information please refer to the following documents by Ulrike Fischer and Frank Mittelbach:

- [Automated tagging of LaTeX documents - What is possible today in 2023](https://www.latex-project.org/publications/2023-UFi-FMi-TUG-tb137fischer-tagging23.pdf)
- [Enhancing LaTeX to automatically produce tagged and accessible PDF](https://www.latex-project.org/publications/2024-FMi-UFi-TUB-tb139mitt-deims24.pdf)



!!! note
    The beamer package is not currently accessible. This is due to the way that beamer is designed. There is work being
    done to make beamer accessible, but it is not currently accessible.
