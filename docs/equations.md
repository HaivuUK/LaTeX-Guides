# Equations/Maths/Formulae

!!! Not
    LaTeX Equations do not break across pages. If you have a long equation that needs to break across pages, you can use
    the `breqn` package. This package will automatically break equations across pages. To use the `breqn` package, you
    can add the following line to the preamble of your document:
    ```latex
    \usepackage{breqn}
    ```


Writing equations is one of the most powerful features of LaTeX. 
It is one of the main reasons that people use LaTeX for academic writing and one of its largest advantages over
processors like word. 
This section will cover the basics of writing equations in LaTeX and some particular cases.

For most mathematical writing, you will want to use the `amsmath` package.
This package provides a number of useful tools for writing equations and is the most commonly used package for writing
equations in LaTeX.
To use the `amsmath` package, you can add the following line to the preamble of your document:

```latex
\usepackage{amsmath}
```

If you want to write matrices, you can use the `amsmath` package with the `amssymb` package.
The `amssymb` package provides a number of useful symbols for writing equations.
To use the `amssymb` package, you can add the following line to the preamble of your document:

```latex
\usepackage{amssymb}
```

If you want to write piecewise functions, you can use the `cases` package.
The `cases` package provides the `numcases` environments for writing piecewise functions.
To use the `cases` package, you can add the following line to the preamble of your document:

```latex
\usepackage{cases}
```


## Basic Syntax

The basic syntax for writing equations in LaTeX is to use the `$` symbol to denote the start and end of the maths
environment.
For example, to write the equation $E = mc^2$ you would write:

```latex
$E = mc^2$
```

This will produce the following equation:

$$
E = mc^2
$$

If you want to write an equation that is displayed on its own line, you can use the `\[` and `\]` symbols.
For example, to write the equation $E = mc^2$ on its own line you would write:

```latex
\[
    E = mc^2
\]
```

To make particular elements of maths please refer to the following table:

|           Element            |              Syntax               |                             Example                              |                              Output                              |
|:----------------------------:|:---------------------------------:|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
|          Subscript           |                `_`                |                              `x_1`                               |                              $x_1$                               |
|         Superscript          |                `^`                |                              `x^2`                               |                              $x^2$                               |
|           Fraction           |  `\frac{numerator}{denominator}`  |                          `\frac{1}{2}`                           |                          $\frac{1}{2}$                           |
|         Square Root          |        `\sqrt{expression}`        |                            `\sqrt{2}`                            |                            $\sqrt{2}$                            |
|             Root             |      `\sqrt[n]{expression}`       |                          `\sqrt[3]{2}`                           |                          $\sqrt[3]{2}$                           |
|          Summation           |       `\sum_{start}^{end}`        |                         `\sum_{i=1}^{n}`                         |                         $\sum_{i=1}^{n}$                         |
|           Product            |       `\prod_{start}^{end}`       |                        `\prod_{i=1}^{n}`                         |                        $\prod_{i=1}^{n}$                         |
|           Integral           |       `\int_{start}^{end}`        |                          `\int_{0}^{1}`                          |                          $\int_{0}^{1}$                          |
|       Contour Integral       |       `\oint_{start}^{end}`       |                         `\oint_{0}^{1}`                          |                         $\oint_{0}^{1}$                          |
|            Limit             |         `\lim_{x \to a}`          |                         `\lim_{x \to 0}`                         |                         $\lim_{x \to 0}$                         |
|            Matrix            | `\begin{matrix} ... \end{matrix}` |           `\begin{matrix} 1 & 2 \\ 3 & 4 \end{matrix}`           |           $\begin{matrix} 1 & 2 \\ 3 & 4 \end{matrix}$           |
|            Cases             |  `\begin{cases} ... \end{cases}`  | `\begin{cases} 1 & x > 0 \\ 0 & x = 0 \\ -1 & x < 0 \end{cases}` | $\begin{cases} 1 & x > 0 \\ 0 & x = 0 \\ -1 & x < 0 \end{cases}$ |
|     Binomial Coefficient     |          `\binom{n}{k}`           |                          `\binom{n}{k}`                          |                          $\binom{n}{k}$                          |
|          Derivative          |          `\frac{d}{dx}`           |                          `\frac{d}{dx}`                          |                          $\frac{d}{dx}$                          |
|      Partial Derivative      |   `\frac{\partial}{\partial x}`   |                  `\frac{\partial}{\partial x}`                   |                  $\frac{\partial}{\partial x}$                   |
|            Vector            |             `\vec{v}`             |                            `\vec{v}`                             |                            $\vec{v}$                             |
|         Bold Symbol          |           `\mathbf{v}`            |                           `\mathbf{v}`                           |                           $\mathbf{v}$                           |
|       Variable Bracket       |       `\left( ... \right)`        |                   `\left( \frac{1}{2} \right)`                   |                   $\left( \frac{1}{2} \right)$                   |
|    Variable Curly Bracket    |      `\left\{ ... \right\}`       |                  `\left\{ \frac{1}{2} \right\}`                  |                  $\left\{ \frac{1}{2} \right\}$                  |
|   Variable Square Bracket    |       `\left[ ... \right]`        |                   `\left[ \frac{1}{2} \right]`                   |                   $\left[ \frac{1}{2} \right]$                   |
|    Variable Angle Bracket    | `\left\langle ... \right\rangle`  |             `\left\langle \frac{1}{2} \right\rangle`             |             $\left\langle \frac{1}{2} \right\rangle$             |
| Variable Single Vertical Bar |      `\left\| ... \right\|`       |                  `\left\| \frac{1}{2} \right\|`                  |              $\left\lvert \frac{1}{2} \right\rvert$              |
| Variable Double Vertical Bar |     `\left\\| ... \right\\|`      |                 `\left\\| \frac{1}{2} \right\\|`                 |                  $\left\| \frac{1}{2} \right\|$                  |
|        Variable Floor        | `\left\lfloor ... \right\rfloor`  |             `\left\lfloor \frac{1}{2} \right\rfloor`             |             $\left\lfloor \frac{1}{2} \right\rfloor$             |
|       Variable Ceiling       |  `\left\lceil ... \right\rceil`   |              `\left\lceil \frac{1}{2} \right\rceil`              |              $\left\lceil \frac{1}{2} \right\rceil$              |




