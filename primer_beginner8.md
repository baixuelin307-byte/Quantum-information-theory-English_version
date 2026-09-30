# 8. Projective and Local Measurements

This chapter introduces **projective measurement**, **local measurement**, and how measurements behave in multi-qubit and entangled systems.

---

## 8.1 Projective Measurement

A projective measurement does not always need to distinguish every basis state individually.

Instead, it can determine **which subspace the quantum state belongs to**.

For example, consider a qutrit:

$$
|\psi\rangle
=
\alpha_0|0\rangle
+
\alpha_1|1\rangle
+
\alpha_2|2\rangle
$$

with

$$
|\alpha_0|^2
+
|\alpha_1|^2
+
|\alpha_2|^2
=
1
$$

A normal computational-basis measurement distinguishes

$$
|0\rangle,\quad |1\rangle,\quad |2\rangle
$$

But we can instead divide the space into two subspaces.

The first subspace is

$$
\mathrm{span}\{|0\rangle,|1\rangle\}
$$

and the second subspace is

$$
\mathrm{span}\{|2\rangle\}
$$

Therefore, the measurement has only two possible outcomes.

---

### Projectors

The projector onto the first subspace is

$$
\Pi_{\mathrm{plane}}
=
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 0
\end{bmatrix}
$$

Applying it to the state gives

$$
\Pi_{\mathrm{plane}}|\psi\rangle
=
\alpha_0|0\rangle
+
\alpha_1|1\rangle
$$

The projector onto the second subspace is

$$
\Pi_{\mathrm{line}}
=
\begin{bmatrix}
0 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$

Applying it gives

$$
\Pi_{\mathrm{line}}|\psi\rangle
=
\alpha_2|2\rangle
$$

The probabilities are

$$
P(\mathrm{plane})
=
|\alpha_0|^2
+
|\alpha_1|^2
$$

and

$$
P(\mathrm{line})
=
|\alpha_2|^2
$$

---

### Properties of a Projector

An orthogonal projector $\Pi$ satisfies

$$
\Pi^\dagger=\Pi
$$

and

$$
\Pi^2=\Pi
$$

Here, $\Pi^\dagger$ is the **conjugate transpose** of $\Pi$.

The condition

$$
\Pi^\dagger=\Pi
$$

means that $\Pi$ is Hermitian.

The condition

$$
\Pi^2=\Pi
$$

means that projecting twice gives the same result as projecting once.

A complete projective measurement satisfies

$$
\sum_k \Pi_k=I
$$

---

### Measurement Probability

For a state $|\psi\rangle$, the probability of obtaining outcome $k$ is

$$
P(k)
=
\langle\psi|\Pi_k|\psi\rangle
$$

After obtaining outcome $k$, the state becomes

$$
\frac{\Pi_k|\psi\rangle}
{\sqrt{\langle\psi|\Pi_k|\psi\rangle}}
$$

The denominator normalizes the state.

---

## 8.2 Local Measurement

A **local measurement** means measuring only part of a multi-qubit system.

Consider a two-qubit state

$$
|\psi\rangle
=
\alpha_{00}|00\rangle
+
\alpha_{01}|01\rangle
+
\alpha_{10}|10\rangle
+
\alpha_{11}|11\rangle
$$

Suppose we measure only the **first qubit**.

---

### First Qubit = 0

If the first qubit is measured as $0$, the state is projected onto

$$
\mathrm{span}\{|00\rangle,|01\rangle\}
$$

The unnormalized state becomes

$$
\alpha_{00}|00\rangle
+
\alpha_{01}|01\rangle
$$

The probability is

$$
P(0)
=
|\alpha_{00}|^2
+
|\alpha_{01}|^2
$$

---

### First Qubit = 1

If the first qubit is measured as $1$, the state is projected onto

$$
\mathrm{span}\{|10\rangle,|11\rangle\}
$$

The unnormalized state becomes

$$
\alpha_{10}|10\rangle
+
\alpha_{11}|11\rangle
$$

The probability is

$$
P(1)
=
|\alpha_{10}|^2
+
|\alpha_{11}|^2
$$

---

### Local Measurement Projectors

Measuring the first qubit is described by

$$
\Pi_0
=
|0\rangle\langle0|
\otimes I
$$

and

$$
\Pi_1
=
|1\rangle\langle1|
\otimes I
$$

The identity $I$ means that the second qubit is **not measured**.

So we can understand local measurement as

$$
\text{measurement on first qubit}
=
\text{projector on first qubit}
\otimes
I
$$

---

### Measuring Part of a Larger System

Suppose we have four qubits and only measure the second and third qubits.

For example,

$$
I
\otimes
|0\rangle\langle0|
\otimes
|0\rangle\langle0|
\otimes
I
$$

means

```text
Qubit 1: not measured → I
Qubit 2: measured     → |0><0|
Qubit 3: measured     → |0><0|
Qubit 4: not measured → I
```

General rule:

- measured qubit → use a projector such as $|0\rangle\langle0|$ or $|1\rangle\langle1|$
- unmeasured qubit → use $I$

---

### Product States and Local Measurement

Suppose the state is separable:

$$
|\psi\rangle\otimes|\phi\rangle
$$

If we measure only the first qubit, the second state $|\phi\rangle$ remains unchanged.

For an entangled state, measuring one qubit can change the **joint state** of the whole system.

---

## 8.3 Order of Local Measurements

Consider

$$
|\psi\rangle
=
\alpha_{00}|00\rangle
+
\alpha_{01}|01\rangle
+
\alpha_{10}|10\rangle
+
\alpha_{11}|11\rangle
$$

The joint measurement probabilities are

$$
P(00)=|\alpha_{00}|^2
$$

$$
P(01)=|\alpha_{01}|^2
$$

