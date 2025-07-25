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

## A Specific Example

Consider a dummy gate $L$ which takes $n$ bits as input and returns $n + 1$ bits.  
The extra bit returned is `1` with 90% probability, and `0` with 10% probability.

**Question**: Can we say that $L$ is reversible with high probability?
