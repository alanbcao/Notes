Dynamic programming (DP) describes a problem solving methodology that **finds the optimal decision by breaking it down into a sequence of decisions over time**. DP is not useful for every problem. In particular, DP is usually employed on problems where
1. [*Bellman Principle of Optimality*] the optimal solution can be constructed from the optimal solutions of its subproblems, and
2. [*Overlapping Subproblems*] the recursive solution solves the same subproblems repeatedly.

**If the problem does not satisfy the Bellman Principle of Optimality, then the DP formulation will be invalid in general.** In that case, other structural properties must be exploited. Otherwise, a brute-force search may be necessary. **On the other hand, if the problem does not have overlapping subproblems, DP will produce the optimal solution but will be less efficient than divide-and-conquer methodologies.**

We may be interested in finding the optimal decision that maximizes some desired value over a finite horizon.
$$
\begin{aligned}
\max\left\{\ \mathbb{E}\left[\ \sum_t r_t(s_t,a_t)\ |\ s_t,a_t\ \right]\ \right\}
\end{aligned}
$$
The *finite-horizon dynamic program* used to solve this problem is given by the recursive equation known as the *Bellman equation*:
$$
\begin{aligned}
V_t(s_t) &= \max_{a_t\in A}\left\{\ r_t(s_t,a_t) + \mathbb{E}\left[\ V_{t+1}(s_{t+1})\ |\ s_t,a_t\ \right]\ \right\} \\
&= \max_{a_t\in A}\left\{\ r_t(s_t,a_t) + \sum_{s_{t+1}\in S} P(\ s_{t+1}\ |\ s_t,a_t\ ) V_{t+1}(s_{t+1})\ \right\}
\end{aligned}
$$
This recursive problem can be solved recursively. Since the value of $V_{t+1}(s_{t+1})$ depends on $V_{t+1}(s_{t+1})$, 
