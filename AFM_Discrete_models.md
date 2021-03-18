### Advanced Financial Models

#### Discrete-time models

19/12/2019

- (P16)
  $$
  \textbf{Market Model:}\quad
  \left\{\begin{array}{lll}
  \text{Price Process:}\quad &P&=(P_t)_{t\ge 0}&\subseteq \mathbb{R}^{n} \\ 
  \text{Dividend Process:}\quad &\delta &= (\delta_t)_{t\ge 0}&\subseteq \mathbb{R}^{n} \end{array}\right.
  $$
  
- (P16)
  $$
  \textbf{Investor Model:}\quad
  \left\{\begin{array}{lll}
  \text{Wealth Process:}\quad &X&=(X_t)_{t\ge 0}&\subseteq \mathbb{R} \\ 
  \text{Income Process:}\quad &I&= (I_t)_{t\ge 0}&\subseteq \mathbb{R} \\
  \text{Consumption Stream:}\quad &C&=(C_t)_{t\ge 0}&\subseteq \mathbb{R} \\
  \text{Investment Strategy/Portfolio Process:}\quad &H&=(H_t)_{t\ge 1}&\subseteq \mathbb{R}^n
  \end{array}\right.
  $$
  
- (P16-17) **Model**:

  $P, \delta, (I=0)$  given, the initial wealth  $X_0=x$  given,  $H$  as a control, then:
  $$
  \begin{aligned}
  X_t=X_{t}^{x, H}&=
  \left\{\begin{array}{ll}
  {x} & {t=0} \\ {H_{t} \cdot(P_{t}+\delta_{t})} & {t \ge 1}
  \end{array}\right. \qquad(P,\delta,x,H)
  \\
  C_t=C_{t}^{x, H}&=
  X_{t}^{x, H}+I_{t}-H_{t+1} \cdot P_{t}
  \\
  &=\left\{\begin{array}{ll}
  {x-H_1\cdot P_0+I_0} & {t=0} \\ {H_{t} \cdot(P_{t}+\delta_{t})-H_{t+1} \cdot P_t+I_t} & {t \ge 1}
  \end{array}\right. \qquad(P,\delta,I,x,H)
  \end{aligned}
  $$

- (P17) **Def**: (Utility maximisation problem)
  $$
  \text { maximise } \mathbb{E}[U(c)] \text { subject to }
  \left\{\begin{array}{l}{c_0=x-H_1\cdot P_0+I_0} & {t=0} \\
  {c_t=H_{t} \cdot(P_{t}+\delta_{t})-H_{t+1} \cdot P_t+I_t} & {1\le t\le T-1} \\
  {c_T=H_T \cdot(P_T+\delta_T)} & {t=T}
  \end{array}\right.
  $$
  where  $U: \mathbb{R}^{1+T} \rightarrow \mathbb{R} \cup\{-\infty\}$  is a given utility function:

  - $c_{t} \longmapsto U(c_{0}, \ldots, c_{T})$  is strictly increasing for each $t$,
  - $U$ is strictly concave (Usually).

- (P17) **Def**: An *arbitrage*  $H=(H_t)_{t\ge 1}\subseteq \mathbb{R}^n$  previsible, $s.t.\ \exist$ non-random  $T>0$, satisfies:

  $\left\{\begin{array}{ll}
  {-H_1\cdot P_0} & {t=0} & \ge 0 \quad \text{a.s.} \\ {H_{t} \cdot(P_{t}+\delta_{t})-H_{t+1}\cdot P_t} & {1\le t\le T-1} & \ge 0 \quad \text{a.s.} \\ {H_T\cdot (P_T+\delta_T)} & {t=T} & \ge 0 \quad \text{a.s.}
  \end{array}\right.\quad$  and  $\mathbb{P}(\text{at least one}>0)>0.$

  **i.e.** Let the initial wealth  $X_0=x=0$, the consumption stream  $C=(C_t)_{t\ge 0}$  satisfies:

  - $C\ge 0$  a.s. (*i.e.*  $C_t\ge 0$  a.s. for all  $0\le t\le T$)  and
  - $\mathbb{P}(C_{t}>0$  for some  $0 \leq t \leq T)>0.$

- (P31) **Def**: A *terminal consumption arbitrage*  $H=(H_t)_{t\ge 1}\subseteq \mathbb{R}^n$  previsible, $s.t.\ \exist$ non-random  $T>0$, satisfies:

  $\left\{\begin{array}{ll}
  {-H_1\cdot P_0} & {t=0} & = 0 \quad \text{a.s.} \\ {H_{t} \cdot(P_{t}+\delta_{t})-H_{t+1}\cdot P_t} & {1\le t\le T-1} & = 0 \quad \text{a.s.} \\ {H_T\cdot (P_T+\delta_T)} & {t=T} & \ge 0 \quad \text{a.s.}
  \end{array}\right.\quad$  and  $\mathbb{P}(H_T\cdot (P_T+\delta_T)>0)>0.$

  **i.e.** Let the initial wealth  $X_0=x=0$, the consumption stream  $C=(C_t)_{t\ge 0}$  satisfies:

  - “**Pure-investment**”:  $C_0=...=C_{T-1}=0$  a.s. and
  - $C_T\ge 0$  a.s. and
  - $\mathbb{P}(C_T>0)>0.$

- (P17) **Note**:

  $\boxed{\textbf{Existence of a maximiser} \text{ (to the utility maximisation problem)} \Longrightarrow \textbf{No arbitrage} \text{ (in the market model)}}$

- (P19) **Def**: A *martingale deflator*  $Y=(Y_t)_{t\ge 0}\subseteq \mathbb{R}$  adapted, $s.t.$

  - $Y\ge 0$  a.s. (*i.e.*  $Y_t>0$  a.s. for all  $t\ge 0$)  and

  - $M=(M_t)_{t\ge 0}\subseteq \mathbb{R}^n: M_{t}\overset{def}{=}P_{t} Y_{t}+\sum_{s=1}^{t} \delta_{s} Y_{s}$  is a martingale.

    Or equivalently,

  - $YP$  and  $Y\delta$  are integrable and  $\mathbb{E}\left[Y_{t+1}\left(P_{t+1}+\delta_{t+1}\right) | \mathcal{F}_{t}\right]=Y_{t} P_{t}$  for all  $t\ge 0.$

- (P19) **Thm**: (First fundamental theorem of asset pricing, 1FTAP)

  $\boxed{\textbf{No arbitrage} \text{ (in the market model)} \iff \textbf{Existence of a martingale deflator} \text{ (for the market model)}}$

- (P25-26) Proof of 1FTAP, easier direction ($\Longleftarrow$)

  If the market model has a martingale deflator, then there is no arbitrage.

- (P26-27) Lagrangian duality.

  $\boxed{\textbf{Existence of a maximiser} \Longrightarrow \textbf{Existence of a martingale deflator}}$

- (P27-30) Proof of 1FTAP, harder direction ($\Longrightarrow$)

  If the market model has no arbitrage, then there exists a martingale deflator.

- (P31) **Def**: A *numeraire portfolio*  $\eta=(\eta_t)_{t\ge 0}\subseteq \mathbb{R}^n$  previsible, $s.t.$

  - $N=\eta\cdot P=(\eta_t \cdot P_t)_{t\ge 0}>0$  a.s. and
  - **Pure-investment**:  $(\eta_t-\eta_{t+1})\cdot P_t=0$  for all  $t\ge 0.$

  **i.e.** Let the initial wealth  $X_0=x=\eta_0\cdot P_0$, the wealth process  $N=(N_t)_{t\ge 0}$  and the consumption stream  $C=(C_t)_{t\ge 0}$  satisfies:

  - $N>0$  a.s. and
  - **Pure-investment**:  $C=0$  a.s.

- (P31) **Def**: A *numeraire asset* $N=(N_t)_{t\ge 0}$ is an asset $s.t.$

  - $N>0$  a.s.

- (P32) **Def**: An *equivalent martingale measure*  $\mathbb{Q}$  *w.r.t the numeraire*  $N$  is any probability measure $s.t.$

  - $\mathbb{Q}\sim \mathbb{P}$  and
  - $\frac{P}{N}=(\frac{P_t}{N_t})_{t\ge 0}$  is a $\mathbb{Q}$-martingale.

- (P31) **Prop**:

  $\boxed{\textbf{Existence of an arbitrage} \stackrel{\exist \text{ a numeraire }N}{\iff} \textbf{Existence of a terminal consumption arbitrage}}$

- (P34) **Prop**:

  $\boxed{\textbf{Existence of an equivalent martingale measure w.r.t. }N \stackrel{\exist \text{ a numeraire }N}{\iff} \textbf{Existence of a martingale deflator}}$

- (P35) **Thm**: (1FTAP when there is a numeraire)
  $$
  \boxed{
  \begin{array}{ll}
  \qquad \qquad \quad \ \ \boxed{\textbf{No arbitrage}} &\Longleftrightarrow& \qquad \qquad \quad \boxed{\textbf{Existence of a martingale deflator}} \\
  \qquad \qquad \qquad \Updownarrow \exist \text{ a numeraire }N && \qquad \qquad \qquad \qquad \qquad \Updownarrow \exist \text{ a numeraire }N \\
  \boxed{\textbf{No terminal consumption arbitrage}} &\Longleftrightarrow& \boxed{\textbf{Existence of an equivalent martingale measure w.r.t. }N}
  \end{array}
  }
  $$
  

