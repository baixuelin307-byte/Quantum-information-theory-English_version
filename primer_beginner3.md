# 3.1 Notation for Qubits and Higher-Dimensional Analogues

## Notation for Qubits and Higher-Dimensional Quantum Systems

A qubit state can be represented by the probability-amplitude vector:

`$(\alpha_0,\alpha_1)$`, where `$\alpha_0,\alpha_1\in\mathbb C$` and `$|\alpha_0|^2+|\alpha_1|^2=1$`.

Thus, the vector is a unit vector.

---

## 1. What Is a Ket?

Quantum information normally uses:

$|\psi\rangle$

rather than an ordinary column-vector notation. This is **Dirac (bra-ket) notation**, and `$|\psi\rangle$` is called a **ket**.

For a single qubit:

$|\psi\rangle=\alpha_0|0\rangle+\alpha_1|1\rangle$

This is equivalent to the amplitude vector `$(\alpha_0,\alpha_1)$`, because `$|0\rangle=(1,0)$` and `$|1\rangle=(0,1)$`.

---

## 2. Computational Basis States

`$|0\rangle$` and `$|1\rangle$` are called the **computational basis states**.

A general qubit `$|\psi\rangle=\alpha_0|0\rangle+\alpha_1|1\rangle$` is a superposition of these basis states.

---

## 3. Higher-Dimensional Quantum Systems

For a d-dimensional quantum system:

$|\psi\rangle=(\alpha_0,\alpha_1,\ldots,\alpha_{d-1})$

where `$\alpha_j\in\mathbb C$` and:

$|\alpha_0|^2+|\alpha_1|^2+\cdots+|\alpha_{d-1}|^2=1$.

> The squared magnitudes of all probability amplitudes must sum to 1.

These squared magnitudes are the probabilities of obtaining the corresponding basis states upon measurement.

---

## 4. Unnormalized State Notation

For convenience, a normalization factor is sometimes omitted. For example:

$\frac{1}{\sqrt2}|0\rangle+\frac{1}{\sqrt2}|1\rangle$

may be written informally as `$|0\rangle+|1\rangle$`, with the understanding that this vector is unnormalized.

For a nonzero unnormalized vector `$|\psi\rangle$`, the corresponding normalized quantum state is:

$\frac{|\psi\rangle}{\|\,|\psi\rangle\,\|}$

**unnormalized vector ÷ its norm = valid quantum state**

---

# 3.3 Unitary Operations

## Unitary Operations

Quantum-state evolution is commonly written as:

$|\psi'\rangle=U|\psi\rangle$

where `U` is a unitary matrix.

---

## 1. Core Properties of a Unitary Matrix

### Property 1: Inner Products Are Preserved

If `$|\psi\rangle$` and `$|\phi\rangle$` both undergo `U`, their inner product remains unchanged.

> A unitary operation preserves the geometric relationship between quantum states.

### Property 2: Rows and Columns Are Orthonormal

Every row and column has unit length, and different rows or columns have inner product zero.

### Property 3: Unitarity Condition

$U^\dagger U=I$

Here `$U^\dagger$` is the conjugate transpose and `I` is the identity. Therefore:

$U^{-1}=U^\dagger$

so a unitary operation is reversible.

---

## 2. Common Unitary Operations

- Hadamard gate `H`
- Pauli-X gate
- Pauli-Y gate
- Pauli-Z gate
- rotation gates

### Pauli-X Gate

`$|0\rangle\leftrightarrow|1\rangle$`; this is a **bit flip**.

### Pauli-Z Gate

`$|0\rangle\rightarrow|0\rangle$`, `$|1\rangle\rightarrow-|1\rangle$`; this is a **phase flip**.

---

## 3. Core Interpretation

> **A unitary operation maps a valid quantum state to another valid quantum state while preserving vector lengths and inner products.**

```text
classical information
→ encode as a quantum state
→ unitary evolution U
→ amplitudes and phases change
→ information is transformed but not destroyed
→ measurement
```

Because unitary evolution is reversible, information can in principle be recovered by the inverse operation before measurement.

---

# 3.4 Understanding Quantum Measurement

## A Deeper Understanding of Quantum Measurement

Suppose:

$|\psi\rangle=\alpha_0|0\rangle+\alpha_1|1\rangle$

with `$|\alpha_0|^2+|\alpha_1|^2=1$`.

---

## 1. Before Measurement

Before the final measurement, a quantum algorithm normally applies a sequence of unitary operations. These change probability amplitudes, relative phases, and interference patterns.

> **The usual goal is to make the desired answer more likely to appear in the final measurement.**

---

## 2. Computational-Basis Measurement

Measuring in `{|0⟩,|1⟩}` gives:

- outcome 0 with `$P(0)=|\alpha_0|^2$`, after which the state is `$|0\rangle$`
- outcome 1 with `$P(1)=|\alpha_1|^2$`, after which the state is `$|1\rangle$`

---

## 3. Measurement Collapse

```text
outcome 0: |ψ⟩ → |0⟩
outcome 1: |ψ⟩ → |1⟩
```

This process is commonly called **state collapse**.

---

## 4. Basic Logic of a Quantum Algorithm

```text
input information
→ quantum state
→ unitary operations
→ change amplitudes and phases
→ interference
→ measurement
→ classical result
```

> **A quantum algorithm does not simply turn a quantum state into 0 or 1 at the beginning. It first adjusts amplitudes and phases so that the correct answer is more likely to be obtained at the final measurement.**

---

## 5. Most Important Interpretation

```text
adjust probability amplitudes
+ adjust relative phases
+ use interference
↓
increase the measurement probability of the target answer
```

The classical result appears only at measurement.

---

# One-Sentence Summary

### Qubit Representation

$|\psi\rangle=\alpha_0|0\rangle+\alpha_1|1\rangle$

### Unitary Evolution

$|\psi'\rangle=U|\psi\rangle$

### Measurement

$P(0)=|\alpha_0|^2$, `$P(1)=|\alpha_1|^2$`

### Overall Process

`quantum state → unitary evolution → interference → measurement → classical result`

> **Before measurement, unitary operations change the amplitudes and phases of a quantum state. At measurement, the squared magnitudes of the amplitudes determine the probabilities of the classical outcomes.**

