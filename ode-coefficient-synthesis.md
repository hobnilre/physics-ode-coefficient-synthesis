---
title: "ODE Coefficient Synthesis"
subtitle: "The coefficient lattice and its staircase"
author: "Hob Nilre & Bo C. Herlin"
date: "2026-10-08"
abstract: |
  Dimensional constraints generate the Laurent-monomial table $A_{r,k}$
  for $(a,b,c)=(L,R,1/C)$. Minimizing the sum of absolute exponents
  selects its staircase and gives coefficients at every derivative order.
  Substituting $D=\mathrm i\omega$ yields the corresponding phasor
  factors and finite sums.
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

Use the template $aD^2y+bDy+cy=f$ from
[*The ODE Template and Its Domain Equivalents*][template], with
$D=d/dt$ and constant $a,b,c>0$. Let $T$ be the time dimension and
$U=[c]$, taken as independent dimensions.
Equality of term dimensions gives
$$
[a]=UT^2,\qquad [b]=UT,\qquad [c]=U.
$$
A coefficient multiplying $D^ky$ must therefore have dimension $UT^k$.
Seek it as a monomial $a^p b^q c^r$. Its dimensions are
$U^{p+q+r}T^{2p+q}$, so the exponents must satisfy
$$
p+q+r=1,\qquad 2p+q=k.
$$
Solving for $p$ and $q$ gives, up to a dimensionless multiplier,
\begin{equation}
\boxed{A_{r,k}(a,b,c)=a^{k-1+r}b^{2-k-2r}c^r.}
\label{eq:family}
\end{equation}
We take $r,k\in\mathbb Z$, so these are Laurent monomials: integer powers
may be positive, zero or negative. Dimension matching also permits real
$r$; integrality is the chosen algebraic class.

For $(a,b,c)=(L,R,1/C)$, equation \eqref{eq:family} becomes
\begin{equation}
\boxed{A_{r,k}=L^{k-1+r}R^{2-k-2r}C^{-r}.}
\label{eq:lrc}
\end{equation}
For example, at $k=3$ the choices $r=0,-1,-2$ give
$$
\frac{L^2}{R},\qquad LRC,\qquad R^3C^2.
$$
The two dimensional constraints leave one exponent free. They determine
a family of coefficients for each order; a selection rule chooses a member.

\newpage

# The coefficient table

Table \ref{tab:lattice} displays equation \eqref{eq:lrc} in two panels.
Boxed entries mark the staircase derived in the next section. The ODE
uses $k\geq0$; negative columns extend the dimension rule to repeated
integrals, whose time factors are $T^{-k}$.

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

The whole table follows from two ratios:
\begin{equation}
A_{r,k+1}=\frac LR A_{r,k},\qquad
A_{r-1,k}=\frac{R^2C}{L}A_{r,k}.
\label{eq:steps}
\end{equation}
Thus one step right contributes a time factor, while one step down
contributes a dimensionless factor.

\newpage

# Selecting the stairs

Choose the integer $r$ that minimizes the sum of absolute exponents
in $(L,R,C)$:
$$
F_k(r)=\lvert k-1+r\rvert+\lvert2-k-2r\rvert+\lvert r\rvert.
$$
If two choices tie, choose the one with a nonnegative exponent of $R$.
The result is
\begin{equation}
\boxed{r_k=\left\lfloor\frac{2-k}{2}\right\rfloor
=1-\left\lceil\frac{k}{2}\right\rceil.}
\label{eq:stairs}
\end{equation}
To see why, the triangle inequality gives
$$
F_k(r)\geq\lvert k-1\rvert+\lvert2-k-2r\rvert.
$$
The last term is at least $0$ for even $k$ and $1$ for odd $k$.
The choice \eqref{eq:stairs} attains this lower bound and makes the
exponent of $R$ equal to $0$ or $1$, respectively. It therefore satisfies
both the minimum and the tie rule. This simplicity criterion refers to
the declared parameter basis.

