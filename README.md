# ODE Coefficient Synthesis

The coefficient lattice and its staircase

## Coefficient construction

Two dimensional constraints generate the complete Laurent-monomial family
of ODE coefficients from three reference quantities. The article derives
its coefficient table for $(a,b,c)=(L,R,1/C)$, proves the staircase selection,
and gives the resulting recurrence and finite weighted synthesis. Its phasor
form derives the frequency factors, staircase sum and derivative-variable
multiplier.

The article is confined to the mathematics and is at most six pages.

## Four related articles

| Article | Main role |
| --- | --- |
| [Template](https://github.com/hobnilre/physics-ode-template) | Common equation, domain dictionary, duality and harmonic convention. |
| [Coefficient synthesis](ode-coefficient-synthesis.pdf) | Coefficient family, LRC table, stairs and phasor factors. |
| [Interconnection](https://github.com/hobnilre/physics-ode-interconnect-ser-par) | Series/parallel constraints, initial coordinates, elimination and phasor solutions. |
| [Energy](https://github.com/hobnilre/physics-ode-energy) | Signed power and work of the added term, with fixed-motion coefficient scaling. |

Each article states its local assumptions. Shared derivations are linked
where they are used. The energy article uses the coefficient-synthesis
article for $A_{-1,3}=LRC$.

## Article and build

[Read the article (PDF)](ode-coefficient-synthesis.pdf) · [Manuscript source](ode-coefficient-synthesis.md)

Install GNU Make, GNU Coreutils, Pandoc, XeLaTeX and the TeX Gyre fonts, including the LaTeX
packages used by `preamble.tex` and `preamble-local.tex` and the TikZ/PGFPlots standalone figures.
Run `make pdf` from this repository. It regenerates changed figures and builds
the article without any sibling repository or private working files.

The title date is the first version's creation date, pinned in `ARTICLE_DATE`
in the Makefile and retained in the manuscript's `date`. Keep both unchanged
when revising the article. The first page also gives the PDF creation time in UTC, followed by the
[GitHub repository](https://github.com/hobnilre/physics-ode-coefficient-synthesis). An up-to-date PDF keeps its timestamp;
`make -B pdf` forces a rebuild. Intermediates go to ignored `build/` by default;
`BUILD_DIR=/absolute/path` selects another location. `make clean` removes that
build directory and keeps the published PDF and figure assets.

Shared typography is installed locally in `article-style.yaml`, `preamble.tex`
and `figures/figure-style.tex`. Article-specific definitions are in
`preamble-local.tex`. These files are complete build inputs; no tools checkout
is required.
