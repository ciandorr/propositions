# propositions LaTeX package

A LaTeX .dtx/docstrip package. Source is `propositions.dtx`; 
`propositions.ins` extracts the .sty; `propositions.pdf` is the manual.

## Rebuild workflow

After editing `propositions.dtx`, always:
1. `pdflatex propositions.ins`  — regenerates `propositions.sty`
2. `pdflatex propositions.dtx`  — rebuilds the documentation PDF
3. Commit `propositions.dtx propositions.sty propositions.pdf` together, then push.

## Repository layout

- `propositions.dtx` — combined source and documentation
- `propositions.ins` — docstrip installer
- `test/`            — test documents (most basic is test-props.tex)

## Style notes

- Implementation uses LaTeX3/expl3 throughout
- Internal names follow `\__props_...` convention
- Item types are stored in prop-list `\l__props_level_defaults_prop`
- The live package lives at `~/Dropbox/texmf/tex/latex/propositions/`
  and is found by TeX automatically (TEXMFHOME tree, no texhash needed)
