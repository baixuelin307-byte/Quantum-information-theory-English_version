# 8. Projective and Local Measurements

## 1. Projective Measurement

A projective measurement does not always distinguish every basis state individually.

Instead, it can determine **which subspace the quantum state is projected onto**.

Consider a qutrit:

```text
|ψ> = α0|0> + α1|1> + α2|2>
```

with

```text
|α0|² + |α1|² + |α2|² = 1
```

A normal computational-basis measurement distinguishes:

```text
|0>, |1>, |2>
```

A projective measurement can instead divide the space into larger subspaces.

For example:

```text
plane = span{|0>, |1>}
line  = span{|2>}
```

Then the measurement has only two possible outcomes:

```text
plane
or
line
```

> A projective measurement tells us which subspace the state falls into.

---

## 2. Projectors

The projector onto the plane `span{|0>,|1>}` is:

```text
Πplane =

[1 0 0
 0 1 0
 0 0 0]
```

Applying it to the state gives:

```text
Πplane|ψ> = α0|0> + α1|1>
```

The projector onto `span{|2>}` is:

```text
Πline =

[0 0 0
 0 0 0
 0 0 1]
```

Applying it gives:

```text
Πline|ψ> = α2|2>
```

The probabilities are:

```text
P(plane) = |α0|² + |α1|²
P(line)  = |α2|²
```

---

## 3. Properties of a Projector

An orthogonal projector satisfies:

```text
Π† = Π
```

and

```text
Π² = Π
```

`Π†` is the **conjugate transpose** of `Π`.

`Π† = Π` means that the projector is Hermitian.

`Π² = Π` means that projecting the same state twice gives the same result as projecting it once.

A complete projective measurement also satisfies:

```text
Π0 + Π1 + ... + Πm-1 = I
```

where `I` is the identity matrix.

---

## 4. Measurement Probability

For a state `|ψ>`, the probability of obtaining outcome `k` is:

```text
P(k) = <ψ|Πk|ψ>
```

After obtaining outcome `k`, the state becomes:

```text
Πk|ψ>
----------------
√(<ψ|Πk|ψ>)
```

The denominator is used to normalize the state.

---

## 5. Local Measurement

A **local measurement** means measuring only part of a multi-qubit system.

Consider a two-qubit state:

```text
|ψ> =
α00|00> +
α01|01> +
α10|10> +
α11|11>
```

Suppose we measure only the **first qubit**.

If the first qubit is measured as `0`, only these terms remain:

```text
α00|00> + α01|01>
```

So the state is projected onto:

```text
span{|00>, |01>}
```

with probability:

```text
P(q1 = 0) = |α00|² + |α01|²
```

If the first qubit is measured as `1`, only these terms remain:

```text
α10|10> + α11|11>
```

So the state is projected onto:

```text
span{|10>, |11>}
```

with probability:

```text
P(q1 = 1) = |α10|² + |α11|²
```

> Measuring one qubit determines which subspace the whole multi-qubit state is projected onto.

---

## 6. Local Measurement Projectors

If we measure only the first qubit, the two projectors are:

```text
Π0 = |0><0| ⊗ I
Π1 = |1><1| ⊗ I
```

Here:

```text
|0><0| or |1><1| → measure the first qubit
I                 → do nothing to the second qubit
```

So:

```text
measure one qubit
        ↓
project that qubit
        ↓
leave the other qubits unchanged
```

---

## 7. Local Measurement in a Larger System

The same idea works for many qubits.

For example, suppose we have four qubits and measure only the second and third qubits.

One possible projector is:

```text
I ⊗ |0><0| ⊗ |0><0| ⊗ I
```

This means:

```text
Qubit 1 → not measured → I
Qubit 2 → measured as 0
Qubit 3 → measured as 0
Qubit 4 → not measured → I
```

General rule:

```text
measured qubit   → projector
unmeasured qubit → I
```

---

## 8. Product States and Local Measurement

Suppose the two-qubit state is separable:

```text
|ψ> ⊗ |φ>
```

If we measure only the first qubit, the second state `|φ>` is unchanged.

For an entangled state, however, measuring one qubit can change the **joint state** of the whole system.

---

## 9. Order of Local Measurements

Consider:

```text
|ψ> =
α00|00> +
α01|01> +
α10|10> +
α11|11>
```

The joint measurement probabilities are:

