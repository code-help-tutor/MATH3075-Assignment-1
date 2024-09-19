# MATH3075 Assignment 1

## MATH3075 Assignment 1: Solutions

### 1. Single-period market model [12marks]

Consider a single-period market model $M = (B,S)$ on a sample space $\Omega = \{\omega_1, \omega_2, \omega_3\}$. Assume that $r = 3$ and the stock price $S = (S_0, S_1)$ satisfies $S_0 = 5$ and $S_1 = (36, 20, 4)$. The real-world probability $P$ is such that $P(\omega_i) = p_i > 0$ for $i = 1, 2, 3$.

**(a) Find the class $M$ of all martingale measures for the model $M$. Is the market model $M$ arbitrage-free? Is this market model complete?**

Answer: [2 marks] We need to solve: $q_1 + q_2 + q_3 = 1$, $0 < q_i < 1$ and (since $1 + r = 4$)
\[
EQ(S_1) = 36q_1 + 20q_2 + 4q_3 = (1 + r)S_0 = 20
\]
or, equivalently,
\[
EQ(S_1 - (1 + r)S_0) = 16q_1 - 16q_3 = 0.
\]
Let $q_2 = \lambda$. Then $q_1 = q_3 = \frac{1 - \lambda}{2}$ where $0 < \lambda < 1$. Hence
\[
M = 
\left\{
(q_1, q_2, q_3) \mid q_1 = q_3 = \frac{1 - \lambda}{2}, q_2 = \lambda, 0 < \lambda < 1
\right\}
\]
The market model $M$ is arbitrage-free since $M \neq \varnothing$. Moreover, it is incomplete since the uniqueness of a martingale measure for $M$ fails to hold.

**(b) Find the replicating strategy for the contingent claim $Y = (10, 2, -6)$ and compute its arbitrage price $p_{i0}(Y)$ at time 0 through replication.**

Answer: [2 marks] First solution. We may use a portfolio $(x, \phi) \in \mathbb{R}^2$ and represent the wealth as follows: $V_0(x, \phi) = x$ and
\[
V_1(x, \phi) = (x - \phi S_0)(1 + r) + \phi S_1 = x(1 + r) + \phi (S_1 - S_0(1 + r)) = xB_1 + \phi (S_1 - S_0B_1)
\]
Then we solve the following equations
\[
\begin{cases}
4x + 16\phi = 10 \\
4x + 0\phi = 2 \\
4x - 16\phi = -6
\end{cases}
\]
From the second equation, we obtain $p_{i0}(Y) = x = 0.5$ and thus from the first (or last) equation we get $\phi = 0.5$.

Second solution. The wealth process of a portfolio $(\phi_{00}, \phi_{10})$ satisfies
\[
V_0(\phi) = \phi_0B_0 + \phi_0S_0, V_1(\phi) = \phi_0B_1 + \phi_0S_1.
\]
Replication of a claim $Y$ means that $V_1(\phi)(\omega_i) = Y(\omega_i)$ for $i = 1, 2, 3$. Hence to find a replicating strategy for $Y$, we need to solve the following equations
\[
\begin{cases}
4\phi_{00} + 36\phi_0 = 10 \\
4\phi_{00} + 20\phi_0 = 2 \\
4\phi_{00} + 4\phi_0 = -6
\end{cases}
\]
We obtain $(\phi_{00}, \phi_{10}) = (-2, 0.5)$ and thus $p_{i0}(Y) = x = \phi_{00}B_0 + \phi_{10}S_0 = -2 + 0.5 \times 5 = 0.5$.
Hence at time 0 we need to buy 0.5 shares of stock. For this purpose, after receiving 0.5 units of cash from the buyer of the claim $Y$, we need to borrow two units of cash in the money market.

**(c) Recompute $p_{i0}(Y)$ using the risk-neutral valuation formula with an arbitrary martingale measure $Q$ from the class $M$.**

Answer: [2 marks] For any $0 < q_2 = \lambda < 1$ and $q_1 = q_3 = \frac{1 - \lambda}{2}$, the risk-neutral valuation formula yields, for every $0 < \lambda < 1$,
\[
p_{i0}(Y) = EQ(Y/B_1) = \frac{1 - \lambda}{2} + \lambda - 3\frac{1 - \lambda}{2} = 0.5.
\]
As expected, the price $p_{i0}(Y)$ does not depend on $\lambda$, that is, on a choice of a martingale measure.

**(d) Check whether that the contingent claim $X = (5, 4, -1)$ is attainable in $M$.**

Answer: [2 marks] To find a replicating strategy, we need to solve the following equations
\[
\begin{cases}
4\phi_{00} + 36\phi_0 = 5 \\
4\phi_{00} + 20\phi_0 = 4 \\
4\phi_{00} + 4\phi_0 = -1
\end{cases}
\]
The strategy $(\phi_0, \phi_1) = (\frac{11}{16}, \frac{1}{16})$ is a unique solution to the first two equations, but it does not satisfy the last one. Hence no replicating strategy for $X$ exists in $M$.

