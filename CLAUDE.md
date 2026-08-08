# propositions LaTeX package

A LaTeX .dtx/docstrip package. Source is `propositions.dtx`; 
`propositions.ins` extracts the .sty; `propositions.pdf` is the manual.

## Rebuild workflow

After editing `propositions.dtx`, always:
1. Check that no documentation line has lost its leading `%`:
   ```
   awk '/^%<\/driver>/{f=1;next} /StopEventually/{f=0} f && !/^%/ && NF \
       {print "line "NR": "$0}' propositions.dtx
   ```
   Silence means all is well. Anything printed is a documentation line that
   docstrip will copy into `propositions.sty` as code, and that also breaks
   the manual — hundreds of errors from one missing character, and the cause
   is invisible in the output. Run this *before* the builds below, since it
   explains failures they would otherwise report very confusingly.
2. `pdflatex propositions.ins`  — regenerates `propositions.sty`
3. `pdflatex propositions.dtx`  — rebuilds the documentation PDF
4. Commit `propositions.dtx propositions.sty propositions.pdf` together, then push.

## Cutting a release

1. Bump the version and date in `\ProvidesExplPackage` at the top of the
   implementation, and in `\fileversion`/`\filedate` if they are separate.
2. Drop `(unreleased)` from that version's entry in the Release notes section.
3. Rebuild (workflow above) and run the test suite.
4. `propositions.zip` for CTAN holds exactly four files: `propositions.dtx`,
   `propositions.ins`, `propositions.pdf`, `README.md`, inside a
   `propositions/` directory.

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