```text
P(00) = |α00|²
P(01) = |α01|²
P(10) = |α10|²
P(11) = |α11|²
```

Alice's local probability is:

```text
P(A = 0) = |α00|² + |α01|²
```

Bob's local probability is:

```text
P(B = 0) = |α00|² + |α10|²
```

For measurements on different qubits:

```text
Alice measures first
        =
Bob measures first
        =
both measure at the same time
```

The final measurement statistics are the same.

> The order of local measurements on different qubits does not change the final joint probabilities.

---

## 10. Local Operations Cannot Change the Other Side's Probabilities

A two-qubit state can be written as:

```text
|ψ> =
β0|0> ⊗ (γ0|0> + γ1|1>)
+
β1|1> ⊗ (δ0|0> + δ1|1>)
```

For Alice:

```text
P(A = 0) = |β0|²
P(A = 1) = |β1|²
```

Suppose Bob applies a unitary operation `U` only to his qubit:

```text
β0|0> ⊗ U(γ0|0> + γ1|1>)
+
β1|1> ⊗ U(δ0|0> + δ1|1>)
```

The coefficients `β0` and `β1` do not change.

Therefore:

```text
P(A = 0) = |β0|²
P(A = 1) = |β1|²
```

remain unchanged.

> Bob can change his own qubit, but he cannot change Alice's local measurement probabilities by a local unitary operation.

---

## 11. Bell Basis Encoding

Two classical bits can be encoded normally as:

```text
00 → |00>
01 → |01>
10 → |10>
11 → |11>
```

In this case, if Alice has the first qubit, measuring it directly reveals the first bit.

Bell-basis encoding is different:

```text
00 → (|00> + |11>) / √2
01 → (|00> - |11>) / √2
10 → (|01> + |10>) / √2
11 → (|01> - |10>) / √2
```

Here, the information is not stored in one qubit individually.

It is stored in the **relationship between the two qubits**.

---

## 12. Looking at Only One Qubit of a Bell State

Consider:

```text
|Φ+> = (|00> + |11>) / √2
```

If Alice measures only the first qubit:

```text
P(0) = 1/2
P(1) = 1/2
```

Now consider:

```text
|Φ-> = (|00> - |11>) / √2
```

Alice still gets:

```text
P(0) = 1/2
P(1) = 1/2
```

The same is true for all four Bell states.

Therefore:

> Alice cannot determine which Bell state she has by measuring only one qubit.

The information is stored in the **joint two-qubit state**.

---

## 13. Local Operations Can Change Bell-Basis Information

Although Alice cannot read the Bell-state information from her single qubit, she can still change the Bell state by applying local gates.

Using the Bell-basis encoding:

```text
X  → changes the first encoded bit
Z  → changes the second encoded bit
XZ → changes both encoded bits
```

For example:

```text
|Φ+> --X--> |Ψ+>
```

This is the key idea behind **superdense coding**.

```text
Alice changes one qubit
        ↓
the joint Bell state changes
        ↓
Bob measures both qubits
        ↓
Bob recovers the encoded information
```

---

## 14. Measuring the Control Qubit of a Controlled-U

Consider a controlled-`U` gate:

```text
control ──●──
          │
target  ──U──
```

There are two ways to think about the process.

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

If the control qubit is measured as `0`:

```text
U is not applied
```

If the control qubit is measured as `1`:

```text
U is applied
```

Therefore, when measuring the control qubit in the **computational basis**:

```text
measure before Controlled-U
        ≡
measure after Controlled-U
```

This equivalence depends on measuring in the computational basis.

---

## 15. Core Summary

> **1. Projective measurement determines which subspace a quantum state is projected onto.**

> **2. A projector satisfies `Π† = Π` and `Π² = Π`.**

> **3. The probability of a projective measurement outcome is `P(k) = <ψ|Πk|ψ>`.**

> **4. A local measurement measures only selected qubits; unmeasured qubits are represented by `I`.**

> **5. Measuring one qubit projects the whole joint state into the corresponding subspace.**

> **6. The order of local measurements on different qubits does not change the final measurement statistics.**

> **7. A local unitary operation on Bob's qubit cannot change Alice's local measurement probabilities.**

> **8. Bell-basis information is stored in the relationship between two qubits, not in either qubit individually.**

> **9. One qubit alone cannot distinguish the four Bell states.**

> **10. In the computational basis, measuring the control qubit before or after a Controlled-U gives the same measurement behavior.**
