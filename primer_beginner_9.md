
## 9. Isometries and Exotic Measurements

Unitary operations are fundamental in quantum information, but more general operations are also allowed.

A simple example is adding a new qubit in a fixed state.

Suppose the input is

\[
|\psi\rangle
\]

and we add an extra qubit initialized to

\[
|0\rangle.
\]

The operation is

\[
|\psi\rangle
\mapsto
|\psi\rangle \otimes |0\rangle.
\]

The first qubit remains unchanged, while the second qubit is a known and fixed ancilla qubit.

If

\[
|\psi\rangle
=
\alpha|0\rangle+\beta|1\rangle,
\]

then

\[
|\psi\rangle\otimes|0\rangle
=
\alpha|00\rangle+\beta|10\rangle.
\]

In vector form,

\[
|\psi\rangle
=
\begin{bmatrix}
\alpha\\
\beta
\end{bmatrix}
\]

is mapped to

\[
|\psi\rangle\otimes|0\rangle
=
\begin{bmatrix}
\alpha\\
0\\
\beta\\
0
\end{bmatrix}.
\]

This mapping can be written as

\[
V=
\begin{bmatrix}
1&0\\
0&0\\
0&1\\
0&0
\end{bmatrix}.
\]

Therefore,

\[
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
\]

The matrix \(V\) is not unitary because it is a \(4\times2\) matrix rather than a square matrix.

Instead, it is an **isometry**, satisfying

\[
V^\dagger V = I.
\]

An isometry can map a smaller Hilbert space into a larger Hilbert space while preserving the quantum information.

### Unitary vs. Isometry

A unitary operation maps between spaces of the same dimension:

\[
\text{Unitary: same dimension}
\rightarrow
\text{same dimension}.
\]

An isometry can map a smaller space into a larger space:

\[
\text{Isometry: smaller dimension}
\rightarrow
\text{larger dimension}.
\]

In this example,

\[
\boxed{
|\psi\rangle
\rightarrow
|\psi\rangle\otimes|0\rangle
}
\]

means that the original qubit is preserved and a new qubit in the state \(|0\rangle\) is added.

This extra qubit is often called an **ancilla qubit**.

Isometries will later be used to construct more general types of quantum measurements.

---

### Question: Is the second qubit a fixed value?

For the mapping

\[
|\psi\rangle
\mapsto
|\psi\rangle\otimes|0\rangle,
\]

is the second qubit fixed and known?

**Yes.**

The second qubit is deliberately prepared in the fixed state

\[
|0\rangle.
\]

It is not random and it is not an unknown quantum state.

If

\[
|\psi\rangle
=
\alpha|0\rangle+\beta|1\rangle,
\]

then

\[
|\psi\rangle\otimes|0\rangle
=
\alpha|00\rangle+\beta|10\rangle.
\]

The original qubit can still be in an arbitrary state \(|\psi\rangle\), but the newly added qubit is always initialized as

\[
|0\rangle.
\]

So we can think of the operation as

\[
\boxed{
\text{original unknown qubit}
+
\text{known fixed ancilla }|0\rangle
}
\]

The purpose is not to copy the unknown qubit. It is simply to enlarge the quantum system by adding a known auxiliary qubit.
