Chapter 1

Event Operations:
1) Union: $A \cup B = \{x:x \in A \;or\; x \in B\}$
2) Intersection: TODO
3) Complement: TODO

Event Relationships
1) Contained: $A \subset B$ or $B \supset A$ i.e. $A$ subset $B$ or $B$ superset $A$
2) Equivalent: $A \subset B$ and $B \subset A \rightarrow A=B$.
3) Mutually Exclusive (AKA: Disjoint): $A \cap B = \emptyset$ i.e. $A$ and $B$ share no common elements.

De Morgan's Law
1) $A_1 \cup A_2 \cup \cdots \cup A_n = A_1' \cap A_2' \cap \cdots \cap A_n'$
   1) Special Case: $(A \cup B)' = A' \cap B'$
2) $A_1 \cap A_2 \cap \cdots \cap A_n = A_1' \cup A_2' \cup \cdots \cup A_n'$
   1) Special Case: $(A \cap B)' = A' \cup B'$

Counting Methods
1) Multiplication Principle
   1) Perform $r$ experiments sequentially.
   2) $E_x$ produces $n_x$ possible outcomes.
   3) for $r$ experiments $n_{total} = n_1 \times n_2 \times \cdots \times n_r$.
   4) e.g. Number of outcomes for $1d6$ and coin thrown together:
   5) $E_1 = 6$, $E_2 = 2 \rightarrow n_{total} = 6 \times 2 = 12$.
2) Addition Principle
   1) Suppose we can do $E$ using $k$ different procedures.
   2) Procedure $P_x$ has $n_x$ possible choices.
   3) Suppose the "choices" do not overlap, we can perform $E$ in $\sum\limits_{x=1}^{k} n_x$ ways.

Permutations & Combinations

1) $P_r^n = \frac{n!}{(n-r)!} = n(n-1)(n-2)\cdots(n-(r-1))$
    1) Special case: $r = n$, $P_n^n = n!$ i.e. num ways to arrange $n$ objects in order.
2) $C_r^n = {n \choose r} = \frac{n!}{r!(n-r!)} = {n \choose n-r}$

Probability

- Probability: Chance that a certain event may occur.
- Let $A$ be an event, $P(A)$ denotes probability that $A$ will occur.
- Probability is related to relative frequency
- $f_A = \frac{n_A}{n} f_A \rightarrow P(A)$ as $n \rightarrow \infty$

---

- If $A$ and $B$ are mutually exclusive, then $P(A \cup B)  = P(A) + P(B)$
- Proposition 2: $P(\emptyset) = 0$
- Proposition 3: $P(A_1 \cup A_2 \cup \cdots \cup A_n) = P(A_1) + P(A_2) + \cdots + P(A_n)$ if all events are mutually exclusive
- Proposition 4: $P(A') = 1 - P(A)$
- Proposition 5: $P(A) = P(A \cap B) + P(A \cap B')$
- Proposition 6: $P(A \cup B) = P(A) + P(B) - P(A \cap B)$
- Proposition 7: If $A \subset B$ then $P(A) \leq P(B)$
- Conditional Probability: $P(A|B) = \frac{P(A \cap B)}{P(B)}$
- Multiplication Rule:
  - $P(A \cap B) = P(A) P(B|A)$, if $P(A) \neq 0$
  - $P(A \cap B) = P(B) P(A|B)$, if $P(B) \neq 0$
- Inverse Probability Formula:
  - $P(A|B) = \frac{P(A)P(B|A)}{P(B)}$

Independence
- $A$ and $B$ are independent if and only if
- $P(A \cap B) = P(A) P(B)$
- $A \perp B$ denotes independence, $A \not\perp B$ denotes dependence
- If $P(A) \neq 0, A \perp B$ iff $P(B|A) = P(B)$
- $P(A \cap B) \neq P(A) P(B) \implies$ <b>dependent</b>
- If $A \perp B$, then $A \perp B'$, $A' \perp B$ and $A' \perp B'$
- Suppose $P(A) > 0, P(B) >0$. $A \perp B \implies$ Mutually Exclusive
- Suppose $P(A) > 0, P(B) >0$. Mutually Exclusive $\implies A \not\perp B$

Law of Total Probability
- Partition: Given mutually exclusive $A_1,\cdots, A_n$ and $\bigcup\limits_{i=1}^n Ai = S$, we call $A_1,\cdots, A_n$ a partition of $S$
- For a partition $A_1, \cdots, A_n$ of $S$ and an event $B \implies$
  -  $P(B) = \sum\limits_{i = 1}^n P(B \cap A_i) = \sum\limits_{i = 1}^n P(A_i)P(B|A_i)$
- Special Case: $P(B) = P(A)P(B|A) + P(A')P(B|A')$

Bayes Theorem
- Let $A_1, \cdots, A_n$ be a partition of $S$. For any $B$ and $k = 1, \cdots, n$:
- $P(A_k | B) = \frac{P(A_k \cap B)}{P(B)} = \frac{P(A_k)P(B|A_k)}{\sum\limits_{i=1}^n P(B \cap A_i)} = \frac{P(A_k)P(B|A_k)}{\sum\limits_{i=1}^n P(A_i)P(B|A_k)}$
- Special Case: $n =2 \rightarrow P(A|B) = \frac{P(A)P(B|A)}{P(A)P(B|A) + P(A')P(B|A')}$

Chapter 2

Random Variable
- Function X, which maps every $s \in S$ to a real number. i.e. $X:S \mapsto \mathbb{R}$
- Range Space: e.g. $R_x = \{0,1,2\}$ for roll $2d2$, $X = n_{heads}$

Probability Distribution
- Discrete: $R_x$ is finite or countable, e.g. $R_x = \{x_1, x_2, x_3, \cdots \}$
- Continuous: $R_x$ is an interval or collection of intervals

Probability Mass Function (pmf) [Discrete]

$$f(x) = \begin{cases}
    P(X = x), & for\; x \in R_x \\
    0, & for\; x \not\in R_x
    \end{cases}$$
- In Tabular Form, for roll $2d2$, $X = n_{heads}$

| x | 0 | 1 | 2 |
| --- | --- | --- | --- |
| f(x) | 1/4 | 1/2 | 1/4 |

Probability Density Function (pdf) [Continuous]
- Example of pdf:

$$f(x) = \begin{cases}
    2x, & for\; 0 \leq x < 1 \\
    0, & otherwise
    \end{cases}$$
- for any $f(x)$ representing a probability density function
- $\int_{-\infty}^{\infty} f(x) dx = 1$ i.e. sum of probabilities is $1$
- $P(a \leq X \leq b) = \int_{a}^{b} f(x) dx$ i.e. probability of $X$, where $X$ is an interval, is the integral of $f(x)$ in that interval
- Two conditions for validity of pdf:
    1) $f(x) \geq 0, \forall x \in R_x; f(x) = 0, \forall x \not\in R_x$
    2) $\int_{R_x} f(x) dx = 1$

