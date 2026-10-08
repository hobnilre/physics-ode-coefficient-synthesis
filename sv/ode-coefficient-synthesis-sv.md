---
title: "Syntes av ODE-koefficienter"
subtitle: "Koefficienttabellen och dess trappa"
author: "Hob Nilre & Bo C. Herlin"
date: "2026-10-08"
lang: sv
abstract: |
  Dimensionskrav ger en tabell över möjliga ODE-koefficienter.
  Minimering av heltalsexponenternas sammanlagda absolutbelopp väljer
  en trappa med rekursionen $A_{k+2}=LC\,A_k$. Ändliga summor bygger upp
  ekvationer av högre ordning, och $D=\mathrm i\omega$ ger deras visarform.
keywords:
  - ordinära differentialekvationer
  - koefficientsyntes
  - dimensionsanalys
  - Laurentmonom
  - visare
---

\begingroup\scriptsize
\noindent PDF created: \pdfbuildtimestamp\par
\noindent Latest on GitHub: \url{https://github.com/hobnilre/physics-ode-coefficient-synthesis}\par
\endgroup

Denna svenska version följer [den engelska originalartikeln][original].

# Härledning av koefficientfamiljen

Utgå från $aD^2y+bDy+cy=f$ i [ODE-mallen][template], där
$D=d/dt$ och $a,b,c>0$ är konstanter. Med de oberoende dimensionerna
$U=[c]$ och tid $T$ kräver lika dimensioner hos termerna att
$$
[a]=UT^2,\qquad [b]=UT,\qquad [c]=U.
$$
En koefficient framför $D^ky$ måste ha dimensionen $UT^k$. För ett monom
$a^p b^q c^r$ innebär det
$$
p+q+r=1,\qquad 2p+q=k.
$$
Lösningen ger följande familj, så när som på en dimensionslös faktor:
\begin{equation}
\boxed{A_{r,k}(a,b,c)=a^{k-1+r}b^{2-k-2r}c^r.}
\label{eq:family}
\end{equation}
Vi väljer heltal $r,k$: exponenterna får vara positiva, noll eller negativa.
Dimensionskraven tillåter även reella $r$; heltalsvillkoret avgränsar den
klass av Laurentmonom som används här.

Med $(a,b,c)=(L,R,1/C)$ fås
\begin{equation}
\boxed{A_{r,k}=L^{k-1+r}R^{2-k-2r}C^{-r}.}
\label{eq:lrc}
\end{equation}
Till exempel ger $k=3$ och $r=0,-1,-2$ koefficienterna $L^2/R$, $LRC$ och $R^3C^2$.
Dimensionskraven lämnar en exponent fri. För att välja en bestämd
koefficient behövs därför ytterligare en regel.

\newpage

# Koefficienttabellen

Tabell \ref{tab:lattice} visar \eqref{eq:lrc}; rutorna markerar den trappa
som väljs i avsnitt 3. ODE:er använder $k\geq0$. Negativa kolumner utvidgar
dimensionsregeln till upprepade integraler, med tidsfaktorer $T^{-k}$.

\begin{table}[htbp]
\centering
\small
\everymath{\displaystyle}
\begin{tabular*}{\textwidth}{@{\extracolsep{\fill}}rccccc@{}}
\toprule
$r\backslash k$ & $-4$ & $-3$ & $-2$ & $-1$ & $0$ \\
\midrule
$3$ & $\stair{\frac{1}{L^{2}C^{3}}}$ & $\frac{1}{LRC^{3}}$ & $\frac{1}{R^{2}C^{3}}$ & $\frac{L}{R^{3}C^{3}}$ & $\frac{L^{2}}{R^{4}C^{3}}$ \\[6pt]
$2$ & $\frac{R^{2}}{L^{3}C^{2}}$ & $\stair{\frac{R}{L^{2}C^{2}}}$ & $\stair{\frac{1}{LC^{2}}}$ & $\frac{1}{RC^{2}}$ & $\frac{L}{R^{2}C^{2}}$ \\[6pt]
$1$ & $\frac{R^{4}}{L^{4}C}$ & $\frac{R^{3}}{L^{3}C}$ & $\frac{R^{2}}{L^{2}C}$ & $\stair{\frac{R}{LC}}$ & $\stair{\frac{1}{C}}$ \\[6pt]
$0$ & $\frac{R^{6}}{L^{5}}$ & $\frac{R^{5}}{L^{4}}$ & $\frac{R^{4}}{L^{3}}$ & $\frac{R^{3}}{L^{2}}$ & $\frac{R^{2}}{L}$ \\[6pt]
$-1$ & $\frac{R^{8}C}{L^{6}}$ & $\frac{R^{7}C}{L^{5}}$ & $\frac{R^{6}C}{L^{4}}$ & $\frac{R^{5}C}{L^{3}}$ & $\frac{R^{4}C}{L^{2}}$ \\[6pt]
$-2$ & $\frac{R^{10}C^{2}}{L^{7}}$ & $\frac{R^{9}C^{2}}{L^{6}}$ & $\frac{R^{8}C^{2}}{L^{5}}$ & $\frac{R^{7}C^{2}}{L^{4}}$ & $\frac{R^{6}C^{2}}{L^{3}}$ \\[6pt]
$-3$ & $\frac{R^{12}C^{3}}{L^{8}}$ & $\frac{R^{11}C^{3}}{L^{7}}$ & $\frac{R^{10}C^{3}}{L^{6}}$ & $\frac{R^{9}C^{3}}{L^{5}}$ & $\frac{R^{8}C^{3}}{L^{4}}$ \\[6pt]
\bottomrule
\end{tabular*}
\par\vspace{12pt}
\begin{tabular*}{\textwidth}{@{\extracolsep{\fill}}rcccccc@{}}
\toprule
$r\backslash k$ & $1$ & $2$ & $3$ & $4$ & $5$ & $6$ \\
\midrule
$3$ & $\frac{L^{3}}{R^{5}C^{3}}$ & $\frac{L^{4}}{R^{6}C^{3}}$ & $\frac{L^{5}}{R^{7}C^{3}}$ & $\frac{L^{6}}{R^{8}C^{3}}$ & $\frac{L^{7}}{R^{9}C^{3}}$ & $\frac{L^{8}}{R^{10}C^{3}}$ \\[6pt]
$2$ & $\frac{L^{2}}{R^{3}C^{2}}$ & $\frac{L^{3}}{R^{4}C^{2}}$ & $\frac{L^{4}}{R^{5}C^{2}}$ & $\frac{L^{5}}{R^{6}C^{2}}$ & $\frac{L^{6}}{R^{7}C^{2}}$ & $\frac{L^{7}}{R^{8}C^{2}}$ \\[6pt]
$1$ & $\frac{L}{RC}$ & $\frac{L^{2}}{R^{2}C}$ & $\frac{L^{3}}{R^{3}C}$ & $\frac{L^{4}}{R^{4}C}$ & $\frac{L^{5}}{R^{5}C}$ & $\frac{L^{6}}{R^{6}C}$ \\[6pt]
$0$ & $\stair{R}$ & $\stair{L}$ & $\frac{L^{2}}{R}$ & $\frac{L^{3}}{R^{2}}$ & $\frac{L^{4}}{R^{3}}$ & $\frac{L^{5}}{R^{4}}$ \\[6pt]
$-1$ & $\frac{R^{3}C}{L}$ & $R^{2}C$ & $\stair{LRC}$ & $\stair{L^{2}C}$ & $\frac{L^{3}C}{R}$ & $\frac{L^{4}C}{R^{2}}$ \\[6pt]
$-2$ & $\frac{R^{5}C^{2}}{L^{2}}$ & $\frac{R^{4}C^{2}}{L}$ & $R^{3}C^{2}$ & $LR^{2}C^{2}$ & $\stair{L^{2}RC^{2}}$ & $\stair{L^{3}C^{2}}$ \\[6pt]
$-3$ & $\frac{R^{7}C^{3}}{L^{3}}$ & $\frac{R^{6}C^{3}}{L^{2}}$ & $\frac{R^{5}C^{3}}{L}$ & $R^{4}C^{3}$ & $LR^{3}C^{3}$ & $L^{2}R^{2}C^{3}$ \\[6pt]
\bottomrule
\end{tabular*}
\caption{Koefficienttabellen för $(a,b,c)=(L,R,1/C)$, med $r=3,\ldots,-3$ och $k=-4,\ldots,6$. Blå rutor markerar $r_k=\lfloor(2-k)/2\rfloor$.}
\label{tab:lattice}
\end{table}
\FloatBarrier

Två kvoter genererar tabellen:
\begin{equation}
A_{r,k+1}=\frac LR A_{r,k},\qquad
A_{r-1,k}=\frac{R^2C}{L}A_{r,k}.
\label{eq:steps}
\end{equation}
Ett steg åt höger tillför en tidsfaktor; ett steg nedåt är dimensionslöst.

\newpage

# Val av trappan

Minimera summan av exponenternas absolutbelopp i den valda basen $(L,R,C)$:
$$
F_k(r)=\lvert k-1+r\rvert+\lvert2-k-2r\rvert+\lvert r\rvert.
$$
Vid lika minimivärden väljs en icke-negativ exponent för $R$. Då fås
\begin{equation}
\boxed{r_k=\left\lfloor\frac{2-k}{2}\right\rfloor
=1-\left\lceil\frac{k}{2}\right\rceil.}
\label{eq:stairs}
\end{equation}
Triangelolikheten ger nämligen
$$
F_k(r)\geq\lvert k-1\rvert+\lvert2-k-2r\rvert.
$$
Den sista termen är minst $0$ för jämna $k$ och $1$ för udda $k$.
Det valda $r_k$ uppnår gränsen och ger just dessa icke-negativa
exponenter för $R$. Både minimivillkoret och regeln vid lika minima är
därmed uppfyllda.

![Den valda trappan $r=r_k$. Varje kolumnpar ligger på samma rad; nästa par ligger en rad lägre.](figures/staircase.pdf){#fig:stairs width=95%}

\FloatBarrier

Sätt $A_k=A_{r_k,k}$. Insättning ger
\begin{equation}
\boxed{A_{2n}=L^nC^{n-1},\qquad A_{2n+1}=R(LC)^n,}
\quad n\in\mathbb Z,
\label{eq:parity}
\end{equation}
och därmed
\begin{equation}
\boxed{A_{k+2}=LC\,A_k,\qquad A_0=\frac1C,\quad A_1=R.}
\label{eq:recurrence}
\end{equation}
Koefficienterna av jämn respektive udda ordning bildar två geometriska
följder: inom vardera följden används samma multiplikationsfaktor i varje
steg. I ordning börjar koefficienterna $1/C,R,L,LRC,L^2C,L^2RC^2,L^3C^2$.

# Att bygga upp en ODE

För heltal $N\geq1$ definieras
\begin{equation}
P_N(D)y=f,\qquad P_N(D)=\sum_{k=0}^N A_kD^k.
\label{eq:ode}
\end{equation}
Med de ursprungliga symbolerna blir detta
$$
A_{2n}=a^nc^{1-n},\qquad A_{2n+1}=b(a/c)^n,\qquad
A_{k+2}=\frac ac A_k.
$$
Polynomet av tredje graden faktoriseras som
\begin{equation}
\frac{ab}{c}D^3+aD^2+bD+c
=(bD+c)\left(1+\frac acD^2\right).
\label{eq:cubic}
\end{equation}
Dess koefficient $ab/c=LRC$ används i beräkningen av arbete med bevarat
tecken i [*Energy Ledgers for Forced Harmonic ODEs*][energy], avsnitt 2--3.
Genom att para ihop intilliggande ordningar fås
\begin{equation}
P_{2m+1}(D)=(c+bD)\sum_{j=0}^m\left(\frac acD^2\right)^j,
\qquad m\geq0.
\label{eq:odd}
\end{equation}
För $m\geq1$ fås $P_{2m}$ genom att lägga $a^mc^{1-m}D^{2m}$ till
$P_{2m-1}$. Dessa ändliga identiteter kräver inget antagande om konvergens.

## Andra val

Låt $S=b^2/a$, $\tau=a/b$ och $\rho=b^2/(ac)$, med dimensionerna
$U,T,1$ i samma ordning. Då gäller
\begin{equation}
A_{r,k}=S\tau^k\rho^{-r},\qquad
B_k=\sum_{r\in\mathcal R_k}w_{r,k}A_{r,k}
=S\tau^k\sum_{r\in\mathcal R_k}w_{r,k}\rho^{-r},
\label{eq:synthesis}
\end{equation}
där varje $\mathcal R_k\subset\mathbb Z$ är ändlig och $w_{r,k}$ är
reella dimensionslösa konstanter. Den resulterande ekvationen $Q(D)y=f$,
$Q(s)=\sum_{k=0}^N B_ks^k$, har ordningen $N$ om $B_N\ne0$.
Trappan väljer $\mathcal R_k=\{r_k\}$ och $w_{r_k,k}=1$;
viktade summor bevarar andra dimensionsmässigt tillåtna val.

# Visarform

Använd $y(t)=\operatorname{Re}(\widehat y e^{\mathrm i\omega t})$,
$\mathrm i^2=-1$, $\omega>0$. Här används komplexa amplituder, även
kallade visare. Insättningen $D=\mathrm i\omega$ ger
\begin{equation}
\boxed{Q(\mathrm i\omega)\widehat y=\widehat f,\qquad
Q(\mathrm i\omega)=\sum_{k=0}^N B_k(\mathrm i\omega)^k.}
\label{eq:phasor-equation}
\end{equation}
Division kräver $Q(\mathrm i\omega)\ne0$; en visare skild från noll
för den homogena ekvationen kräver $Q(\mathrm i\omega)=0$.
Detta beskriver harmoniska komponenter. Begynnelsedata för den
fullständiga lösningen anges separat.

## Frekvensfaktorer

Multiplicera tabellens kolumn $k$ med $(\mathrm i\omega)^k$:
\begin{equation}
\Phi_{r,k}=A_{r,k}(\mathrm i\omega)^k
=S\rho^{-r}(\mathrm i\omega\tau)^k.
\label{eq:phasor-lattice}
\end{equation}
Faktorerna $\mathrm i^k$ upprepar följden $1,\mathrm i,-1,-\mathrm i$.
För negativa $k$ ger detta den harmoniska primitiva funktionen;
integrationskonstanterna anges separat. På trappan gäller
\begin{equation}
\Phi_{2n}=\frac1C(-\omega^2LC)^n,\qquad
\Phi_{2n+1}=\mathrm i\omega R(-\omega^2LC)^n,
\quad n\in\mathbb Z.
\label{eq:phasor-stairs}
\end{equation}
Alltså är $\Phi_{k+2}=-\omega^2LC\,\Phi_k$: två ordningar framåt
byter bidraget tecken och dess absolutbelopp multipliceras med
$\omega^2LC$. Genom att para ihop termer fås
\begin{equation}
\boxed{P_{2m+1}(\mathrm i\omega)
=\left(\frac1C+\mathrm i\omega R\right)
\sum_{n=0}^m(-\omega^2LC)^n,\qquad m\geq0.}
\label{eq:phasor-sum}
\end{equation}
Speciellt gäller $P_3(\mathrm i\omega)=(1/C+\mathrm i\omega R)(1-\omega^2LC)$.
Den ändliga summan gäller för alla $\omega>0$.

## Derivatan som terminalvariabel

För $u=Dy$ gäller $\widehat u=\mathrm i\omega\widehat y$, vilket ger
\begin{equation}
H(\omega)=\frac{Q(\mathrm i\omega)}{\mathrm i\omega}
=\sum_{k=0}^N B_k(\mathrm i\omega)^{k-1},\qquad
\widehat f=H(\omega)\widehat u.
\label{eq:phasor-derivative}
\end{equation}
Exponenterna är $k$ för $y$ och $k-1$ för $Dy$.
[*Interconnecting Series and Parallel ODEs*][interconnect], avsnitt 3,
kombinerar dessa terminalkvoter med villkor för gemensamma variabler
och för summor.

# Referenser {-}

1. H. Nilre och B. C. Herlin (2026). [The ODE Template and Its Domain Equivalents][template].
2. H. Nilre och B. C. Herlin (2026). [Interconnecting Series and Parallel ODEs][interconnect].
3. H. Nilre och B. C. Herlin (2026). [Energy Ledgers for Forced Harmonic ODEs][energy].

[template]: https://github.com/hobnilre/physics-ode-template
[interconnect]: https://github.com/hobnilre/physics-ode-interconnect-ser-par
[energy]: https://github.com/hobnilre/physics-ode-energy

[original]: https://github.com/hobnilre/physics-ode-coefficient-synthesis/blob/main/ode-coefficient-synthesis.md
