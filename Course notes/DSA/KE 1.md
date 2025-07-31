## O - Notation
![[Pasted image 20250725155524.png]]

## **Big O notation** involving **functions with two variables** (e.g., n and m). These help students practice analyzing complex runtimes.
---

## **Exercise 1: Double Loop**

```python
for i in range(n):
    for j in range(m):
        print(i, j)
```

**Solution:**  
- Outer loop runs n times.
- Inner loop runs m times for each i.
- Total iterations: n * m.
- **Big O:** O(nm)

---

## **Exercise 2: Nested Loop with Inner Radius**

```python
for i in range(n):
    for j in range(i, m):
        print(i, j)
```

**Solution:**  
- For each i, j goes from i to m-1. Number of iterations for given i is (m - i).
- Total iterations:  
  $$
  \sum_{i=0}^{n-1} (m - i) = n \cdot m - \frac{n(n-1)}{2}
  $$
- Highest order term is n*m, so ignores lower-degree terms and constants.
- **Big O:** O(nm)

---

## **Exercise 3: Separate Loops**

```python
for i in range(n):
    print(i)

for j in range(m):
    print(j)
```

**Solution:**  
- First loop: n iterations.
- Second loop: m iterations.
- Total: n + m.
- **Big O:** O(n + m)

---

## **Exercise 4: Nested with Logarithm**

```python
for i in range(n):
    j = 1
    while j < m:
        print(i, j)
        j *= 2
```

**Solution:**  
- Outer loop: n times.
- Inner: starts at 1 and doubles each time until m. This is O(log m) iterations per i.
- Total: n * log m
- **Big O:** O(n log m)

---

## **Exercise 5: Triple Loop**

```python
for i in range(n):
    for j in range(m):
        for k in range(10):
            print(i, j, k)
```

**Solution:**  
- Outer: n times.
- Middle: m times.
- Inner: 10 times (constant).
- Total: n * m * 10 = 10nm
- Drop constant: **Big O:** O(nm)




## Problem

$$
f(n, m) = \max(3^m + 5 n^2,\;\; 16 m^3 + 9 n)
$$

We want to determine the asymptotic behavior in terms of both \(n\) and \(m\).

---

## **Step 1: Extract Dominant Terms**

- \(3^m + 5 n^2\) becomes \(O(3^m + n^2)\) (ignore constants)
- \(16 m^3 + 9 n\) becomes \(O(m^3 + n)\)

So,

$$
f(n, m) = \max(3^m + n^2,\; m^3 + n)
$$

---

## **Step 2: Compare Both Arguments**

There are two sorts of terms—exponential (in \(m\)), polynomials (in \(m\) and \(n\)), and linear in \(n\).

- For **large \(m\)**, \(3^m\) will grow much faster than \(m^3\), \(n^2\), or \(n\).
- For **large \(n\) and small \(m\)**, \(n^2\) can be larger than both \(m^3\) and \(3^m\) for small values of \(m\). But eventually, for larger \(m\), \(3^m\) will outpace everything.
- For **large \(m\), any \(n\)**: \(3^m\) will dominate.
- For **large \(n\), small \(m\)**: \(n^2\) will dominate.

So the function’s upper bound is determined by which of \(3^m\) and \(n^2\) is larger.

---

## **Step 3: Asymptotic Bound**

Therefore, asymptotically:

$$
f(n, m) = O\left(\max(3^m,\, n^2)\right)
$$

In words: **the maximum of \(3^m\) and \(n^2\) will always dominate the growth rate of this function**.

---

## **Step 4: Examples**

- If \(m\) is fixed and \(n \to \infty\): \(f(n, m) = O(n^2)\)
- If \(n\) is fixed and \(m \to \infty\): \(f(n, m) = O(3^m)\)
- If both grow, the term that grows faster (between \(n^2\) and \(3^m\)) wins.

---

## **Final Boxed Answer**

$$
\boxed{O\left(\max(3^m,\; n^2)\right)}
$$

---

Let’s construct an example algorithm with complexity  
$$\mathbf{O(\max(3^m,\, n^2))}$$
### Example Problem

Suppose we receive as input:

- An integer n and an integer m.
- A list of length n.

Our algorithm will:

1. First, generate **all possible strings of length m where each character is 'A', 'B', or 'C'** (there are exactly \(3^m\) such strings).
2. Traverse the n-element list **quadratically** (double loop, \(n^2\)), doing some simple processing.

The total time is proportional to **the greater of the two steps**, thus \(\max(3^m,\, n^2)\).

---

### Python Implementation

```python
import itertools

def algorithm(n, m, data):
    # Step 1: Generate all possible strings of length m over 'A', 'B', 'C'
    count1 = 0
    for s in itertools.product('ABC', repeat=m):
        # Do something trivial for each string
        count1 += 1

    # Step 2: Quadratic computation over the data list
    count2 = 0
    for i in range(n):
        for j in range(n):
            # Do something trivial for each pair
            count2 += 1

    print("Step 1 operations:", count1)
    print("Step 2 operations:", count2)
    # Return total count to show both are evaluated
    return max(count1, count2)

# Example usage:
n = 100
m = 5
data = [0]*n
print(algorithm(n, m, data))
```

---

### **Explanation**

- itertools.product('ABC', repeat=m) generates all \(3^m\) strings (step 1: exponential in m).
- The double loop over n runs \(n^2\) times (step 2: quadratic in n).
- The overall runtime is \(O(\max(3^m, n^2))\), because both are always performed and whichever is bigger dominates.



