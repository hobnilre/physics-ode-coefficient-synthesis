---
title: "ODE Coefficient Synthesis"
subtitle: "The coefficient lattice and its staircase"
author: "Hob Nilre & Bo C. Herlin"
date: "2026-10-08"
abstract: |
  Dimensional constraints give a table of admissible ODE coefficients.
  Minimizing absolute integer exponents selects a staircase with
  recurrence $A_{k+2}=LC\,A_k$. Finite sums assemble higher-order
  equations, and $D=\mathrm i\omega$ gives their phasor form.
keywords:
  - ordinary differential equations
  - coefficient synthesis
  - dimensional analysis
  - Laurent monomials
  - phasors
---

\begingroup\scriptsize
\noindent PDF created: \pdfbuildtimestamp\par
\noindent Latest on GitHub: \url{https://github.com/hobnilre/physics-ode-coefficient-synthesis}\par
\endgroup

# Deriving the coefficient family

Start with $aD^2y+bDy+cy=f$ from [the ODE template][template], where
$D=d/dt$ and $a,b,c>0$ are constants. With independent dimensions
$U=[c]$ and time $T$, equal term dimensions require
$$
[a]=UT^2,\qquad [b]=UT,\qquad [c]=U.
$$
A coefficient of $D^ky$ must have dimension $UT^k$. For a monomial
$a^p b^q c^r$, this means
$$
p+q+r=1,\qquad 2p+q=k.
$$
Solving gives the family, up to a dimensionless multiplier,
\begin{equation}
\boxed{A_{r,k}(a,b,c)=a^{k-1+r}b^{2-k-2r}c^r.}
\label{eq:family}
\end{equation}
We choose integer $r,k$: the powers may be positive, zero or negative.
Dimensions alone also allow real $r$; the integer restriction defines the
Laurent-monomial class used here.

With $(a,b,c)=(L,R,1/C)$,
\begin{equation}
\boxed{A_{r,k}=L^{k-1+r}R^{2-k-2r}C^{-r}.}
\label{eq:lrc}
\end{equation}
For example, $k=3$ and $r=0,-1,-2$ give $L^2/R$, $LRC$ and $R^3C^2$.
Dimensions leave one exponent free; selecting a coefficient needs another rule.

\newpage

# The coefficient table

Table \ref{tab:lattice} lists \eqref{eq:lrc}; boxes mark the staircase
selected in Section 3. ODEs use $k\geq0$. Negative columns extend the
dimension rule to repeated integrals, with time factors $T^{-k}$.

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
\caption{The coefficient table for $(a,b,c)=(L,R,1/C)$, with $r=3,\ldots,-3$ and $k=-4,\ldots,6$. Blue boxes select $r_k=\lfloor(2-k)/2\rfloor$.}
\label{tab:lattice}
\end{table}
\FloatBarrier

Two ratios generate the table:
\begin{equation}
A_{r,k+1}=\frac LR A_{r,k},\qquad
A_{r-1,k}=\frac{R^2C}{L}A_{r,k}.
\label{eq:steps}
\end{equation}
A step right contributes a time factor; a step down is dimensionless.

\newpage

# Selecting the staircase

Minimize the sum of absolute exponents in the declared basis $(L,R,C)$:
$$
F_k(r)=\lvert k-1+r\rvert+\lvert2-k-2r\rvert+\lvert r\rvert.
$$
Break ties by choosing a nonnegative exponent of $R$. Then
\begin{equation}
\boxed{r_k=\left\lfloor\frac{2-k}{2}\right\rfloor
=1-\left\lceil\frac{k}{2}\right\rceil.}
\label{eq:stairs}
\end{equation}
Indeed, the triangle inequality gives
$$
F_k(r)\geq\lvert k-1\rvert+\lvert2-k-2r\rvert.
$$
The last term is at least $0$ for even $k$ and $1$ for odd $k$.
The chosen $r_k$ attains this bound and gives those same nonnegative
exponents of $R$, satisfying the minimum and tie rule.

![The selected staircase $r=r_k$. Each pair of columns shares one row; the next pair is one row lower.](figures/staircase.pdf){#fig:stairs width=95%}

\FloatBarrier

Set $A_k=A_{r_k,k}$. Substitution gives
\begin{equation}
\boxed{A_{2n}=L^nC^{n-1},\qquad A_{2n+1}=R(LC)^n,}
\quad n\in\mathbb Z,
\label{eq:parity}
\end{equation}
and therefore
\begin{equation}
\boxed{A_{k+2}=LC\,A_k,\qquad A_0=\frac1C,\quad A_1=R.}
\label{eq:recurrence}
\end{equation}
The even and odd coefficients are two geometric sequences. Together they
begin $1/C,R,L,LRC,L^2C,L^2RC^2,L^3C^2$.

# Assembling an ODE

For integer $N\geq1$, define
\begin{equation}
P_N(D)y=f,\qquad P_N(D)=\sum_{k=0}^N A_kD^k.
\label{eq:ode}
\end{equation}
In the original symbols,
$$
A_{2n}=a^nc^{1-n},\qquad A_{2n+1}=b(a/c)^n,\qquad
A_{k+2}=\frac ac A_k.
$$
The cubic factors as
\begin{equation}
\frac{ab}{c}D^3+aD^2+bD+c
=(bD+c)\left(1+\frac acD^2\right).
\label{eq:cubic}
\end{equation}
Its coefficient $ab/c=LRC$ is used in the signed-work calculation of
[*Energy Ledgers for Forced Harmonic ODEs*][energy], Sections 2--3.
Pairing adjacent orders gives
\begin{equation}
P_{2m+1}(D)=(c+bD)\sum_{j=0}^m\left(\frac acD^2\right)^j,
\qquad m\geq0.
\label{eq:odd}
\end{equation}
For $m\geq1$, obtain $P_{2m}$ by adding $a^mc^{1-m}D^{2m}$ to
$P_{2m-1}$. These finite identities require no convergence assumption.

## Other selections

Let $S=b^2/a$, $\tau=a/b$ and $\rho=b^2/(ac)$, with dimensions
$U,T,1$, respectively. Then
\begin{equation}
A_{r,k}=S\tau^k\rho^{-r},\qquad
B_k=\sum_{r\in\mathcal R_k}w_{r,k}A_{r,k}
=S\tau^k\sum_{r\in\mathcal R_k}w_{r,k}\rho^{-r},
\label{eq:synthesis}
\end{equation}
where each $\mathcal R_k\subset\mathbb Z$ is finite and $w_{r,k}$ are
real dimensionless constants. The resulting $Q(D)y=f$,
$Q(s)=\sum_{k=0}^N B_ks^k$, has order $N$ if $B_N\ne0$.
The staircase takes $\mathcal R_k=\{r_k\}$ and $w_{r_k,k}=1$;
weighted sums retain other dimensionally admissible choices.

# Phasor form

Use $y(t)=\operatorname{Re}(\widehat y e^{\mathrm i\omega t})$,
$\mathrm i^2=-1$, $\omega>0$. Substituting $D=\mathrm i\omega$ gives
\begin{equation}
\boxed{Q(\mathrm i\omega)\widehat y=\widehat f,\qquad
Q(\mathrm i\omega)=\sum_{k=0}^N B_k(\mathrm i\omega)^k.}
\label{eq:phasor-equation}
\end{equation}
Division requires $Q(\mathrm i\omega)\ne0$; a nonzero homogeneous phasor
requires $Q(\mathrm i\omega)=0$. These are harmonic components, with
initial data for the full solution specified separately.

## Frequency factors

Multiply column $k$ of the table by $(\mathrm i\omega)^k$:
\begin{equation}
\Phi_{r,k}=A_{r,k}(\mathrm i\omega)^k
=S\rho^{-r}(\mathrm i\omega\tau)^k.
\label{eq:phasor-lattice}
\end{equation}
The factors $\mathrm i^k$ cycle through $1,\mathrm i,-1,-\mathrm i$.
For negative $k$, this gives the harmonic antiderivative; integration
constants are separate. On the staircase,
\begin{equation}
\Phi_{2n}=\frac1C(-\omega^2LC)^n,\qquad
\Phi_{2n+1}=\mathrm i\omega R(-\omega^2LC)^n,
\quad n\in\mathbb Z.
\label{eq:phasor-stairs}
\end{equation}
Thus $\Phi_{k+2}=-\omega^2LC\,\Phi_k$: every two orders reverse the sign
and multiply the magnitude by $\omega^2LC$. Pairing terms gives
\begin{equation}
\boxed{P_{2m+1}(\mathrm i\omega)
=\left(\frac1C+\mathrm i\omega R\right)
\sum_{n=0}^m(-\omega^2LC)^n,\qquad m\geq0.}
\label{eq:phasor-sum}
\end{equation}
In particular, $P_3(\mathrm i\omega)=(1/C+\mathrm i\omega R)(1-\omega^2LC)$.
The finite sum is valid at every $\omega>0$.

## Using the derivative as terminal variable

For $u=Dy$, $\widehat u=\mathrm i\omega\widehat y$, so
\begin{equation}
H(\omega)=\frac{Q(\mathrm i\omega)}{\mathrm i\omega}
=\sum_{k=0}^N B_k(\mathrm i\omega)^{k-1},\qquad
\widehat f=H(\omega)\widehat u.
\label{eq:phasor-derivative}
\end{equation}
The exponent is $k$ for $y$ and $k-1$ for $Dy$.
[*Interconnecting Series and Parallel ODEs*][interconnect], Section 3,
combines these terminal ratios through common-variable and sum constraints.

# References {-}

1. H. Nilre and B. C. Herlin (2026). [The ODE Template and Its Domain Equivalents][template].
2. H. Nilre and B. C. Herlin (2026). [Interconnecting Series and Parallel ODEs][interconnect].
3. H. Nilre and B. C. Herlin (2026). [Energy Ledgers for Forced Harmonic ODEs][energy].

[template]: https://github.com/hobnilre/physics-ode-template
[interconnect]: https://github.com/hobnilre/physics-ode-interconnect-ser-par
[energy]: https://github.com/hobnilre/physics-ode-energy
