# Custom Commands

Sometimes in LaTeX there is not a package that does exactly what you want, or you want to make a specific action
repeatable. In these cases, you can define your own commands. This is done using the `\newcommand` command or the
`\newenvironment` command. 

When defining new commands or environments you will want to add in `\makeatletter` and `\makeatother` to allow for the
use of `@` and other special characters in the command. This is done as follows:

```latex
\makeatletter
% Define new commands here
\makeatother
```

## New Commands

The syntax for `\newcommand` is:

```latex
\newcommand{\commandname}[num]{definition}
```

where `\commandname` is the name of the command, `num` is the number of arguments the command takes (up to 9), and
`definition` is what the command does. For example, if you wanted to define a command that bolds text, you could use:

```latex
\newcommand{\bold}[1]{\textbf{#1}}
```

This would allow you to use `\bold{some text}` to bold the text "some text". If you wanted to define a command that
takes two arguments, you could use:

```latex
\newcommand{\add}[2]{#1 + #2}
```

This would allow you to use `\add{2}{3}` to get "2 + 3".

These are simple examples, but you can define more complex commands. For example, you could define a command that
creates a new section with a label and a reference:

```latex
\newcommand{\newsection}[2]{\section{#1}\label{#2}\ref{#2}}
```

This would allow you to use `\newsection{Introduction}{sec:intro}` to create a new section titled "Introduction" with
the label "sec:intro" and a reference to it.

A particularly useful command may be extending the roman numeral command to be more inline with your needs. For example:

```latex
\newcommand{\Rom}[1]{\textrm{\MakeUppercase{\romannumeral #1}}}
\newcommand{\rom}[1]{\textrm{\romannumeral #1}}
\newcommand{\Romit}[1]{\textit{\textrm{\MakeUppercase{\romannumeral #1}}}}
\newcommand{\romit}[1]{\textit{\textrm{\romannumeral #1}}}
```

This would allow you to use `\Rom{1}` to get "I", `\rom{1}` to get "i", `\Romit{1}` to get "_I_", and 
`\romit{1}` to get "_i_".

However, you may find it impractical to define a new command for each case here, in this case you can define a command
with optional arguments instead. This is done by using the following syntax:

```latex
\newcommand{\roms}[2][n]{%
	\if S#1 \textrm{\MakeUppercase{\romannumeral #2}}%
	\else \if I#1 \textit{\textrm{\MakeUppercase{\romannumeral #2}}}%
	\else \if i#1 \textit{\textrm{\romannumeral #2}}%
	\else \textrm{\romannumeral #2}%
	\fi \fi \fi
}
```

This would allow you to use `\roms{1}` to get "i", `\roms[I]{1}` to get "_I_", `\roms[i]{1}` to get "_i_", and
`\roms[S]{1}` to get "I".

## New Environments

The syntax for `\newenvironment` is:

```latex
\newenvironment{name}[num]{before}{after}
```

where `name` is the name of the environment, `num` is the number of arguments the environment takes (up to 9), `before`
is what happens before the environment, and `after` is what happens after the environment. For example, if you wanted to
define an environment that bolds text, you could use:

```latex
\newenvironment{boldenv}{\textbf\bgroup}{\egroup}
```

This would allow you to use:

```latex
\begin{boldenv}
some text
\end{boldenv}
```

This gives you large levels of control over your documents and gives you the ability to create tools to make your time
writing LaTeX easier.

## Additional Notes

- When defining new commands or environments, you should be careful not to overwrite existing commands or environments.
- You can use `\renewcommand` to redefine an existing command.
- You can use `\providecommand` to define a command only if it does not already exist.
- You can use `\newcommand*` to define a command that does not allow for paragraph breaks in its arguments.
- You can use `\newenvironment*` to define an environment that does not allow for paragraph breaks in its contents.

You may want to save your custom commands in a separate file like a `.sty` file and include it in your main document,
if this is stored in your `texmf` directory you can use it in any document you write and call it as a package.
