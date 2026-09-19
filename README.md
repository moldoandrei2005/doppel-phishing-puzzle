# Optimal phrase distribution under a KL detector

**Answer to the 3b1b talent page phishing puzzle.** An attacker chooses a distribution of phishing phrases to maximize the probability of success while keeping its phrase frequencies close enough to a baseline distribution to avoid an alarm. This is a constrained expected-payoff problem, with Kullback–Leibler (KL) divergence measuring how much the chosen distribution differs from the baseline.

Let $q=(q_1,\ldots,q_n)$ be the baseline distribution, $s_i$ the success probability of phrase $i$, and $C\geq0$ the detector threshold. We seek

$$
\max_{p\in\Delta_n}\sum_i p_i s_i
\quad\text{subject to}\quad
D(p\Vert q)=\sum_i p_i\log\frac{p_i}{q_i}\leq C.
$$

Assume $q_i>0$ on at least one phrase. Write

$$
s_m=\max_i s_i,\qquad S=\{i:s_i=s_m\},\qquad Q=\sum_{i\in S}q_i.
$$

## Result

If all $s_i$ are equal, every feasible distribution has the same payoff. Otherwise:

| Detection threshold | Optimal strategy |
| --- | --- |
| $0<C<\log(1/Q)$ | Use the exponential tilt $p_i^*=q_i e^{\beta s_i}/Z(\beta)$, where $Z(\beta)=\sum_jq_j e^{\beta s_j}$ and the unique $\beta>0$ that satisfies $D(p^*\Vert q)=C$. |
| $C\geq\log(1/Q)$ | Use $p_i^*=q_i/Q$ for $i\in S$ and $p_i^*=0$ otherwise. This attains the largest possible payoff $m$. |

## Full derivation

Read [the full proof (Word)](full-proof.docx) for the Lagrange-multiplier derivation, the KL limit calculation, and the boundary case. The site version is available at [index.html](index.html).