**(e) Find the range of arbitrage prices for $X$ using the class $M$ of all martingale measures for the model $M$.**

Answer: [2 marks] We compute the range of prices for $X$ consistent with the no-arbitrage principle. We have
\[
p_{i0}(X) = EQ(X/B_1) = \frac{1 - \lambda}{2} + 4\lambda - 1\frac{1 - \lambda}{2} = 0.5(1 + \lambda).
\]
Since from part (c) we know that $\lambda \in (0, 1)$, it is clear the range of prices $p_{i0}(X)$ consistent with the no-arbitrage principle is the open interval $(0.5, 1)$.

**(f) Suppose that at time 0 you have sold the claim $X$ for 2 units of cash. Show that there exists a hedge ratio $\phi$ such that the wealth $V_1(2, \phi)$ at time 1 strictly dominates the payoff $X$, meaning that $V_1(2, \phi)(\omega_i) > X(\omega_i)$ for $i = 1, 2, 3$.**

Answer: [2 marks] It suffices to give any example of a portfolio $(x, \phi)$ with the initial value $x = 2$ such that the inequality $V_1(x, \phi)(\omega_i) > X(\omega_i)$ holds for $i = 1, 2, 3$. We may use the representation of the wealth at time $t = 1$
\[
V_1(x, \phi) = (x - \phi S_0)(1 + r) + \phi S_1 = x(1 + r) + \phi (S_1 - S_0(1 + r)) = xB_1 + \phi (S_1 - S_0B_1)
\]
Since $x = 2$ and $B_1 = 4$ so that $S_0B_1 = 20$, it suffices to find a number $\phi \in \mathbb{R}$ such that the following inequalities are satisfied
\[
\begin{cases}
8 + 16\phi > 5 \\
8 + 0\phi > 4 \\
8 - 16\phi > -1
\end{cases}
\]
For instance, we may take $\phi = 0.5$. Then the wealth of the portfolio $(x, \phi) = (2, 0.5)$ at time $t = 1$ equals $V_1(2, 0.5) = (16, 8, 0)$ so it is clear that $V_1(2, 0.5)(\omega_i) > X(\omega_i)$ for $i = 1, 2, 3$.

### 2. Static hedging with options [8marks]

Consider a parametrised family of contingent claims with the payoff $Y(\alpha)$ at time $T$ given by the following expression
\[
Y(\alpha) = \min\{\alpha, \beta + 2|\beta - S_T| - S_T\}
\]
where a real number $\beta > 0$ is fixed and the parameter $\alpha$ is an arbitrary real number such that $\alpha \geq 0$.

**(a) For any fixed $\alpha \geq 0$, sketch the profile of the payoff $Y(\alpha)$ as a function of $S_T \geq 0$ and find a decomposition of $Y(\alpha)$ in terms of the payoffs of standard call and put options with maturity date $T$ (do not use a constant payoff). Notice that a decomposition of $Y(\alpha)$ may depend on the value of the parameter $\alpha$.**

Answer: [2 marks] It is easy to see that the payoff $Y(\alpha)$ is a piecewise linear and continuous function, which is nonnegative and bounded from above by $\alpha$.

We first consider the case $\alpha \geq 3\beta$. Let us take $\beta = 1$. Then for $\alpha \geq 3\beta$ we obtain by taking, for instance, $\alpha = 4$
\[
\begin{array}{|c|c|}
\hline
\beta = 1 & \beta + \alpha = 5 \\
\hline
S_T & Y(\alpha) \\
\hline
\end{array}
\quad
\begin{array}{|c|c|}
\hline
0 \leq S_T \leq 1 & S_T + 2(1 - S_T) - S_T = 2 - S_T \\
\hline
1 < S_T \leq 3 & 1 + 2(S_T - 1) - S_T = S_T - 1 \\
\hline
S_T > 3 & \alpha = 4 \\
\hline
\end{array}
\]

We now consider the case $\alpha < 3\beta$. We take again $\beta = 1$ and we obtain by taking, for instance, $\alpha = 2$
\[
\begin{array}{|c|c|}
\hline
\beta = 1 & \beta + \alpha = 3 \\
\hline
S_T & Y(\alpha) \\
\hline
\end{array}
\quad
\begin{array}{|c|c|}
\hline
0 \leq S_T \leq 1 & S_T + 2(1 - S_T) - S_T = 2 - S_T \\
\hline
1 < S_T \leq \frac{4}{3} & 1 + 2(S_T - 1) - S_T = S_T - 1 \\
\hline
\frac{4}{3} < S_T \leq 3 & 3 - S_T \\
\hline
S_T > 3 & \alpha = 2 \\
\hline
\end{array}
\]

