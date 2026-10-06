# 9. Isometries and Exotic Measurements

Unitary operations are fundamental in quantum information processing.

However, quantum information also allows operations that are more general than unitary operations.

A simple example is:

```text
Input:  one qubit

Output: the original qubit + one additional qubit
```

Suppose the input qubit is

```math
|\psi\rangle
```

and we prepare another qubit in the fixed state

```math
|0\rangle.
```

Then the operation is

```math
|\psi\rangle
\mapsto
|\psi\rangle\otimes|0\rangle.
```

The original qubit remains unchanged.

The second qubit is a new qubit that we deliberately prepare in the known state

```math
|0\rangle.
```

Therefore:

```text
First qubit  = original quantum state

Second qubit = fixed known state |0⟩
```

This type of additional qubit is often called an **ancilla qubit**.

---

##  Example

Suppose

```math
|\psi\rangle
=
\alpha|0\rangle+\beta|1\rangle.
```

Then adding an ancilla qubit in state

```math
|0\rangle
```

gives

```math
|\psi\rangle\otimes|0\rangle
=
\left(
\alpha|0\rangle+\beta|1\rangle
\right)
\otimes|0\rangle.
```

Therefore,

```math
|\psi\rangle\otimes|0\rangle
=
\alpha|00\rangle+\beta|10\rangle.
```

So the mapping is

```text
α|0⟩ + β|1⟩

        ↓

α|00⟩ + β|10⟩
```

The original quantum information is preserved.

We have only enlarged the quantum system by adding a known qubit.

---

## Vector Representation

The original state can be written as

```math
|\psi\rangle
=
\begin{bmatrix}
\alpha\\
\beta
\end{bmatrix}.
```

After adding the qubit

```math
|0\rangle,
```

the state becomes

```math
|\psi\rangle\otimes|0\rangle
=
\begin{bmatrix}
\alpha\\
0\\
\beta\\
0
\end{bmatrix}.
```

Therefore, the dimension changes from

```text
2-dimensional state vector
```

to

```text
4-dimensional state vector.
```

This corresponds to

```text
1 qubit  →  2 qubits
```

because

```math
2^1=2
```

and

```math
2^2=4.
```

---

##  Matrix Representation

The operation can be represented by the matrix

```math
V
=
\begin{bmatrix}
1&0\\
0&0\\
0&1\\
0&0
\end{bmatrix}.
```

Then

```math
V
\begin{bmatrix}
\alpha\\
\beta
\end{bmatrix}
=
\begin{bmatrix}
\alpha\\
0\\
\beta\\
0
\end{bmatrix}.
```

Therefore,

```math
V|\psi\rangle
=
|\psi\rangle\otimes|0\rangle.
```

The matrix

```math
V
```

has size

```text
4 × 2.
```

So it maps a vector from a 2-dimensional space into a 4-dimensional space.

---

##  Why Is This Not a Unitary Matrix?

A unitary matrix must be square.

For example:

```text
2 × 2

4 × 4

8 × 8
```

A unitary operation normally maps a Hilbert space to another Hilbert space of the same dimension.

For example:

```text
2 dimensions → 2 dimensions

4 dimensions → 4 dimensions
```

However, the matrix

```math
V
=
\begin{bmatrix}
1&0\\
0&0\\
0&1\\
0&0
\end{bmatrix}
```

has size

```text
4 × 2.
```

Therefore, it is not a unitary matrix.

Instead, it is an **isometry**.

---

#  What Is an Isometry?

An isometry is a linear transformation that preserves inner products.

For an isometry

```math
V,
```

we have

```math
V^\dagger V=I.
```

For the previous example,

```math
V
=
\begin{bmatrix}
1&0\\
0&0\\
0&1\\
0&0
\end{bmatrix}.
```

Its conjugate transpose is

```math
V^\dagger
=
\begin{bmatrix}
1&0&0&0\\
0&0&1&0
\end{bmatrix}.
```

Therefore,

```math
V^\dagger V
=
\begin{bmatrix}
1&0\\
0&1
\end{bmatrix}
=
I.
```

So

```math
V
```

is an isometry.

---

##  Unitary vs. Isometry

The main difference can be summarized as:

```text
Unitary operation:

same dimension
      ↓
same dimension
```

while

```text
Isometry:

smaller dimension
      ↓
larger dimension
```

For example,

```math
|\psi\rangle
\mapsto
|\psi\rangle\otimes|0\rangle
```

maps

```text
1 qubit
```

to

```text
2 qubits.
```

The important point is that the original quantum information is preserved.

---

##  Important Intuition

An isometry can be understood as embedding a smaller quantum system into a larger quantum system.

For example:

```text
Original system:

|ψ⟩
```

becomes

```text
Larger system:

|ψ⟩ ⊗ |0⟩
```

The original state is not destroyed.

Instead, we add an additional known quantum system.

Therefore:

```text
Isometry
=
preserve the original quantum information
+
embed it into a larger Hilbert space
```

---

##  Question: Is the Second Qubit a Fixed Value?

For the mapping

```math
|\psi\rangle
\mapsto
|\psi\rangle\otimes|0\rangle,
```

is the second qubit fixed and known?

**Yes.**

The second qubit is deliberately prepared in the state

```math
|0\rangle.
```

It is not random.

It is not an unknown quantum state.

For example, if

```math
|\psi\rangle
=
\alpha|0\rangle+\beta|1\rangle,
```

then

```math
|\psi\rangle\otimes|0\rangle
=
\alpha|00\rangle+\beta|10\rangle.
```

Therefore:

```text
First qubit:

arbitrary / unknown state |ψ⟩

Second qubit:

known fixed state |0⟩
```

So we can think of the operation as

```text
original unknown qubit

+

known fixed ancilla qubit |0⟩
```

The purpose is **not** to copy the unknown qubit.

The operation does not produce

```math
|\psi\rangle\otimes|\psi\rangle.
```

Instead, it produces

```math
|\psi\rangle\otimes|0\rangle.
```

So we are simply adding a new known qubit to enlarge the quantum system.

---

##  Why Is This Useful?

Isometries are useful because they allow us to introduce auxiliary quantum systems.

These auxiliary systems can later interact with the original system through unitary operations.

This idea is important for constructing more general quantum operations and more general quantum measurements.

Therefore:

```text
Add ancilla qubits
        ↓
Apply larger quantum operations
        ↓
Perform measurements
        ↓
Obtain more general measurement procedures
```

This is why isometries are closely related to the next topic:

```text
exotic / generalized quantum measurements.
```

---

##  Key Idea

The main idea of this section is:

```text
Unitary operations are not the only valid operations in quantum information.
```

An isometry can enlarge the quantum system while preserving the original quantum information.

The basic example is

```math
|\psi\rangle
\mapsto
|\psi\rangle\otimes|0\rangle.
```

Here,

```text
|ψ⟩ = original quantum state

|0⟩ = known fixed ancilla qubit
```

and

```math
V^\dagger V=I.
```

So:

```text
Unitary:

same Hilbert-space dimension


Isometry:

smaller Hilbert space
        ↓
larger Hilbert space
```

The next step is to use these isometries to construct more general forms of quantum measurement.
