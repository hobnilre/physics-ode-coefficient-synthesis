# Syntes av ODE-koefficienter

[Läs artikeln (PDF)](ode-coefficient-synthesis-sv.pdf) · [Manuskript](ode-coefficient-synthesis-sv.md)

Dimensionskrav ger en tabell över möjliga koefficienter. En regel som minimerar
exponenternas sammanlagda absolutbelopp väljer en trappa i tabellen och ger
rekursionen $A_{k+2}=LC\,A_k$. Ändliga summor bygger upp ODE:er av högre ordning
och deras visarformer.

[ODE-mallen](https://github.com/hobnilre/physics-ode-template) ger
referenskoefficienterna. För terminalvariabler som ström använder
[artikeln om sammankoppling](https://github.com/hobnilre/physics-ode-interconnect-ser-par)
kvoten $Q(\mathrm i\omega)/(\mathrm i\omega)$.
Den valda koefficienten $LRC$ för tredje ordningen ingår i
[exemplen på arbete med bevarat tecken](https://github.com/hobnilre/physics-ode-energy).