It is readily seen that for $\alpha \geq 3\beta$ the payoff $Y(\alpha)$ can be represented as follows
\[
Y(\alpha) = 3P_T(\beta) + C_T(\beta) - C_T(\beta + \alpha)
\]
whereas for $0 \leq \alpha < 3\beta$ we have that
\[
Y(\alpha) = 3P_T(\beta) - 3P_T\left(\beta - \frac{1}{3}\alpha\right) + C_T(\beta) - C_T(\beta + \alpha).
\]
Notice that the second decomposition above gives $Y(\alpha) = 0$ when $\alpha = 0$ and the two decompositions of $Y(\alpha)$ coincide when $\alpha = 3\beta$.

**(b) Assume that call and put options with all strikes are traded at time 0 at some finite prices. For each value of $\alpha \geq 0$, compute the arbitrage price $p_{i0}(Y(\alpha))$ at time $t = 0$ for the claim $Y(\alpha)$ using the prices at time 0 of call and put options and a suitable decomposition obtained in part (a).**

Answer: [2 marks] By the additivity property of arbitrage pricing, we obtain, for every $0 \leq \alpha \leq 3\beta$,
\[
p_{i0}(Y(\alpha)) = 3P_0(\beta) - 3P_0\left(\beta - \frac{1}{3}\alpha\right) + C_0(\beta) - C_0(\beta + \alpha)
\]
and, for every $\alpha \geq 3\beta$,
\[
p_{i0}(Y(\alpha)) = 3P_0(\beta) + C_0(\beta) - C_0(\beta + \alpha).
\]
In particular, we deduce from (1) that $p_{i0}(Y(\alpha)) = 0$ when $\alpha = 0$, which is obvious since $Y(\alpha) = 0$ when $\alpha = 0$.

**(c) For any $\alpha > 0$, examine the sign of an arbitrage price of the claim $Y(\alpha)$ in any (not necessarily complete) arbitrage-free market model $M = (B,S)$ with a finite state space $\Omega$. Justify your answer.**

Answer: [2 marks] Since the payoff $Y(\alpha)$ is strictly positive for every value of $S_T$ (except for $S_T = \beta$) the price $p_{i0}(Y(\alpha))$ should be strictly positive in any arbitrage-free market model $M = (B,S)$ since otherwise an arbitrage opportunity would arise in the extended market model. You may use the argument that the range of prices for any contingent claim $X$ coincides with the range of values of the expectation $EQ(B_T^{-1}X)$ when $Q$ runs over the class $M$ of all martingale measures for the model $M$.

**(d) Consider a complete arbitrage-free market model $M = (B,S)$ defined on some finite sample space $\Omega$. Show that the arbitrage price of $Y(\alpha)$ at time $t = 0$ is a monotone function of the variable $\alpha \geq 0$ and find the limits $\lim_{\alpha \to 0}p_{i0}(Y(\alpha))$, $\lim_{\alpha \to \infty}p_{i0}(Y(\alpha))$ and $\lim_{\alpha \to 3\beta}p_{i0}(Y(\alpha))$.**

Answer: [2 marks] We observe that the payoff $Y(\alpha)$ increases when $\alpha$ increases. Specifically, if we consider the payoffs $Y(\alpha_1)$ and $Y(\alpha_2)$ corresponding to $\alpha_1$ and $\alpha_2$, respectively, where $\alpha_1 < \alpha_2$ then it is clear that $Y(\alpha_1) \leq Y(\alpha_2)$. Consequently, $p_{i0}(Y(\alpha_1)) \leq p_{i0}(Y(\alpha_2))$ and thus the price $p_{i0}(Y(\alpha))$ is a nondecreasing function of the variable $\alpha$.

Furthermore, $\lim_{\alpha \to 0}p_{i0}(Y(\alpha)) = 0$ since $\lim_{\alpha \to 0}Y(\alpha)(\omega) = 0$ for all $\omega \in \Omega$ and thus
\[
0 \leq \lim_{\alpha \to 0}\sup_{Q \in M}EQ(B_T^{-1}Y(\alpha)) \leq \lim_{\alpha \to 0}\max_{\omega \in \Omega}B_T^{-1}Y(\alpha)(\omega) = 0.
\]
Moreover, using (1) and (2)
\[
\lim_{\alpha \to 3\beta}p_{i0}(Y(\alpha)) = 3P_0(\beta) + C_0(\beta) - C_0(4\beta), \lim_{\alpha \to \infty}p_{i0}(Y(\alpha)) = 3P_0(\beta) + C_0(\beta).
\]# MATH3075 Assignment 1

# CS Tutor | 计算机编程辅导 | Code Help | Programming Help

# WeChat: cstutorcs

# Email: tutorcs@163.com

# QQ: 749389476

# 非中介, 直接联系程序员本人
