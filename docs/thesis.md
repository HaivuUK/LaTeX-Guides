# Writing a Thesis in LaTeX

Here you will find a template for writing a thesis in LaTeX. This template is designed to be a starting point for
writing. It should not require changes to the document class, and should be able to be used as is.

<center>
[:fontawesome-solid-download: Thesis Template](templates/template-for-guide.zip){:download="Thesis Template" .md-button}
</center>

## Usage

To use this template locally, download the zip file and extract it to a location on your computer. You can then open the
`thesis-main.tex` file in your LaTeX editor and start writing your thesis from there.

To use this template in Overleaf, download the zip file and start a new project in Overleaf by uploading the zip file.
This should make a new project setup with the template files.

## Structure

The structure of the template is as follows:

- `thesis-main.tex` - The main file for the thesis. This is where the document class is set and the document is built.
- `chp1/` - A folder containing the first chapter of the thesis. Each chapter should be a separate folder for be management.
- `chp2/` - A folder containing the second chapter of the thesis.
- `preamble.tex` - A file containing the preamble for the document. This is where packages are loaded and settings are set.
- `refs.bib` - A file containing the references for the document. This is where the bibliography is stored.
- `guidethesis.cls` - A class file for the thesis. This is where the document class is defined.
- `abstract.tex` - A file containing the abstract for the thesis. This is where the abstract is stored.
- `acknowledgements.tex` - A file containing the acknowledgements for the thesis. This is where the acknowledgements are stored.
- `dedication.tex` - A file containing the dedication for the thesis. This is where the dedication is stored.
- `appendix1.tex` - A file containing the first appendix for the thesis. This is where the appendix is stored.
- `appendix2.tex` - A file containing the second appendix for the thesis.

For more information on structuring the thesis please refer to [Multi-file Projects](multifile-docs.md).

## Features

The template has a number of features that are designed to make writing a thesis easier. These include:

- Allowance for multiple logos on the title page, predefined using the `setcustomlogo` command.
- Supervisor declaration, which switches between plural and singular depending on the number of supervisors.
- Predefined fix for subfix and bibliography autocompletion.
- etc

!!! note
    If you find any issues with the template, please raise an issue on the repository or contact the author.