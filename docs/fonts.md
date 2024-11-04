# Fonts

Fonts are a key element of any written document and so you want to make sure you are utilising them effectively.

LaTeX supports a wide range of fonts and has a number built in and designed specifically for it. However, you can also 
use any font that is installed on your system.

The main distinction is between TrueType (TTF), OpenType (OTF) and Type-1 fonts. TrueType and OpenType are the most 
common and are supported by most modern systems. Type 1 fonts are an older format and are less common.

Type-1 fonts were developed in the 1980s by Adobe and are still widely used in the publishing industry. Around the same
time TrueType fonts were developed in the 1980s by Apple and then OpenType fonts were developed due to a failed attempt
to license Apples typography technology in the 1990s developed by Microsoft and Adobe. 
OpenType fonts are the most modern and are the most feature rich.

The main difference between TrueType and OpenType fonts is that OpenType fonts are able to contain more glyphs and
support more languages. They also have more advanced typographic features such as ligatures, small caps and old style
figures.

Type-1 fonts are the default in LaTeX and are still widely used. However, you can use TrueType and OpenType fonts in
LaTeX.

One of the greatest advantages of LaTeX is its management of typography compared to other document preparation systems.
This is due to the fact that LaTeX is a typesetting system and not a word processor. This means that LaTeX is able to
produce high quality typography that is consistent and professional.

For example the handling of ligatures, kerning and hyphenation is much better in LaTeX than in other systems.

<figure markdown="span">
    ![Ligatures TeX](images/ligatures-tex.png){: style="width:200px"}
    <figcaption>Default Ligatures in LaTeX _(Computer Modern)_</figcaption>
</figure>

<figure markdown="span">
    ![Ligatures Word](images/ligatures-word.png){: style="width:200px"}
    <figcaption>Default ligatures in Word _(Times New Roman)_</figcaption>
</figure>

The default font in LaTeX is Computer Modern. This is a serif font and is designed to be easy to read. However, you may
want to use a different font for your document. This can be done by using the `fontspec` package.

The `fontspec` package allows you to use TrueType and OpenType fonts in LaTeX. It also allows you to set the font size,
font weight and font style. However, you must use a compiler that supports the `fontspec` package such as `XeLaTeX` or
`LuaLaTeX`.

You need to be careful when using non-standard LaTeX fonts as they may not support all the features you require. In
these cases you may need to find additionally packages to provide the features you need. This may include a different
font for math mode or a different font for sans-serif text.

To set the font for your document you need to load the package for the font, for example to use `Helvetica` the 
`\usepackage{helvet}` command should be used. You can then set the font using the 
`\renewcommand{\familydefault}{\sfdefault}` command.

The following is an example of how to set the font to `Helvetica`:

```latex
\documentclass{article}
\usepackage{helvet}
\renewcommand{\familydefault}{\sfdefault}
\begin{document}
This is some text in Helvetica.
\end{document}
```

If you need to set your font a specific family (between `roman`, `sans` and `monospace`), you can use the following
commands:

```latex
\renewcommand{\familydefault}{\rmdefault} % Roman
\renewcommand{\familydefault}{\sfdefault} % Sans-serif
\renewcommand{\familydefault}{\ttdefault} % Monospace
```

This is specific to using LaTeX type fonts in `pdflatex`. If you are using `XeLaTeX` or `LuaLaTeX` you can use the
`fontspec` package to set the font. For example to set the font to `Helvetica` you would use the following commands:

```latex
\documentclass{article}
\usepackage{fontspec}
\setmainfont{Helvetica}
\begin{document}
This is some text in Helvetica.
\end{document}
```

This will set the main font for the document to `Helvetica`. You can also set the font size, weight and style using the
`fontspec` package.

You can see it's a bit simpler to control fonts in the `XeLaTeX` and `LuaLaTeX` engines. However, you can still use
`pdflatex` to use TrueType and OpenType fonts.
