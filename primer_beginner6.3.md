# 6.3 Subsystems of n-qubit Systems

## 1. An n-Qubit System Can Be Divided into Subsystems

Like an n-bit system, an n-qubit system can be viewed as a whole or by focusing on selected qubits. A 3-qubit state has amplitudes:

```text
[α000, α001, α010, α011,
 α100, α101, α110, α111]
```

These are **probability amplitudes**, not probabilities:

`P(ijk) = |αijk|²`

---

## 2. Why Can We Not Add Amplitudes Like Classical Probabilities?

Classically, `P(b1 = 0) = p000 + p001 + p010 + p011` because each `p` is a probability. Quantum amplitudes cannot be added this way to obtain a marginal probability.

---

## 3. Counterexample

Consider:

```text
[ 1/√8, -1/√8, 1/√8, -1/√8,
  1/√8, -1/√8, 1/√8, -1/√8 ]
```

Adding the first four amplitudes gives `0`; the last four also give `0`, producing `[0,0]`. This is invalid because `|0|² + |0|² = 0 ≠ 1`.

> A quantum subsystem cannot be obtained by directly adding amplitudes.

---

## 4. If We Only Need Measurement Probabilities

For the first qubit:

```text
P(q1 = 0) = |α000|² + |α001|² + |α010|² + |α011|²
P(q1 = 1) = |α100|² + |α101|² + |α110|² + |α111|²
```

```text
amplitude α → squared magnitude |α|² → probability
            → sum over other qubits → subsystem distribution
```

---

## 5. Measurement Distribution ≠ Complete Quantum State

`[P(q1 = 0), P(q1 = 1)]` gives only computational-basis measurement probabilities. A complete subsystem state may also contain phase, coherence, and mixedness caused by entanglement.

---

## 6. Complete Representation of a Subsystem

Use a `density matrix` and a `partial trace`:

```text
whole quantum state
        ↓
construct the density matrix
        ↓
partial trace over the unwanted subsystem
        ↓
density matrix of the target subsystem
```

`ρA = TrB(ρAB)`

Here, `ρAB` describes the whole system, `B` is discarded, and `ρA` is the complete state of subsystem `A`.

---

## 7. Difference from a Classical Subsystem

### Classical System

```text
probabilities → sum over unwanted bits → subsystem distribution
```

### Quantum System

For measurement probabilities:

```text
amplitudes → |α|² → probabilities → sum over unwanted qubits
```

For the complete state:

```text
whole state → density matrix → partial trace → subsystem density matrix
```

---

## 8. Core Summary

> **1. A quantum state contains probability amplitudes, not probabilities.**

> **2. To obtain a subsystem's measurement distribution, first take squared magnitudes and then sum over unwanted qubits.**

> **3. To represent the complete subsystem state, use a density matrix and partial trace.**

