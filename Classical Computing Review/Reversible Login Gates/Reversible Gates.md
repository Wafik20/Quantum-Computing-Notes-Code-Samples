# What is a Reversible, Irreversible Gate?

A **reversible gate** is a logic gate where, given the output(s), we can always determine what the input(s) were.

An **irreversible gate** is a logic gate where, given the output(s), we **cannot** determine the original inputs.

### Examples

- **Reversible gates**: `NOT`
- **Irreversible gates**: `AND`, `OR`, `XOR`

---

# Reversibility in a More Interesting View

Let $L$ be some logic gate that takes $n$ bits as input and outputs $k < n$ bits.  
Does $L$ always have to be irreversible? And is the converse true?

---

## Theorem

Let $L^n$ be the class of all logic gates that take $n$ bits of input and output $k < n$ bits.  
Then all logic gates $L \in L^n$ are **irreversible**.

---

## More Deep Thoughts

Let's think about $L^{k}$ — the class of logic gates that take $k > n$ input bits and output $n$ bits.

- Are these gates reversible?
- What happens if we allow **probabilistic logic gates**?

---

## A Specific Example (Research Topic)

Consider a dummy gate $L$ which takes $n$ bits as input and returns $n + 1$ bits.  
The extra bit returned is `1` with 90% probability, and `0` with 10% probability.

**Question**: Can we say that $L$ is reversible with high probability?

---

## Example: Is $(A,B) \mapsto (AB, A)$ reversible?

Consider the function:

$f(A, B) = (AB, A)$

| Input | Output |
|-------|---------|
| (0,0) | (0,0)   |
| (0,1) | (0,0)   |
| (1,0) | (0,1)   |
| (1,1) | (1,1)   |

- Notice that inputs $(0,0)$ and $(0,1)$ produce the **same output** $(0,0)$.
- This means the function is **not injective** and thus **not reversible**.

---

### Is it reversible with high probability?

Assuming all inputs are equally likely (uniform distribution):

- For output $(1,1)$, the input must have been $(1,1)$ (100% recoverable).
- For output $(0,1)$, the input must have been $(1,0)$ (100% recoverable).
- For output $(0,0)$, the input could be either $(0,0)$ or $(0,1)$ — so guessing right is 50%.

Probability of correct guess when inverting:

\[
P(\text{correct}) = \frac{1}{4} \times 1 + \frac{1}{4} \times 1 + \frac{2}{4} \times \frac{1}{2} = \frac{3}{4} = 75\%
\]

So the function is **reversible with 75% accuracy** under uniform input distribution, but not truly reversible.

---

# Toffoli Gate (The reversible AND gate)

The **Toffoli gate** is a classic example of a reversible logic gate often called the **controlled-controlled-NOT (CCNOT)** gate. It takes three input bits $(a, b, c)$ and outputs three bits:

$(a, \quad b, \quad c \oplus (a \land b))$

- The first two bits, $a$ and $b$, are passed through unchanged.
- The third bit $c$ is flipped (XORed) **only if** both $a$ and $b$ are 1.

---

### Why is the Toffoli gate reversible?

Because the mapping from inputs to outputs is **bijective** — every output corresponds to exactly one input.

Given outputs $(a', b', c')$, the original inputs are recovered as:

$$
\begin{cases}
a = a' \\
b = b' \\
c = c' \oplus (a \land b)
\end{cases}
$$

---

### The Toffoli gate is its own inverse

Applying the Toffoli gate twice returns the original input:

$T(a,b,c) = (a, b, c \oplus (a \land b))$

Applying $T$ again on the output:

$T(T(a,b,c)) = \bigl(a, b, (c \oplus (a \land b)) \oplus (a \land b)\bigr) = (a, b, c)$

because:

$x \oplus x = 0$ and $x \oplus 0 = x$

Thus,

$\boxed{T = T^{-1}}$

which means the Toffoli gate is **its own inverse** — an involution.

---
### Next up:

## [[Making Irreversible Gates Reversible]]


---
