# Representing Local Unitary Operations in Multi-Qubit Systems

## 1. Basic Concept

In a multi-qubit system, a unitary operation may act on only one qubit or subsystem. In a two-qubit system:

```text
q1 → no operation
q2 → apply U
```

the whole operation is `I ⊗ U`, where `I` is the identity and `U` acts on the second qubit.

---

## 2. Why Can We Not Write Only U?

A single-qubit unitary is a `2 × 2` matrix, whereas a two-qubit state vector is four-dimensional. An operation on the complete system must be `4 × 4`, so the local `U` is extended as `I ⊗ U`.

---

## 3. Matrix Form of I ⊗ U

If:

```text
U = [u00  u01
     u10  u11]
```

then:

```text
I ⊗ U =

[u00  u01   0    0
 u10  u11   0    0
  0    0   u00  u01
  0    0   u10  u11]

= [U  0
   0  U]
```

---

## 4. Does U Change the First Qubit?

No. The first qubit is acted on by `I`, and `I|ψ⟩ = |ψ⟩`:

```text
(I ⊗ U)|00⟩ = |0⟩ ⊗ U|0⟩
(I ⊗ U)|10⟩ = |1⟩ ⊗ U|0⟩
```

Only the second factor changes.

---

## 5. The First Qubit Is Not “Absent”

The first qubit remains part of the complete system; it is acted on by the identity rather than ignored.

---

## 6. Action on the Computational Basis

```text
|00⟩ → |0⟩ ⊗ U|0⟩
|01⟩ → |0⟩ ⊗ U|1⟩
|10⟩ → |1⟩ ⊗ U|0⟩
|11⟩ → |1⟩ ⊗ U|1⟩
```

The first bit remains unchanged; the second evolves according to `U`.

---

## 7. Operating on the First Qubit

```text
I ⊗ U → apply U to the second qubit
U ⊗ I → apply U to the first qubit
```

---

## 8. Extension to an n-Qubit System

Place identities at all positions other than the target. For five qubits, applying `U` only to qubit 3 gives:

`I ⊗ I ⊗ U ⊗ I ⊗ I`

---

## 9. What Do the Symbols U, V, and S Mean?

`U`, `V`, and `S` usually denote arbitrary unitary operations, not fixed gates. Symbols such as `X`, `Y`, `Z`, `H`, and `CNOT` normally have standard meanings.

---

## 10. Unitary Evolution

In a closed quantum system:

`|ψ'⟩ = U|ψ⟩`, with `U†U = I`.

This preserves normalization: `||ψ'||² = 1`. A local operation, when extended with identities, is still unitary on the full Hilbert space.

---

## 11. When No Local Operation Is Applied

In an ideal circuit model, no gate is equivalent to `I`. In a physical system, however, the state may still evolve because of its Hamiltonian, the quantum channel, noise, decoherence, or photon loss.

```text
Circuit abstraction: no gate → I → unchanged
Physical system: no active control → natural/channel evolution may continue
```

---

## 12. Core Summary

> **A local unitary changes only its target subsystem, but identities and tensor products are needed to express it as a complete unitary operation on the multi-qubit system.**

---

## 13. Different Local Unitary Operations on Different Qubits

If subsystem A undergoes `V` and subsystem B undergoes `U`, the joint operation is:

`V ⊗ U`

---

## 14. Operations on Different Subsystems Commute

Because they act on different tensor factors:

```text
(V ⊗ I)(I ⊗ U)
= (I ⊗ U)(V ⊗ I)
= V ⊗ U
```

Thus, local unitaries on disjoint subsystems can be reordered or performed in parallel.

---

## 15. Multiple Layers of Local Unitary Operations

If subsystem A undergoes `V1` followed by `V2`, and subsystem B undergoes `U1` followed by `U2`, then:

### Method 1: Evolve Each Subsystem Separately

`(V2V1) ⊗ (U2U1)`

### Method 2: Combine Each Time Layer

```text
(V2 ⊗ U2)(V1 ⊗ U1)
= (V2V1) ⊗ (U2U1)
```

The two views are equivalent.

---

## 16. Central Ideas

> **1. Different qubits may undergo different local unitary operations.**

> **2. If two subsystems undergo `V` and `U`, the complete operation is `V ⊗ U`.**

> **3. Local unitaries on different subsystems commute and can be performed in parallel.**

> **4. In multilayer operations, we may evolve each subsystem first or combine operations by time layer; the result is the same.**

