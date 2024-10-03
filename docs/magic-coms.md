# Magic Comments

!!! Note
    These should work for most LaTeX editors, but some may have specific requirements or additional options.

Magic comments are placed at the beginning of a document and affect how the editor handles the document.

This list is not exhaustive, but covers the most common magic comments.

## Compiler Selection

The compiler can be selected using:

```latex
% !TeX program = lualatex
```

This will compile the document using LuaLaTeX. Other options include:

- `pdflatex`
- `xelatex`

## Encoding

!!! Note
    This is not required for most documents. And LaTeX3 by default uses UTF-8 encoding.

The encoding can be selected using:

```latex
% !TeX encoding = UTF-8
```

This will set the encoding to UTF-8. Other options include:

- `latin1`
- `latin9`
- `ascii`

## Spell Check

The spell check language can be selected using:

```latex
% !TeX spellcheck = en_GB
```

This will set the spell check language to British English. Other options include:

- `en_US`
- `de_DE`

## TeX Root

The root document can be specified using:

```latex
% !TeX root = main.tex
```

This will set the root document to `main.tex`. This is useful for multi-file documents.
