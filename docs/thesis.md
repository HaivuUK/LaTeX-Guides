# Writing a Thesis in LaTeX

!!! note
    This template uses expl features in LaTeX3 and requires at least a 2024 distribution of LaTeX. Tested working on
    Overleaf and TeXLive 2024 as of 06-November-2024.

Here you will find a template for writing a thesis in LaTeX. This template is designed to be a starting point for
writing. It should not require changes to the document class, and should be able to be used as is.

<center>
[:fontawesome-solid-download: $\LaTeX3$ Thesis Template](https://github.com/HaivuUK/LaTeX-Guides/raw/refs/heads/main/docs/templates/template-for-guide.zip){:download="Thesis Template" .md-button}
</center>

## Usage

To use this template locally, download the zip file and extract it to a location on your computer. You can then open the
`thesis-main.tex` file in your LaTeX editor and start writing your thesis from there.

To use this template in Overleaf, download the zip file and start a new project in Overleaf by uploading the zip file.
This should make a new project setup with the template files.

## Structure

The structure of the template is as follows:

```tree
├─ guidethesis.cls                      # Class file for the thesis. This defines how the document should be formatted.
├─ thesis-main.tex                      # Main document. This is the main file where the document is organised.
├─ chp1/                                # Subfolder for chapter 1. For simplicity each chapter is in its own folder.
│   └─ doc1.tex                         # Subfile for chapter 1
├─ chp2/                                # Subfolder for chapter 2
│   └─ doc2.tex                         # Subfile for chapter 2
├─ preamble.tex                         # Preamble for the document. This is where packages are loaded and settings are set.
├─ refs.bib                             # Bibliography file
├─ abstract.tex                         # Abstract for the thesis
├─ acknowledgements.tex                 # Acknowledgements for the thesis
├─ dedication.tex                       # Dedication for the thesis
├─ appendix1.tex                        # First appendix for the thesis
└─ appendix2.tex                        # Second appendix for the thesis
```

The structure inside the main document is as follows:

```latex
├─ Engine Declaration
├─ Document Metadata Declaration
├─ Document Class Declaration
├─ Preamble
├─ Bibliography Resources
├─ Title Page Declarations
├─ Document Start/
│   ├─ Make Title Command
│   ├─ Dedication
│   ├─ Acknowledgements
│   ├─ Abstract
│   ├─ Table of Contents
│   ├─ List of Figures
│   ├─ List of Tables
│   ├─ Chapter 1/
│   │   └─ Chapter 1
│   ├─ Chapter 2/
│   │   └─ Chapter 2
│   ├─ Appendix 1
│   ├─ Appendix 2
│   └─ Bibliography
```



For more information on structuring the thesis please refer to [Multi-file Projects](multifile-docs.md).

## Features

The template has a number of features that are designed to make writing a thesis easier. These include:

- Allowance for multiple logos on the title page, predefined using the `setcustomlogo` command.
- Supervisor declaration, which switches between plural and singular depending on the number of supervisors.
- Predefined fix for subfix and bibliography autocompletion.
- etc

!!! note
    If you find any issues with the template, please raise an issue on the repository or contact the author.