![The stairs $r=r_k$. Each horizontal pair uses one value of $r$; the next pair is one row lower. The boxed entries in Table \ref{tab:lattice} follow this path.](figures/staircase.pdf){#fig:stairs width=95%}

\FloatBarrier

Set $A_k=A_{r_k,k}$. Substituting $k=2n$ and $k=2n+1$ into
\eqref{eq:lrc} yields
\begin{equation}
\boxed{A_{2n}=L^nC^{n-1},\qquad A_{2n+1}=R(LC)^n,}
\quad n\in\mathbb Z.
\label{eq:parity}
\end{equation}
Consequently,
\begin{equation}
\boxed{A_{k+2}=LC\,A_k,\qquad A_0=\frac1C,\quad A_1=R.}
\label{eq:recurrence}
\end{equation}
Every second coefficient is obtained by multiplying by $LC$. The even
and odd orders are two interleaved geometric sequences.

# Assembling an ODE

For an integer $N\geq1$, the staircase coefficients define
\begin{equation}
P_N(D)y=0,\qquad P_N(D)=\sum_{k=0}^{N}A_kD^k.
\label{eq:ode}
\end{equation}
The first seven coefficients, in ascending derivative order, are
$$
(A_0,\ldots,A_6)=
\left(\frac1C,\ R,\ L,\ LRC,\ L^2C,\ L^2RC^2,\ L^3C^2\right).
$$
In the original reference symbols the same rule is
$$
A_{2n}=a^nc^{1-n},\qquad A_{2n+1}=b(a/c)^n,
\qquad A_{k+2}=\frac ac A_k.
$$
In particular, the coefficient of $D^3$ is $A_3=ab/c$, and direct
multiplication shows
\begin{equation}
\frac{ab}{c}D^3+aD^2+bD+c
=(bD+c)\left(1+\frac acD^2\right).
\label{eq:cubic}
\end{equation}
More generally, pairing adjacent orders gives, for $m\geq0$,
\begin{equation}
P_{2m+1}(D)=(c+bD)\sum_{j=0}^{m}\left(\frac acD^2\right)^j.
\label{eq:odd}
\end{equation}
For even order $2m$ with $m\geq1$, add $a^mc^{1-m}D^{2m}$ to
$P_{2m-1}(D)$. These are finite polynomial identities; no convergence
assumption is needed.

## Choosing other coefficients

To retain the full family, introduce
$$
S=\frac{b^2}{a},\qquad \tau=\frac ab,\qquad
\rho=\frac{b^2}{ac}.
$$
Then $[S]=U$, $[\tau]=T$ and $[\rho]=1$, and
\begin{equation}
A_{r,k}=S\tau^k\rho^{-r},\qquad
B_k=\sum_{r\in\mathcal R_k}w_{r,k}A_{r,k}
=S\tau^k\sum_{r\in\mathcal R_k}w_{r,k}\rho^{-r},
\label{eq:synthesis}
\end{equation}
where $\mathcal R_k\subset\mathbb Z$ is finite and $w_{r,k}$ are
dimensionless constants. Using $B_k$ in $\sum_{k=0}^N B_kD^ky=0$
gives a finite synthesis from the table; its order is $N$ when $B_N\ne0$.
The staircase is the choice $\mathcal R_k=\{r_k\}$ and $w_{r_k,k}=1$.

Dimension matching constructs the table. Minimizing integer exponents
selects the stairs, and the stairs give a coefficient at every order
through one recurrence. Finite weighted sums retain the other choices.

# Using phasors

With the convention $\operatorname{Re}(\widehat y e^{\mathrm i\omega t})$,
$\omega>0$, from [*The ODE Template and Its Domain Equivalents*][template],
replace $D$ by $\mathrm i\omega$. For real coefficients $B_k$ and
$Q(s)=\sum_{k=0}^N B_ks^k$, $Q(D)y=f$ becomes
\begin{equation}
\boxed{Q(\mathrm i\omega)\widehat y=\widehat f,\qquad
Q(\mathrm i\omega)=\sum_{k=0}^N B_k(\mathrm i\omega)^k.}
\label{eq:phasor-equation}
\end{equation}
If $Q(\mathrm i\omega)\ne0$, then
$\widehat y=\widehat f/Q(\mathrm i\omega)$. For the homogeneous
equation, a nonzero phasor requires $Q(\mathrm i\omega)=0$.

## The table and stairs in phasor form

Multiply column $k$ of Table \ref{tab:lattice} by
$(\mathrm i\omega)^k$. Each entry contributes
\begin{equation}
\Phi_{r,k}(\omega)
=A_{r,k}(\mathrm i\omega)^k
=S\rho^{-r}(\mathrm i\omega\tau)^k.
\label{eq:phasor-lattice}
\end{equation}
The factors $\mathrm i^k$ cycle through $1,\mathrm i,-1,-\mathrm i$.
Negative columns use the same rule for the harmonic antiderivative,
with integration constants specified separately. Weighted sums of
these entries give $Q(\mathrm i\omega)$.

For the staircase, write $\Phi_k=A_k(\mathrm i\omega)^k$.
Equation \eqref{eq:parity} gives
\begin{equation}
\Phi_{2n}=\frac1C(-\omega^2LC)^n,\qquad
\Phi_{2n+1}=\mathrm i\omega R(-\omega^2LC)^n,
\quad n\in\mathbb Z.
\label{eq:phasor-stairs}
\end{equation}
Hence $\Phi_{k+2}=-\omega^2LC\,\Phi_k$: every two orders reverse
the sign and multiply the magnitude by $\omega^2LC$. Pairing terms
as in \eqref{eq:odd} yields
\begin{equation}
\boxed{P_{2m+1}(\mathrm i\omega)
=\left(\frac1C+\mathrm i\omega R\right)
\sum_{n=0}^{m}(-\omega^2LC)^n,\qquad m\geq0.}
\label{eq:phasor-sum}
\end{equation}
For example,
$P_3(\mathrm i\omega)=(1/C+\mathrm i\omega R)(1-\omega^2LC)$.
The sum is finite, so no restriction $\omega^2LC<1$ is needed.

## Expressing the equation using a derivative

If $u=Dy$, then $\widehat u=\mathrm i\omega\widehat y$.
The multiplier relating $\widehat u$ to $\widehat f$ is therefore
\begin{equation}
H(\omega)=\frac{Q(\mathrm i\omega)}{\mathrm i\omega}
=\sum_{k=0}^N B_k(\mathrm i\omega)^{k-1},
\qquad \widehat f=H(\omega)\widehat u.
\label{eq:phasor-derivative}
\end{equation}
The exponent is $k$ for $y$ and $k-1$ for $Dy$. Terminal ratios of
this form are combined in [*Interconnecting Series and Parallel ODEs*][interconnect],
Section 3. The signed-work calculation for the selected $A_3=LRC$
is developed in [*Energy Ledgers for Forced Harmonic ODEs*][energy],
Parts 2 and 3.

# References {-}

1. H. Nilre and B. C. Herlin (2026). [The ODE Template and Its Domain Equivalents][template].
2. H. Nilre and B. C. Herlin (2026). [Interconnecting Series and Parallel ODEs][interconnect].
3. H. Nilre and B. C. Herlin (2026). [Energy Ledgers for Forced Harmonic ODEs][energy].

[template]: https://github.com/hobnilre/physics-ode-template
[interconnect]: https://github.com/hobnilre/physics-ode-interconnect-ser-par
[energy]: https://github.com/hobnilre/physics-ode-energy
