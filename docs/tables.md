# Tables

!!! Note
    The recommended package for creating tables is [tabularray](https://ctan.org/pkg/tabularray).

Tables can be created using the `\begin{table}` environment or the `\begin{tblr}` environment from the `tabularray` 
package. The difference between the two is that the former is a floating environment, while the latter is not.

Table with `tabularray` package:

```latex
\documentclass{article}
\usepackage{tabularray}
\begin{document}

\begin{tblr}{hlines,vlines}
  Alpha & Beta & Gamma \\
  Epsilon & Zeta & Eta \\
\end{tblr}

\end{document}
```

Table with `table` environment:

!!! Note
    This still requires the `tabularray` package.

```latex
\documentclass{article}
\usepackage{tabularray}
\begin{document}

\begin{table}
  \centering
    \begin{tblr}{hlines,vlines}
      Alpha & Beta & Gamma \\
      Epsilon & Zeta & Eta \\
    \end{tblr}
    \caption{A table}
\end{table}

\end{document}
```

Using floating tables is recommended when you want LaTeX to decide where to place the table. If you want to place the
table at a specific location, you can use the `[H]` option from the `float` package.

You can additionally caption the table using the `\caption` command and label it using `\zlabel` or `\label` (depending
on whether you are using the `zref` package mentioned in [Cross-Referencing](crossref.md)).

## Auto-generating tables

If you have a CSV file or dat file you can auto-generate tables for your data. This uses the `csvsimple` package in
combination with the `tabularray` package. There are a few ways to do this, but here are the most common ones:

You can load the package `csvsimple` with `\usepackage{csvsimple}` or `\usepackage[l3]{csvsimple}`.

If you have a CSV file with the following data:

|   Name   | Givenname | Matriculation | Gender | Grade |
|:--------:|:---------:|:-------------:|:------:|:-----:|
|  Maier   |   Hans    |     12345     |   m    |   1   |
|  Huber   |   Anna    |     23456     |   f    |  2.3  |
| Weißback |  Werner   |     34567     |   m    |   5   |
|  Bauer   |   Maria   |     19202     |   f    |  3.3  |

## csvreader (Verbose Method)

The most complex read in is the following, This allows for alot of customisation but due to the verbosity it is not
always easy to get right:

```latex
\csvreader[%
    head to column names,
    centered tabularray={%
        width=\textwidth, 
        hline{1,2,Z}={1pt, solid}, 
        colspec={X[l] X[c] X[c] X[c] X[c]},
        },
    table head={Name & Givenname & Matric & Gender & Grade\\}
    ]{data.csv}{}{%
        \Name & \Givenname & \Matriculation & \Gender & \Grade
    }
```

## csvautotabularray (Simple Method)

The following is a simpler version of the above, using the `csvautotabularray` it can be as simple as a single line:

```latex	
\csvautotabularray[table centered]{data.csv}
```

This is still customisable through the following two additions of optional arguments.

```latex
\csvautotabularray[table centered]{data.csv}[%
    width=\textwidth,
    hline{1,2,Z}={1pt,solid},
    colspec={X[l] X[c] X[c] X[c] X[c]},
    row{1}={font=\bfseries}
    ]
```

To add a caption to the table you just need to add caption to the first set of optional arguments:

```latex
\csvautotabularray[table centered]{data.csv}[tall,caption={This is a table},remark{Note}={This a remark on the table},][%
    width=\textwidth,
    hline{1,2,Z}={1pt,solid},
    colspec={X[l] X[c] X[c] X[c] X[c]},
    row{1}={font=\bfseries}
    ]
```

## Column Types

The `tabularray` package has a number of column types that can be used to format the data in the table. Here are some
examples:

- `X[l]`: Left-aligned column
- `X[c]`: Centered column
- `X[r]`: Right-aligned column
- `X[p]`: Paragraph column

The X column type allows for the column to be stretched to fit the width of the table. This is useful when you have a
lot of data in a column, and you want it to wrap and do not want to manually set the width of the column.

## Multi-Row and Multi-Column Cells

The `tabularray` package also has support for multi-row and multi-column cells. Here are some examples:

- `\SetCell[r=2]{c}`: Multi-row cell spanning 2 rows and centered
- `\SetCell[c=2]{c}`: Multi-column cell spanning 2 columns and centered
- `\SetCell[r=2,c=2]{c}`: Multi-row and multi-column cell spanning 2 rows and 2 columns and centered

This would look like:

```latex
\begin{tblr}{hlines,vlines}
  Alpha & Beta & Gamma \\
  \SetCell[r=2]{c} Epsilon & Zeta & Eta \\
  Iota & Kappa & Lambda \\
\end{tblr}
```

## Further Information

For more information on the `tabularray` package, you can refer to the [documentation](https://ctan.org/pkg/tabularray).