For more information on writing equations in LaTeX, please refer to the 
[Overleaf documentation](https://www.overleaf.com/learn/latex/Mathematical_expressions).

If you want to practice writing equations in LaTeX, you can use the fun online game [TeXnique](https://texnique.xyz/).
And if there is something you want to write but you are not sure how to do it, you can use the 
[Detexify](http://detexify.kirelabs.org/classify.html) tool to find the LaTeX command for the symbol you want to write.




## Basic Equations

The most basic way to write an equation in LaTeX is to use the `equation` environment.
This will automatically number the equation and place it in the centre of the page.
Here is an example:

```latex
\begin{equation}
    E = mc^2
\end{equation}
```

This will produce the following equation:

$$
E = mc^2 \tag{1}
$$

If you want to write an equation without a number, you can use the `equation*` environment.

## Multi-line Equations

If you want to write a multi-line equation, you can use the `align` environment.
This will align the equations at the `&` symbol.
Here is an example:

```latex
\begin{align}
    E &= mc^2 \\
    F &= ma
\end{align}
```

This will produce the following equations:

$$
\begin{align}
    E &= mc^2 \tag{2} \\
    F &= ma \tag{3}
\end{align}
$$

You can place the `&` symbol at different points in the equation to align the equations at that point.
And if you do not want numbers you can use the `align*` environment to write multi-line equations without numbers. 

## Matrices

If you want to write a matrix, you can use the `bmatrix` environment.
Here is an example:

```latex
\[
    \begin{bmatrix}
        1 & 2 \\
        3 & 4
    \end{bmatrix}
\]
```

This will produce the following matrix:

$$
\begin{bmatrix}
    1 & 2 \\
    3 & 4
\end{bmatrix}
$$

You can use the `pmatrix`, `vmatrix`, `Vmatrix`, `Bmatrix`, and `smallmatrix` environments to write different types 
of matrices.

## Cases

If you want to write a piecewise function, you can use the `cases` environment.
Here is an example:

```latex
\[
    f(x) = 
    \begin{cases}
        1 & x > 0 \\
        0 & x = 0 \\
        -1 & x < 0
    \end{cases}
\]
```

This will produce the following piecewise function:

$$
f(x) =
\begin{cases}\tag{1}
    1 & x > 0 \\
    0 & x = 0 \\
    -1 & x < 0
\end{cases}
$$

Some time you will want to write a piecewise function with a single equation number.
To do this you can use the `numcases` environment from the `cases` package.
Here is an example:

```latex
\begin{numcases}{f(x)}
    1 & $x > 0$ \\
    0 & $x = 0$ \\
    -1 & $x < 0$
\end{numcases}
```

This will produce the following piecewise function with a single equation number:

$$
\require{amsmath}
\require{cases}
\begin{numcases}{f(x)}
    1 & x > 0 \tag{1} \\
    0 & x = 0 \tag{2} \\
    -1 & x < 0 \tag{3}
\end{numcases}
$$

When you are using cases with complex equations you may find the equation gets too small to read. In this case you can
use the `dcases` environment from the `mathtools` package. This will make the equations larger and easier to read.
Here is an example:

```latex
f(x) = 
\begin{dcases}
    \frac{1}{x} & x \neq 0 \\
    \frac{1}{\frac{1-3}{x}+3.313} & x \neq 0 \\
    0 & x = 0
\end{dcases}
```

This will produce the following piecewise function:

$$
\require{amsmath}
\require{mathtools}
f(x) =
\begin{dcases}
    \frac{1}{x} & x \neq 0 \\
    \frac{1}{\frac{1-3}{x}+3.313} & x \neq 0 \\
    0 & x = 0
\end{dcases}
$$

## Greek and Special Characters

To write Greek letters and special characters in LaTeX, you can use the following syntax:

```latex

\alpha \beta \gamma \delta \epsilon \varepsilon \zeta \eta \theta \vartheta \iota \kappa \lambda \mu \nu \xi \pi 

\Gamma \Delta \Theta \Lambda \Xi \Pi \Sigma \Upsilon \Phi \Psi \Omega

\infty \partial \hbar \imath \jmath \ell \Re \Im \wp \aleph \forall \exists \neg \flat \natural \sharp \backslash 
```

This will produce the following Greek letters and special characters:

$$
\begin{align}
&\alpha \beta \gamma \delta \epsilon \varepsilon \zeta \eta \theta \vartheta \iota \kappa \lambda \mu \nu \xi \pi \\
&\Gamma \Delta \Theta \Lambda \Xi \Pi \Sigma \Upsilon \Phi \Psi \Omega \\
&\infty \partial \hbar \imath \jmath \ell \Re \Im \wp \aleph \forall \exists \neg \flat \natural \sharp \backslash
\end{align}
$$

This is just a small selection of the Greek letters and special characters that you can write in LaTeX. For a full list
of Greek letters and special characters, please refer to the
[LaTeX WikiBook](https://en.wikibooks.org/wiki/LaTeX/Mathematics).