Cumulative Distribution Function (cdf) [Discrete / Continuous]
- $F(x) = P(X \leq x)$
- For Discrete:
- $P(a \leq X \leq b) = P(X \leq b) - P(X < a) = F(b) - F(a-)$
- $a-$ represents largest value in $R_x$ that is smaller than $a$
- For Continuous:
- $F(x) = \int_{-\infty}^x f(t) dt$
- $f(x) = \frac{d}{dx}F(x)$
- $P(a \leq X \leq b) = P(a < X < b) = F(b) - F(a)$

Probability Distribution General Remarks
1) $F(x)$ is non decreasing. i.e. $\forall x_1 < x_2, F(x_1) \leq F(x_2)$
2) Every <em>pmf/pdf</em> uniquely maps to **one** <em>cdf</em> and vice versa
3) Ranges of $F(x)$ and $f(x)$ satisfy:
   - $0 \leq F(x) \leq 1$
   - Discrete: $0 \leq f(x) \leq 1$
   - Continuous $f(x) \geq 0$, but not necessarily $f(x) \leq 1$

Expectation (aka: Mean) and Variance
- Expectation/Mean: $\rightarrow E(X) = \mu_X$
- For Discrete: $E(X) = \sum\limits_{x_i \in R_X}x_i f(x_i)$ 
- Continuous: $\mu_X = \int_{-\infty}^{\infty} xf(x)dx$

Properties of Expectation
1. $E(aX + b) = aE(x) + b$
2. $E(X + Y) = E(X) + E(Y)$
3. Let $g(\cdot)$ be an arbitrary function
   1. For discrete: $E[g(X)] = \sum\limits_{x \in R_X} g(x)f(x)$
   2. For continuous: $E[g(X)] = \int_{R_X} g(x)f(x)dx$

Variance
- Let $g(x) = (x - \mu_X)^2$ then $E[(g(X))]$ is **variance** for $X$
- i.e. $\sigma_X^2 = V(X) = E(X - \mu_X)^2$
- For discrete: $V(X) = \sum\limits_{x\in R_X}(x - \mu_X)^2 f(x)$
- For continuous: $V(X) = \int_{R_X}(x - \mu_X)^2 f(x) dx$
- $V(X) \geq 0\; \forall X \iff P(X = E(X)) = 1$ i.e. $X$ is a constant
- For $a, b \in \mathbb{R}, V(aX+B) = a^2V(X)$
- Alternative formula: $V(X) = E(X^2) - [E(X)]^2$
- Standard Deviation: $\sigma_X = \sqrt{V(X)}$

Miscellaneous:
- Standard 52-card deck: 
  - 13 ranks - {A, 2, 3, 4, 5, 6, 7, 8, 9, 10, J, Q, K}
  - 4 suits - {:clubs:, :diamonds:, :hearts:, :spades:}