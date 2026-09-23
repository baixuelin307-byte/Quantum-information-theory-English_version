## Trine-State Strategy: Why Is the Success Probability $7/12$?

Alice wants to send a trit

$$
k \in \{0,1,2\}.
$$

She encodes $k$ into the corresponding trine state

$$
|\phi_k\rangle.
$$

Bob does not know $k$, so he randomly chooses

$$
e \in \{0,1,2\}.
$$

Since the three values are equally likely,

$$
P(e=k)=\frac{1}{3}
$$

and

$$
P(e\neq k)=\frac{2}{3}.
$$

Bob then measures in the basis

$$
\{|\phi_e\rangle,|\phi_e^\perp\rangle\}.
$$

---

### Case 1: $e=k$

This happens with probability

$$
P(e=k)=\frac{1}{3}.
$$

Since

$$
|\phi_k\rangle=|\phi_e\rangle,
$$

Bob obtains the outcome

$$
|\phi_e\rangle
$$

with probability $1$.

He outputs $e$, and because $e=k$, the answer is correct.

Therefore,

$$
P(\text{success}\mid e=k)=1.
$$

The contribution of this case to the total success probability is

$$
\frac{1}{3}\times 1=\frac{1}{3}.
$$

---

### Case 2: $e\neq k$

This happens with probability

$$
P(e\neq k)=\frac{2}{3}.
$$

Two different trine states are separated by

$$
120^\circ.
$$

Therefore, the probability of obtaining the outcome $|\phi_e\rangle$ is

$$
|\langle\phi_e|\phi_k\rangle|^2.
$$

Because

$$
\langle\phi_e|\phi_k\rangle=\cos 120^\circ=-\frac{1}{2},
$$

we get

$$
|\langle\phi_e|\phi_k\rangle|^2
=
\left(-\frac{1}{2}\right)^2
=
\frac{1}{4}.
$$

So,

$$
P(|\phi_e\rangle)=\frac{1}{4}.
$$

If this outcome occurs, Bob outputs $e$.

However,

$$
e\neq k,
$$

so Bob is wrong.

The other possible measurement outcome is

$$
|\phi_e^\perp\rangle.
$$

Its probability is

$$
P(|\phi_e^\perp\rangle)
=
1-\frac{1}{4}
=
\frac{3}{4}.
$$

If Bob gets $|\phi_e^\perp\rangle$, he knows that the true value is not $e$.

There were originally three possibilities,

$$
\{0,1,2\}.
$$

After excluding $e$, only two possibilities remain.

Bob chooses randomly between these two values, so

$$
P(\text{correct guess})=\frac{1}{2}.
$$

Therefore,

$$
P(\text{success}\mid e\neq k)
=
\frac{3}{4}\times\frac{1}{2}
=
\frac{3}{8}.
$$

---

## Total Success Probability

Using the law of total probability,

$$
P(\text{success})
=
P(e=k)P(\text{success}\mid e=k)
+
P(e\neq k)P(\text{success}\mid e\neq k).
$$

Substituting the values,

$$
P(\text{success})
=
\frac{1}{3}\times 1
+
\frac{2}{3}\times\frac{3}{8}.
$$

Therefore,

$$
P(\text{success})
=
\frac{1}{3}
+
\frac{1}{4}.
$$

Thus,

$$
P(\text{success})
=
\frac{7}{12}.
$$

Numerically,

$$
P(\text{success})
\approx 0.583.
$$

---

## Key Point

The factor

$$
\frac{3}{4}
$$

is the probability of obtaining the measurement outcome

$$
|\phi_e^\perp\rangle.
$$

It is not related to the number of possible states.

The factor

$$
\frac{1}{2}
$$

comes from guessing between the two remaining possible values after excluding $e$.

Therefore,

$$
\frac{3}{4}\times\frac{1}{2}
=
\frac{3}{8}.
$$
