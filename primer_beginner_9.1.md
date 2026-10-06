# 11. Isometry vs. Unitary Operation

An **isometry** and a **unitary operation** are closely related, but they are not exactly the same.

The main difference is the dimension of the input and output spaces.

---

## 11.1 Unitary Operation

A unitary operation is represented by a square matrix

```math
U.
```

It satisfies

```math
U^\dagger U
=
UU^\dagger
=
I.
```

A unitary operation maps a Hilbert space to another Hilbert space of the same dimension.

For example:

```text
2 dimensions → 2 dimensions

4 dimensions → 4 dimensions
```

So a unitary operation has the form

```text
same dimension
      ↓
      U
      ↓
same dimension
```

A unitary operation is fully reversible.

For example,

```math
U^{-1}
=
U^\dagger.
```

A simple example is the Pauli-X gate:

```math
X
=
\begin{bmatrix}
0&1\\
1&0
\end{bmatrix}.
```

It is a

```text
2 × 2
```

matrix, and it satisfies

```math
X^\dagger X
=
XX^\dagger
=
I.
```

Therefore, the Pauli-X gate is unitary.

---

## 11.2 Isometry

An isometry is an

```text
m × n
```

matrix

```math
V
```

that satisfies

```math
V^\dagger V
=
I.
```

Usually,

```math
m\geq n.
```

This means that an isometry can map a smaller Hilbert space into a larger Hilbert space.

For example:

```text
2 dimensions → 3 dimensions

2 dimensions → 4 dimensions
```

So an isometry can have the form

```text
smaller dimension
       ↓
       V
       ↓
larger dimension
```

The important point is that the original quantum information is preserved.

---

## 11.3 Example of an Isometry

Consider

```math
V
=
\begin{bmatrix}
1&0\\
0&1\\
0&0
\end{bmatrix}.
```

This is a

```text
3 × 2
```

matrix.

Suppose the input state is

```math
|\psi\rangle
=
\alpha_0|0\rangle
+
\alpha_1|1\rangle.
```

In vector form,

```math
|\psi\rangle
=
\begin{bmatrix}
\alpha_0\\
\alpha_1
\end{bmatrix}.
```

Applying the isometry gives

```math
V|\psi\rangle
=
\begin{bmatrix}
1&0\\
0&1\\
0&0
\end{bmatrix}
\begin{bmatrix}
\alpha_0\\
\alpha_1
\end{bmatrix}
=
\begin{bmatrix}
\alpha_0\\
\alpha_1\\
0
\end{bmatrix}.
```

So the process is

```text
2-dimensional state
        ↓
        V
        ↓
3-dimensional state
```

The original amplitudes

```text
α₀ and α₁
```

are preserved.

---

## 11.4 Why Is This Not Unitary?

The matrix

```math
V
=
\begin{bmatrix}
1&0\\
0&1\\
0&0
\end{bmatrix}
```

is not square.

It has size

```text
3 × 2.
```

Therefore, it cannot be a unitary matrix.

However, it satisfies

```math
V^\dagger V
=
I.
```

So it is an isometry.

---

## 11.5 Connection with Adding an Ancilla Qubit

Another important example of an isometry is

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

If

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

In vector form,

```math
\begin{bmatrix}
\alpha\\
\beta
\end{bmatrix}
\mapsto
\begin{bmatrix}
\alpha\\
0\\
\beta\\
0
\end{bmatrix}.
```

So this is a mapping from

```text
2 dimensions
```

to

```text
4 dimensions.
```

This is an isometry because the original quantum information is preserved while the state is embedded into a larger Hilbert space.

---

## 11.6 Main Difference

The main difference can be summarized as follows:

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

For a unitary matrix,

```math
U^\dagger U
=
UU^\dagger
=
I.
```

For an isometry,

```math
V^\dagger V
=
I.
```

But in general,

```math
VV^\dagger
\neq
I.
```

because \(V\) does not have to be square.

---

## 11.7 Relationship Between Them

If an isometry has

```math
m=n,
```

then it is square.

In this case,

```math
V^\dagger V
=
I
```

implies that \(V\) is unitary.

Therefore,

```text
Every unitary operation is an isometry.
```

But:

```text
Not every isometry is unitary.
```

So the relationship is

```text
Unitary
⊂
Isometry
```

A unitary operation is a special case of an isometry.

---

## 11.8 Key Intuition

You can remember the difference as:

```text
Unitary:

rearrange / transform quantum information
inside the same-size Hilbert space
```

while

```text
Isometry:

embed quantum information
into a larger Hilbert space
```

Both preserve inner products and quantum information.

The key mathematical conditions are

```math
U^\dagger U
=
UU^\dagger
=
I
```

for a unitary operation, and

```math
V^\dagger V
=
I
```

for an isometry.

The most important conclusion is:

```text
Every unitary is an isometry,
but not every isometry is unitary.
```
