Of course. Here is a proof for the given statement.

### **Proof**

We are given that $f: [a, b] \to \mathbf{R}$ is a bounded function and that for some partition $P = \{x_0, x_1, \dots, x_n\}$ of $[a, b]$, the lower and upper Darboux sums are equal:

$$L(f, P, [a, b]) = U(f, P, [a, b])$$

---

**1. Definitions of Darboux Sums**

Let's define the components of the Darboux sums for the partition $P$, where $a = x_0 < x_1 < \dots < x_n = b$. For each subinterval $I_i = [x_{i-1}, x_i]$:

* Let $\Delta x_i = x_i - x_{i-1}$ be the length of the subinterval.
* Let $m_i = \inf\{f(x) \mid x \in I_i\}$ be the infimum (greatest lower bound) of $f$ on $I_i$.
* Let $M_i = \sup\{f(x) \mid x \in I_i\}$ be the supremum (least upper bound) of $f$ on $I_i$.

The lower and upper Darboux sums are then defined as:

$$L(f, P, [a, b]) = \sum_{i=1}^{n} m_i \Delta x_i$$
$$U(f, P, [a, b]) = \sum_{i=1}^{n} M_i \Delta x_i$$

---

**2. Analyzing the Equality**

Starting with the given equality:

$$\sum_{i=1}^{n} m_i \Delta x_i = \sum_{i=1}^{n} M_i \Delta x_i$$

We can rearrange this equation by moving all terms to one side:

$$\sum_{i=1}^{n} M_i \Delta x_i - \sum_{i=1}^{n} m_i \Delta x_i = 0$$
$$\sum_{i=1}^{n} (M_i - m_i) \Delta x_i = 0$$

Now, let's analyze the terms in this summation.

* For any valid partition $P$, the length of each subinterval is strictly positive, so $\Delta x_i > 0$ for all $i$.
* By the definitions of supremum and infimum, for any given subinterval $I_i$, the infimum can be no larger than the supremum. Thus, $m_i \le M_i$, which implies that the difference $(M_i - m_i) \ge 0$.

This means that each term in the sum, $(M_i - m_i) \Delta x_i$, is a product of two non-negative numbers, and is therefore itself non-negative.

The only way a sum of non-negative terms can equal zero is if **every individual term is zero**. Therefore, for each subinterval $i=1, 2, \dots, n$, it must be true that:

$$(M_i - m_i) \Delta x_i = 0$$

Since we know $\Delta x_i > 0$, this forces the other part of the product to be zero:

$$M_i - m_i = 0 \implies \mathbf{M_i = m_i}$$

---

**3. Conclusion**

The condition $M_i = m_i$ means that for each subinterval $I_i = [x_{i-1}, x_i]$, the supremum of the function is equal to its infimum. This can only be true if the function **f is constant** on that subinterval. So, for each $i$, there exists a constant $c_i$ such that $f(x) = c_i$ for all $x \in [x_{i-1}, x_i]$.

Now we must show that these constants are all the same. Consider two adjacent subintervals, $[x_{i-1}, x_i]$ and $[x_i, x_{i+1}]$.

* On $[x_{i-1}, x_i]$, we have $f(x) = c_i$.
* On $[x_i, x_{i+1}]$, we have $f(x) = c_{i+1}$.

Since the function $f$ must have a single, well-defined value at the boundary point $x_i$, it follows that $f(x_i) = c_i$ and $f(x_i) = c_{i+1}$. Therefore, $c_i = c_{i+1}$.

By extending this argument across all adjacent subintervals, we find that $c_1 = c_2 = \dots = c_n$. Let's call this common value $c$.

Since $f(x) = c$ on every subinterval and the union of all subintervals is the entire interval $[a, b]$, we have proven that **$f$ is a constant function on $[a, b]$**.

∎