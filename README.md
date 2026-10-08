# ODE Coefficient Synthesis

[Read the article (PDF)](ode-coefficient-synthesis.pdf) · [Manuscript](ode-coefficient-synthesis.md)

Dimensional constraints generate a coefficient table. A minimum-exponent
rule selects its staircase, giving the recurrence $A_{k+2}=LC\,A_k$.
Finite sums assemble higher-order ODEs and their phasor forms.

The [ODE template](https://github.com/hobnilre/physics-ode-template) supplies
the reference coefficients. For terminal variables such as current,
[interconnection](https://github.com/hobnilre/physics-ode-interconnect-ser-par)
uses the ratio $Q(\mathrm i\omega)/(\mathrm i\omega)$.
The selected cubic coefficient $LRC$ enters the
[signed-work examples](https://github.com/hobnilre/physics-ode-energy).

## Build

Install GNU Make, GNU Coreutils, Pandoc, XeLaTeX, the TeX Gyre fonts and the
LaTeX packages used by the included preambles and figures. Run `make pdf`;
all build inputs are in this repository.

The title date stays fixed; the PDF creation timestamp advances on rebuild.
Use `make -B pdf` to force a rebuild. Intermediates go to ignored `build/`,
or to the path set by `BUILD_DIR`. `make clean` removes that directory and
keeps the article PDF and figure assets.
