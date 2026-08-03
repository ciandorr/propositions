# The `propositions` package

Version 0.9 (2026/08/02)

A LaTeX package for typesetting and cross-referencing named and numbered displayed propositions (examples, theses, premises...).

## Features

- Key-value interface for named and numbered propositions.
- Customizable styles, with many useful built-in styles.  
- Formatted cross-references: `\ref` automatically provides adds specified
  formatting (e.g. parentheses, boldface, or a prefix derived from a 
  parent proposition).
- Extended reference syntax: e.g. `\oref` adds prefixes/suffixes within 
  the formatting provided by `\ref`, and `\nref` strips formatting.
- `\ptag` allows tagging displayed equations with proposition labels;
  `equations` option treats numbered equations like numbered propositions.  
- Integration with `hyperref` and `cleveref` as well as `amsmath`.  

## Usage

```latex
\usepackage{propositions}

\begin{prop}
  \item[Physicalism] Everything is physical. \label{phys}
  \item[Idealism] Everything is mental. \label{ideal}
\end{prop}

\ref{phys} is more plausible than \ref{ideal}.
```

See the package documentation (`propositions.pdf`) for full details.

## Requirements

Requires `calc`, which it loads itself. The following are needed only for
particular features, and are not loaded by the package: `amsmath` for `\ptag`
and the `equations` option, `tcolorbox` for the `framed` style, and `hyperref`
and `cleveref` where those are used.

## Installation

```
latex propositions.ins
```

Move `propositions.sty` to a directory in your TeX search path, conventionally
`tex/latex/propositions/` in your local or personal TeX tree.

## Contributing

The source is available at <https://github.com/ciandorr/propositions>.
Bug reports and contributions are welcome via the issue tracker and pull requests.

## License

Copyright (C) 2026 Cian Dorr

This work may be distributed and/or modified under the conditions of the
LaTeX Project Public License, either version 1.3c of this license or (at
your option) any later version.

The latest version of this license is in
<https://www.latex-project.org/lppl.txt>
and version 1.3c or later is part of all distributions of LaTeX version
2008 or later.

This work has the LPPL maintenance status `maintained`.

The Current Maintainer of this work is Cian Dorr.

This work consists of the files `propositions.dtx` and `propositions.ins`
and the derived files `propositions.sty` and `propositions.pdf`.
