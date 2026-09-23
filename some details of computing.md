## Trine-State Strategy: Why Is the Success Probability $7/12$?

Alice wants to send:

$$
k \in \{0,1,2\}
$$

She encodes $k$ into the corresponding trine state:

$$
|\phi_k\rangle
$$

Bob does not know $k$, so he first randomly chooses:

$$
e \in \{0,1,2\}
$$

Since the three values are equally likely,

$$
P(e=k)=\frac{1}{3}
$$

and

$$
P(e\neq k)=\frac{2}{3}.
$$

Bob then measures using the basis:

$$
\boxed{\{|\phi_e\rangle,\ |\phi_e^\perp\rangle\}}
$$

---

### Case 1: $e=k$

The probability of this case is:

$$
P(e=k)=\frac{1}{3}.
$$

The received state is exactly:

$$
|\phi_k\rangle = |\phi_e\rangle.
$$

Therefore, Bob obtains the measurement outcome:

$$
|\phi_e\rangle
$$

with probability $1$.

He then outputs:

$$
e=k.
$$

Thus,

$$
\boxed{P(\text{success}\mid e=k)=1}
$$

and the contribution of this case to the total success probability is:

$$
\frac{1}{3}\times 1=\frac{1}{3}.
$$

---

### Case 2: $e\neq k$

The probability of this case is:

$$
P(e\neq k)=\frac{2}{3}.
$$

Any two different trine states are separated by:

$$
120^\circ.
$$

Therefore, the overlap between the true state $|\phi_k\rangle$ and $|\phi_e\rangle$ is:

$$
|\langle \phi_e|\phi_k\rangle|^2
=
\cos^2 120^\circ
=
\left(-\frac{1}{2}\right)^2
=
\frac{1}{4}.
$$

So the probability of obtaining the measurement outcome:

$$
|\phi_e\rangle
$$

is:

$$
\frac{1}{4}.
$$

If this happens, Bob outputs $e$, but since:

$$
e\neq k,
$$

this answer is incorrect.

---

Therefore, the probability of obtaining the other measurement outcome:

$$
|\phi_e^\perp\rangle
$$

is:

$$
1-\frac{1}{4}=\frac{3}{4}.
$$

When Bob obtains $|\phi_e^\perp\rangle$, he knows that:

$$
k\neq e.
$$

Originally, there are three possible values:

$$
\{0,1,2\}.
$$

After excluding $e$, only two possible values remain.

Bob randomly guesses between these two values, so:

$$
P(\text{correct guess})=\frac{1}{2}.
$$

Therefore,

$$
\boxed{
P(\text{success}\mid e\neq k)
=
\frac{3}{4}\times\frac{1}{2}
=
\frac{3}{8}
}
$$

---

## Total Success Probability

Using the law of total probability:

$$
P(\text{success})
=
P(e=k)P(\text{success}\mid e=k)
+
P(e\neq k)P(\text{success}\mid e\neq k).
$$

Substituting the values:

$$
P(\text{success})
=
\frac{1}{3}\times 1
+
\frac{2}{3}\times\frac{3}{8}.
$$

Therefore,

$$
=
\frac{1}{3}
+
\frac{1}{4}
$$

and hence:

$$
=
\boxed{\frac{7}{12}}.
$$

Thus,

$$
\boxed{
P(\text{success})
=
\frac{7}{12}
\approx 0.583
}
$$

---

## Key Point

The factor

$$
\boxed{
\frac{3}{4}
}
$$

is the probability of obtaining the measurement outcome:

$$
|\phi_e^\perp\rangle.
$$

It does **not** mean that there are four possible states.

The factor

$$
\boxed{
\frac{1}{2}
}
$$

comes from the fact that, after excluding $e$, Bob must guess between the remaining two possible values.

Therefore,

$$
\boxed{
\frac{3}{4}\times\frac{1}{2}
=
\frac{3}{8}
}
$$
