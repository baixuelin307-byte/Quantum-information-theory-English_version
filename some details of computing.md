### Trine-State Strategy: Why Is the Success Probability $7/12$?

Alice wants to send a trit:

```math
k \in \{0,1,2\}
```

She encodes $k$ into the corresponding trine state:

```math
|\phi_k\rangle
```

Bob does not know $k$, so he randomly chooses:

```math
e \in \{0,1,2\}
```

Since the three values are equally likely:

```math
P(e=k)=\frac{1}{3}
```

and

```math
P(e\neq k)=\frac{2}{3}
```

Bob then measures in the basis:

```math
\{|\phi_e\rangle,\ |\phi_e^\perp\rangle\}
```

---

### Case 1: $e=k$

This happens with probability:

```math
P(e=k)=\frac{1}{3}
```

In this case, the received state is exactly:

```math
|\phi_k\rangle=|\phi_e\rangle
```

Therefore, Bob obtains the measurement outcome:

```math
|\phi_e\rangle
```

with probability 1.

Bob then outputs $e$.

Since:

```math
e=k
```

his answer is correct.

Therefore:

```math
P(\text{success}\mid e=k)=1
```

The contribution of this case to the total success probability is:

```math
\frac{1}{3}\times 1=\frac{1}{3}
```

---

### Case 2: $e\neq k$

This happens with probability:

```math
P(e\neq k)=\frac{2}{3}
```

Any two different trine states are separated by:

```math
120^\circ
```

Therefore, the overlap between the true state $|\phi_k\rangle$ and the measurement state $|\phi_e\rangle$ is:

```math
|\langle \phi_e|\phi_k\rangle|^2
=
\cos^2 120^\circ
=
\left(-\frac{1}{2}\right)^2
=
\frac{1}{4}
```

So the probability of obtaining the measurement outcome:

```math
|\phi_e\rangle
```

is:

```math
\frac{1}{4}
```

If this happens, Bob outputs $e$.

However:

```math
e\neq k
```

so Bob's answer is incorrect.

---

The other possible measurement outcome is:

```math
|\phi_e^\perp\rangle
```

Its probability is:

```math
1-\frac{1}{4}
=
\frac{3}{4}
```

When Bob obtains $|\phi_e^\perp\rangle$, he knows that the true value is not $e$:

```math
k\neq e
```

Originally, there are three possible values:

```math
\{0,1,2\}
```

After excluding $e$, only two possible values remain.

Bob randomly guesses between these two remaining values.

Therefore:

```math
P(\text{correct guess})=\frac{1}{2}
```

Thus, when $e\neq k$, the success probability is:

```math
P(\text{success}\mid e\neq k)
=
\frac{3}{4}\times\frac{1}{2}
=
\frac{3}{8}
```

---

## Total Success Probability

There are two possible cases:

```text
Case 1: e = k
Probability = 1/3
Success probability = 1

Case 2: e ≠ k
Probability = 2/3
Success probability = 3/8
```

Using the law of total probability:

```math
P(\text{success})
=
P(e=k)P(\text{success}\mid e=k)
+
P(e\neq k)P(\text{success}\mid e\neq k)
```

Substituting the values:

```math
P(\text{success})
=
\frac{1}{3}\times 1
+
\frac{2}{3}\times\frac{3}{8}
```

Therefore:

```math
P(\text{success})
=
\frac{1}{3}
+
\frac{1}{4}
```

Hence:

```math
P(\text{success})
=
\frac{7}{12}
```

Numerically:

```math
P(\text{success})
\approx 0.583
```

So the final success probability is:

```math
\boxed{
P(\text{success})=\frac{7}{12}\approx 0.583
}
```

---

## Key Point

The factor:

```math
\frac{3}{4}
```

is the probability of obtaining the measurement outcome:

```math
|\phi_e^\perp\rangle
```

It does **not** mean that there are four possible states.

The reason is that, when $e\neq k$:

```math
P(|\phi_e\rangle)
=
|\langle\phi_e|\phi_k\rangle|^2
=
\frac{1}{4}
```

Therefore:

```math
P(|\phi_e^\perp\rangle)
=
1-\frac{1}{4}
=
\frac{3}{4}
```

The factor:

```math
\frac{1}{2}
```

comes from the fact that after excluding $e$, only two possible values remain.

Bob randomly chooses between these two values, so:

```math
P(\text{correct guess})=\frac{1}{2}
```

Therefore:

```math
\frac{3}{4}\times\frac{1}{2}
=
\frac{3}{8}
```

So:

```math
P(\text{success}\mid e\neq k)=\frac{3}{8}
```

and finally:

```math
P(\text{success})
=
\frac{1}{3}
+
\frac{2}{3}\times\frac{3}{8}
=
\frac{7}{12}
```
