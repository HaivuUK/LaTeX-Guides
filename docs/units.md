# Units in LaTeX

!!! Note
    **TLDR:** It is recommended to use the `siunitx` package for typesetting units in LaTeX. The `units` package is simpler
    and easier to use, but it is also less powerful and flexible.

There are a few ways to typeset units in LaTeX. The two most common ways are to use the `siunitx` package or to use 
the `units` package. The `siunitx` package is more powerful and flexible, but the `units` package is simpler and 
easier to use. This document will cover both methods.

## [siunitx](https://ctan.org/pkg/siunitx)

The `siunitx` provides a wide range of options for formatting units, including the ability to control the spacing 
between the number and the unit, the ability to automatically convert units, and the ability to define custom units.

### Basic Usage

To use the `siunitx` package, you must first include it in your document preamble:

```latex
\usepackage{siunitx}
```

!!! Note
    Since version 3 it is no longer recommended to use `\si` or `\SI` anymore as they are deprecated. Instead, 
    use `\qty`, `\unit`, etc.

Numbers can be typeset with `\num`:

```latex
\num{3.14159e-21}
```

This will produce the output $3.14159 \times 10^{-21}$.

Units can be typeset with `\unit`:

```latex
\unit{kg}
```

Quantities can be typeset with `\qty`:

```latex
\qty{3.14159}{kg}
```

And angles can be typeset with `\ang`:

```latex
\ang{90}
```

### Writing units

The `siunitx` package provides a number of options for calling units. For example you can use full names or 
abbreviations:

```latex
\unit{kg.m.s^{-1}}
```

or

```latex
\unit{\kilogram\meter\per\second}
```

These will both produce the output $\text{kg m s}^{-1}$.

If you use the option `per-mode=symbol` you will instead get the output $\text{kg m/s}$.


### Custom Units

The `siunitx` package also allows you to define custom units using the `\DeclareSIUnit` command:

```latex
\DeclareSIUnit{\lightyear}{ly}
```

You can then use this custom unit in the same way as the built-in units:

```latex
\qty{1}{\lightyear}
```
    
This will produce the output $1 \text{ ly}$.


## [units](https://ctan.org/pkg/units)

The `units` package is simpler and easier to use than the `siunitx` package, but it is also less powerful and flexible.

### Basic Usage

To use the `units` package, you must first include it in your document preamble:

```latex
\usepackage{units}
```

Numbers can be typeset with `\unit`:

```latex
\unit[3.14159e-21]{kg}
```

This will produce the output $3.14159\text{e}^{-21} \text{ kg}$.

Fractional units can be typeset with:

```latex
\unitfrac[3.14159]{kg}{m}
```

This will produce the output $3.14159 \text{ kg/m}$.

