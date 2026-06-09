What is dynamic programming?

The finite-horizon dynamic program is given by the recursive equation
$$
\begin{align}
V_t(s_t) &= \max_{a_t\in A}\left\{\ r_t(s_t,a_t) + \mathbb{E}\left[\ V_{t+1}(s_{t+1})\ |\ s_t,a_t\ \right]\ \right\} \\
&= \max_{a_t\in A}\{\ r_t(s_t,a_t) + \sum_{s_{t+1}\in S} P(\ s_{t+1}\ |\ s_t,a_t\ ) V_{t+1}(s_{t+1})\ \}
\end{align}
$$
This recursive problem can be solved recursively. Since the value of $V_{t+1}(s_{t+1})$ depends on $V_{t+1}(s_{t+1})$, 
