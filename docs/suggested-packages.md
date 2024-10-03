# Suggested Packages

This is a list of suggested packages that you can install to enhance your experience with LaTeX or have a base preamble
to start with.

```latex
\usepackage{standalone} % Required for including standalone files

\usepackage{geometry} % Required for adjusting page dimensions and margins
\geometry{verbose,tmargin=2.54cm,bmargin=2.54cm,lmargin=2.54cm,rmargin=2.54cm} % Set the margins

\usepackage{amssymb} % For math symbols
\usepackage{amsmath} % For math extended mode
\usepackage{amstext} % For text in math mode
\usepackage{arevmath} % For math symbols
\usepackage{mathtools} % Allows for additional math symbols

\usepackage{graphicx} % Required for including images
\usepackage{float} % Allows putting an [H] in \begin{figure} to specify the exact location of the figure

\usepackage{tikz}
\usetikzlibrary{arrows.meta,patterns.meta,shapes}
\usetikzlibrary{matrix,positioning}

\usepackage{pgfplots}
\pgfplotsset{compat=1.18}
\usepackage{pgfplotstable}
\usepgfplotslibrary{groupplots}
\usepgfplotslibrary{colormaps,statistics}

\renewcommand{\familydefault}{\sfdefault} % Define the default font family

\usepackage[l3]{csvsimple}
\usepackage{booktabs}
\usepackage{array}
\usepackage[fitting,most]{tcolorbox}
\usepackage{subcaption}
\usepackage{refstyle}
\usepackage{siunitx}

\usepackage{zref-clever} % Clever zref support
\usepackage{zref-xr} % Cross-referencing between documents
\usepackage{hyperref} % Hyperlinks

\usepackage{tabularray} % Current preferred package for tables
\usepackage{etoolbox} % Provdies a list of tools for programming in LaTeX
\usepackage{setspace} % Provides the \onehalfspacing command
\onehalfspacing
\usepackage{polyglossia} % Required for multilingual documents

\usepackage{glossaries} % Required for creating glossaries
\setacronymstyle{long-sc-short} % Set the acronym style

\setdefaultlanguage[variant=british]{english} % Set the default language
\usepackage[obeyFinal,textsize=scriptsize]{todonotes} % Required for adding todo notes/comments
\usepackage{pdfpages} % Required for including PDFs
\usepackage{datetime2} % Required for date and time formatting
```