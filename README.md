# The `propositions` package

A LaTeX package for labelling and cross-referencing displayed propositions,
theses, premises, etc.

## Features

- Key-value interface for named, numbered, and custom-typed items
- Formatted cross-references: `\ref` automatically reproduces the item's
  display format (parentheses, bold, small caps, etc.)
- `\oref` for adding prefixes/suffixes to references; `\nref` for
  stripping formatting
- `\ptag` for tagging displayed equations with proposition labels
- Nested proposition lists with automatic sub-item naming
- Integration with `hyperref`, `cleveref`, and `amsmath`

## Usage

```latex
\usepackage{propositions}

\begin{prop}
  \pitem[Physicalism] Everything is physical. \label{phys}
  \pitem[Idealism] Everything is mental. \label{ideal}
\end{prop}

\ref{phys} is more plausible than \ref{ideal}.
```

See the package documentation (`propositions.pdf`) for full details.

## Installation

```
latex propositions.ins
```

Move `propositions.sty` to a directory in your TeX search path.

## License

Copyright (C) 2026 Cian Dorr

This work may be distributed and/or modified under the conditions of the
LaTeX Project Public License, either version 1.3c of this license or (at
your option) any later version.

The latest version of this license is in
<https://www.latex-project.org/lppl.txt>

This work consists of the files `propositions.dtx` and `propositions.ins`
and the derived file `propositions.sty`.