$$
P(10)=|\alpha_{10}|^2
$$

$$
P(11)=|\alpha_{11}|^2
$$

Alice's probability of measuring $0$ is

$$
P(A=0)
=
|\alpha_{00}|^2
+
|\alpha_{01}|^2
$$

Bob's probability of measuring $0$ is

$$
P(B=0)
=
|\alpha_{00}|^2
+
|\alpha_{10}|^2
$$

For local measurements on different qubits, the measurement order does not change the final joint statistics.

```text
Alice measures first
        =
Bob measures first
        =
both measure simultaneously
```

---

### Local Operations Cannot Change the Other Side's Measurement Probabilities

The state can be rewritten as

$$
|\psi\rangle
=
\beta_0|0\rangle
\otimes
(\gamma_0|0\rangle+\gamma_1|1\rangle)
+
\beta_1|1\rangle
\otimes
(\delta_0|0\rangle+\delta_1|1\rangle)
$$

where

$$
|\beta_0|^2
=
|\alpha_{00}|^2
+
|\alpha_{01}|^2
$$

and

$$
|\beta_1|^2
=
|\alpha_{10}|^2
+
|\alpha_{11}|^2
$$

Therefore,

$$
P(A=0)=|\beta_0|^2
$$

and

$$
P(A=1)=|\beta_1|^2
$$

Now suppose Bob applies a unitary operation $U$ only to his qubit.

The state becomes

$$
\beta_0|0\rangle
\otimes
U(\gamma_0|0\rangle+\gamma_1|1\rangle)
+
\beta_1|1\rangle
\otimes
U(\delta_0|0\rangle+\delta_1|1\rangle)
$$

The coefficients $\beta_0$ and $\beta_1$ do not change.

Therefore,

$$
P(A=0)=|\beta_0|^2
$$

and

$$
P(A=1)=|\beta_1|^2
$$

remain unchanged.

So Bob cannot change Alice's local measurement probabilities simply by applying a local unitary to his own qubit.

---

## 8.4 Bell Basis Encoding

Two classical bits can be represented using the computational basis:

$$
00\rightarrow|00\rangle
$$

$$
01\rightarrow|01\rangle
$$

$$
10\rightarrow|10\rangle
$$

$$
11\rightarrow|11\rangle
$$

If Alice holds the first qubit, measuring it directly reveals the first classical bit.

---

### Encoding with the Bell Basis

The same two classical bits can instead be encoded using the four Bell states:

$$
00
\rightarrow
\frac{|00\rangle+|11\rangle}{\sqrt{2}}
$$

$$
01
\rightarrow
\frac{|00\rangle-|11\rangle}{\sqrt{2}}
$$

$$
10
\rightarrow
\frac{|01\rangle+|10\rangle}{\sqrt{2}}
$$

$$
11
\rightarrow
\frac{|01\rangle-|10\rangle}{\sqrt{2}}
$$

The important difference is:

> In Bell-basis encoding, the information is stored in the relationship between the two qubits, not in either qubit individually.

---

### Looking at Only One Qubit

Consider

$$
|\Phi^+\rangle
=
\frac{|00\rangle+|11\rangle}{\sqrt{2}}
$$

If Alice measures only the first qubit,

$$
P(0)=\frac{1}{2}
$$

and

$$
P(1)=\frac{1}{2}
$$

Now consider

$$
|\Phi^-\rangle
=
\frac{|00\rangle-|11\rangle}{\sqrt{2}}
$$

Again,

$$
P(0)=\frac{1}{2}
$$

and

$$
P(1)=\frac{1}{2}
$$

The same is true for all four Bell states.

Therefore, Alice cannot determine which Bell state she has by measuring only one qubit.

The information is stored in the **joint two-qubit state**.

---

### Local Operations Can Change Bell-Basis Information

Although Alice cannot read the encoded two bits from one qubit, she can change the Bell state by applying local gates.

Using the encoding above:

- $X$ changes the first encoded bit
- $Z$ changes the second encoded bit
- $XZ$ changes both encoded bits

For example,

$$
|\Phi^+\rangle
\xrightarrow{X}
|\Psi^+\rangle
$$

This property is the key idea behind **superdense coding**.

---

## 8.5 Measuring the Control Qubit of a Controlled-$U$

Consider a controlled-$U$ operation:

```text
control ──●──
          │
target  ──U──
```

Suppose the control qubit is measured in the computational basis.

There are two equivalent ways to think about the process.

### Method 1

```text
Controlled-U
     ↓
measure control
```

### Method 2

```text
measure control
     ↓
control = 0 → do nothing
control = 1 → apply U
```

If the control qubit is measured as $0$, then $U$ is not applied.

If the control qubit is measured as $1$, then $U$ is applied.

Therefore, when the control qubit is measured in the computational basis,

$$
\text{measure before controlled-}U
\equiv
\text{measure after controlled-}U
$$

This equivalence depends on using the **computational basis**.

---

# Key Ideas

1. A projective measurement determines which subspace a quantum state belongs to.

2. An orthogonal projector satisfies

$$
\Pi^\dagger=\Pi
$$

and

$$
\Pi^2=\Pi
$$

3. Measurement probability is

$$
P(k)
=
\langle\psi|\Pi_k|\psi\rangle
$$

4. Local measurement measures only selected qubits.

5. Unmeasured qubits are represented by the identity operator $I$.

6. Measuring one qubit projects the entire joint state into the corresponding subspace.

7. Local operations on Bob's qubit cannot change Alice's local measurement probabilities.

8. Bell-basis information is stored in the joint relationship between two qubits.

9. One qubit alone cannot reveal which Bell state was encoded.

10. Measuring the control qubit of a controlled-$U$ in the computational basis can be moved before or after the controlled operation.
