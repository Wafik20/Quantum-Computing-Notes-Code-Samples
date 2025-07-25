
Given any irreversible function $f: \{0,1\}^n \rightarrow \{0,1\}^k$, we can construct a **reversible** version of it using the following strategy:

### General Strategy

We define a new function:

$$
R_f(x, y) = (x, y \oplus f(x))
$$

Where:
- $x$ is the original $n$-bit input,
- $y$ is a $k$-bit auxiliary input (typically initialized to $0^k$),
- $\oplus$ is bitwise XOR.

This mapping is **bijective** over $\{0,1\}^{n+k}$:
- The original input $x$ is preserved.
- The output is embedded into $y$ using XOR, which is self-inverting.

### Why XOR?

XOR is used because of its reversible property:

$$
(a \oplus b) \oplus b = a
$$

This means applying $R_f$ twice undoes itself:

1. Forward: $(x, 0^k) \mapsto (x, f(x))$
2. Reverse: $(x, f(x)) \mapsto (x, 0^k)$

So we avoid overwriting any input and maintain reversibility.

---
