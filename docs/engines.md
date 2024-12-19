# LaTeX Engines/Compilers

!!! Note
    _**TLDR: Use pdfLaTeX unless you need specific features that it does not support at which point LuaLaTeX is recommended.**_

## How to specify the LaTeX compiler

LaTeX compilers are specified using magic comments. These are comments that are placed at the beginning of the LaTeX
document and are used to specify the compiler that should be used to compile the document. The most common magic comment
is: 
```
% !TeX program = lualatex
```
Which specifies that the document should be compiled using LuaLaTeX. Other magic comments can be used to specify 
different compilers, such as pdfLaTeX or XeLaTeX.

For more information on magic comments, please refer to the [Magic Comments](magic-coms.md)

## Specificities of LaTeX Compilers

As previously discussed on the introduction page, LaTeX is not a standalone typesetting program/new language/or engine, 
but rather is a collection of TeX macros that work to improve and make the functionality of TeX more accessible. And
were created by Leslie Lamport in the 1980s.

When the original TeX code was frozen in the 1980s, it had basic functionality that Knuth thought would be sufficient
for most users. However, technology changes alot and so alternative engines were created to improve on the original and
support LaTeX. These engines are:

### **pdfLaTeX**
This is an extension of TeX that can create PDF directly from TeX source files. It is the 
default engine for most LaTeX distributions. PdfLaTeX is the fastest engine available, but it does not support Unicode.
or OpenType fonts, which can be a limitation for some users. If you need fonts like Calibri, Arial, or Cambria, you will
need to use XeLaTeX or LuaLaTeX.

### **XeLaTeX**
This is a Unicode-based TeX system that can create PDF directly from TeX source files. It is an 
alternative to pdfLaTeX and is used for more complex scripts and fonts. However, it is slower than pdfLaTeX and has
not been actively developed since about 2017.

### **LuaLaTeX**
This is an extended version of pdfLaTeX that can create PDF directly from TeX source files. It 
is used for more complex scripts and fonts. LuaLaTeX is the most modern engine available and is actively developed.
It is based on Lua, a powerful scripting language that is easy to learn and use. LuaLaTeX is the most flexible engine
available and can be used for a wide range of projects. It is the slowest engine to compile but is the most powerful.

### **Tectonic**
This is a modernised, complete, self-contained TeX/LaTeX engine that is based on XeTeX and TeXLive. It
is used for more complex scripts and fonts. It is faster than XeLaTeX and LuaLaTeX and is actively developed. However,
it is not as flexible as LuaLaTeX and does not support all the features of LuaLaTeX. It additionally acts as a
package manager for LaTeX packages.

This list does not include all the engines available, but these are the most commonly used engines for LaTeX. Each 
engine has its own strengths and weaknesses, and the best engine for you will depend on your specific needs but general
guidance is to remain on pdfLaTeX unless you need specific features that it does not support at which point LuaLaTeX is
recommended.

For more information on the engines, please refer to the 
[LaTeX Wikibook](https://en.wikibooks.org/wiki/LaTeX/Introduction) or 
[Overleaf](https://www.overleaf.com/learn/latex/Articles/What%27s_in_a_Name%3A_A_Guide_to_the_Many_Flavours_of_TeX).

## Additional Engine Enhancements

**PythonTeX** is a LaTeX package that allows you to write and execute Python code in your LaTeX documents. 
It is a powerful tool that can be used to create dynamic documents that include data analysis, visualizations, and
other computational tasks. PythonTeX is a great way to combine the power of Python with the elegance of LaTeX.

**Sweave** is a tool that allows you to embed R code in your LaTeX documents. It is similar to PythonTeX but is
specifically designed for R. 
