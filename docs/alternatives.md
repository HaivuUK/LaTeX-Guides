# Alternatives to LaTeX

## Why LaTeX?

Over the years the LaTeX typesetting system has become the gold standard for academic and scientific documents.
However, in the same time word processors have become more powerful and easier to use. So why should you use LaTeX?

Regardless of the progress of word processors, many still do not match the features or typesetting quality of LaTeX.

Below are some deep dives into LaTeX compared to other document preparation or typesetting systems.

- [On Typesetting Engines: A Programmer's Perspective](https://blog.ppresume.com/posts/on-typesetting-engines#cjk-character-set-is-huge)
  * A recent comparison of LaTeX, Typst, HTML & CSS, LaTeX.js, and React-pdf.
  * While the focus is on picking a typsetting engine for a resume builder the comparison is still useful.
  
| Typesetting Engine | Knuth Plass line breaking |   CJK   | Pagination | Instant Preview |
|:------------------:|:-------------------------:|:-------:|:----------:|:---------------:|
| HTML & CSS         |            No             |   Yes   |  Partial   |       Yes       |
| LaTeX              |            Yes            |   Yes   |    Yes     |       No        |
| LaTeX.js           |            No             |   Yes   |     No     |       Yes       |
| Typst              |            Yes            | Partial |    Yes     |     Partial     |
| React-pdf          |            Yes            |   No    |    Yes     |       Yes       |


- [LaTeX vs. Word: Main Differences](https://www.baeldung.com/cs/latex-vs-word-main-differences)
    * A fairly surface level comparison of LaTeX and Word.

- [The Beauty of LaTeX](https://nitens.org/w/latex/)
  * A deep dive in to the difference of word processors and LaTeX that focusing on typesetting quality.
  * It a really strong comparison of the difference that may not be initially obvious but make LaTeX shine.
  * The article has not been updated since 2015 and word processors have made progress since then but the 
  information is still relevant.

## Markdown

Markdown is a lightweight language with plain text formatting syntax. It is designed so that it can be converted to 
HTML and many other formats using a tool by the same name. Markdown is often used to format readme files, for writing 
messages in online discussion forums, and to create rich text using a plain text editor.

It is used in many places, including GitHub, Reddit, and Stack Exchange. It is also used in the documentation for
many projects, including this one, or popular note-taking applications like Obsidian.

There are multiple flavours of markdown, with GitHub Flavored Markdown (GFM) being the most popular. Each flavour has 
its own extensions and limitations.

**Advantages**

- Easy to learn
- Easy to read
- Easy to write
- Easy to convert to other formats
- Can be used in many places
- Can be used in many tools
- Supports extensions

**Disadvantages**

- Limited formatting options
- Limited layout options
- Limited support for complex documents

An example of a Markdown document:

```markdown
# Markdown Example

This is an example of a markdown document.

## Section 1

This is the first section.

### Subsection 1

This is a subsection.

We can write text with **bold** and *italic* formatting.

- We can also create lists
- Like this one

1. And numbered lists
2. Like this one

Math is also supported, like $x^2$. Using LaTeX syntax.
```

Although slightly more complex you can also use HTML, CSS, and JavaScript in markdown documents. Or use pandoc to
create cross-references.

For simple documents, markdown is a great choice and much quicker to get going with than LaTeX. However, for more 
complex documents, you may want to consider LaTeX.

Using markdown with pandoc can also be a good way to get the best of both worlds. You can write in markdown and then
convert to LaTeX or use a LaTeX template for pdf export. Markdown generally converts to word documents well too.

## Typst

Typst is a new language that is designed to be a concise modern alternative to LaTeX. It is designed to be easy to
write and read, while still providing similar power to LaTeX. It does not have the same level of complexity as LaTeX,
and is available as a web-based editor.

However, it does not have the same level of support as LaTeX, and is not as widely used. Although its typesetting 
produces similarly nice results to LaTeX.

An example of Typst code:

```typst
#show: elsearticle.with(
  title: "Title of the paper",
  authors: (
    (
      name: "A. Author",
      affiliation: "University A, City A, Country A",
      corr: "a.author@univa.edu",
      id: "a",
    ),
    (
      name: "B. Author",
      affiliation: "University B, City B, Country B",
      corr: none,
      id: "b"
    ),
    (
      name: lorem(2),
      affiliation: none,
      corr: none,
      id: "a",
    ),
    (
      name: lorem(3),
      affiliation: none,
      corr: none,
      id: "a",
    ),
    (
      name: "A. Author",
      affiliation: none,
      corr: none,
      id: "a",
    ),
    (
      name: "A. Author",
      affiliation: none,
      corr: none,
      id: "a",
    ),
  ),
  journal: "Name of the Journal",
  abstract: abstract,
  keywords: ("keyword 1", "keyword 2"),
  format: "review"
)

= Introduction

#lorem(100)

= Section 1

#lorem(50)

== Subsection 1

#lorem(10) (see @eq1) @Aut10.

$
y = a x +b
$ <eq1>
where ...

== Features

=== Table

Below is @tab:tab1.

#let tab1 = {
  table(
  columns: 3,
  table.header(
    [*Header 1*],
    [*Header 2*],
    [*Header 3*],
  ),
  [Row 1], [12.0], [92.1],
  [Row 2], [16.6], [104],
)
}

#figure(
    tab1,
    kind: table,
    caption : [Example]
) <tab:tab1>

=== Figures

Below is @fig:logo.

#figure(
  image("images/typst-logo.svg", width: 50%),
  caption : [Typst logo - Credit: \@fenjalien]
) <fig:logo>

=== Subfigures

Below are @figa and @figb, which are part of @fig:typst.

#subfigure(
figure(image("images/typst-logo.svg"), caption: []), <figa>,
figure(image("images/typst-logo.svg"), caption: []), <figb>,
columns: (1fr, 1fr),
caption: [(a) Left image and (b) Right image],
label: <fig:typst>,
)

#show: appendix

= Appendix A

== Figures

In @fig:app

#figure(
  image("images/typst-logo.svg", width: 50%),
  caption : [Books cover]
) <fig:app>

== Subfigures

Below are @figa-app and @figb-app, which are part of @fig:typst-app.

#subfigure(
figure(image("images/typst-logo.svg"), caption: []), <figa-app>,
figure(image("images/typst-logo.svg"), caption: []), <figb-app>,
columns: (1fr, 1fr),
caption: [(a) Left image and (b) Right image],
label: <fig:typst-app>,
)

== Tables

In @tab:app

#figure(
    tab1,
    kind: table,
    caption : [Example]
) <tab:app>

== Equations

In @eq

$
y = f(x)
$ <eq>

#nonumeq[$
    y = g(x)
    $
]

#bibliography("refs.bib")
```

## ConTeXt

ConTeXt is another fork of TeX taking a different approach to LaTeX. It is designed to be more consistent but equally
flexible to LaTeX. 

ConTeXt tries to avoid the need to load packages to limit the complexity. And its integration by design with Lua and
MetaPost makes it very flexible.

It is near identical to LaTeX in typesetting, although they differ slightly. It however is not as widely used as LaTeX.

An example of ConTeXt code:

```tex
\setuppapersize[A4]

\setupbodyfont [palatino]

\definecolor [Top] [h=a5b291]
\definecolor [Bottom] [h=b7c1a7]
\definecolor [TitleColor] [h=96433a]

\define[1]\titlefont{%
  \setcharacterkerning[extrakerning]%
  \cap
  \definedfont[#1]%
  \ignorespaces
}

\starttext

\startMPpage

    StartPage ;

    numeric w ; w := bbwidth(Page) ;
    numeric h ; h := bbheight(Page) ;

    fill (unitsquare xyscaled (w,.8h)) withcolor \MPcolor{Bottom} ;
    fill (unitsquare xyscaled (w,.2h) yshifted .8h) withcolor \MPcolor{Top} ;
    draw (0,.8h) -- (w,.8h) withpen pensquare scaled 2pt withcolor white ;

    draw textext.rt("\definedfont[Serif at 10pt]G H Allison") shifted (.1w,.95h) ;
    draw textext.rt("\titlefont{Serif at 20pt} A ConTeXt Example") shifted (.1w,.85h) withcolor \MPcolor{TitleColor} ;
    draw textext.rt("\titlefont{SerifBold at 10pt} An alternative to LaTeX") shifted (.1w,.75h) withcolor \MPcolor{TitleColor} ;
    draw textext.rt("\titlefont{SerifBold at 10pt} Use google if you want to know more") shifted (.1w,.70h) ;


%    picture p; p := externalfigure "matterhorn.png" ;
%    draw p scaled (w/bbwidth p) ;

    StopPage ;

\stopMPpage

\definedfont[Serif at 10pt]

\section{Section 1}
This is the first section.

\subsection{Subsection 1}
This is a subsection.

We can write text with \bold{bold} and \italic{italic} formatting.

\startitemize
\item We can also create lists
\item Like this one
\stopitemize

{
\setupTABLE[framecolor=black]

\bTABLE
    \bTR  \bTD[row=1,col=1]  1  \eTD  \bTD[row=1,col=2]  2  \eTD  \bTD[row=1,col=3]  3  \eTD  \eTR
    \bTR  \bTD[row=2,col=1]  2  \eTD  \bTD[row=2,col=2]  2  \eTD  \bTD[row=2,col=3]  2  \eTD  \eTR
    \bTR  \bTD[row=3,col=1]  3  \eTD  \bTD[row=3,col=2]  2  \eTD  \bTD[row=3,col=3]  1  \eTD  \eTR
\eTABLE}


\stoptext
```

The similarity to LaTeX is clear. If you would like to try out ConTeXt, you can use the online editor at
[ConTeXt on Web](https://live.contextgarden.net).

## MS Word

You can use this if you want.