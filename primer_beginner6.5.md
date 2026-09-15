# 6.5 Notation for Explicitly Referring to Individual Qubits

## 1. Why Qubits Need Labels

In a multi-qubit system, unlabeled kets such as `|0⟩`, `|1⟩`, and `|01⟩` can become ambiguous. Subscripts identify the qubit:

```text
|0⟩₁ = qubit 1 is in |0⟩
|1⟩₂ = qubit 2 is in |1⟩
|0⟩₃ = qubit 3 is in |0⟩
```

---

## 2. A Qubit Label Is Only a Label, Not a Physical Position

> A qubit number distinguishes one qubit from another; it does not specify its location in physical space.

`qubit label ≠ physical location`

---

## 3. Labels Allow the Written Order to Change

```text
|1⟩₁ |0⟩₂ |1⟩₃
```

means qubits 1, 2, and 3 are in `|1⟩`, `|0⟩`, and `|1⟩`, respectively. Because every ket is labeled, writing:

```text
|1⟩₃ |1⟩₁ |0⟩₂
```

describes the same assignments in a different order.

---

## 4. A Multi-Qubit Subsystem Can Also Be Labeled

`|00⟩₁,₃` denotes the two-qubit state of qubits 1 and 3. Thus:

```text
(|00⟩₁,₃ + |11⟩₁,₃) ⊗ |0⟩₂
```

clearly specifies that qubits 1 and 3 form one subsystem while qubit 2 is separately in `|0⟩`.

---

## 5. Why This Notation Matters

Without labels, `(|00⟩ + |11⟩) ⊗ |0⟩` does not reveal which physical qubits belong to each ket.

> **The main purpose of qubit labels is to eliminate ambiguity in multi-qubit systems.**

---

## 6. Qubit Labels for Alice and Bob

Quantum-communication participants may hold several qubits:

```text
Alice → A1, A2
Bob   → B1, B2
```

This is clearer than using a single sequence `1, 2, 3, 4`.

---

## 7. Alice-and-Bob Example

If `A1,B1` form one pair and `A2,B2` another:

```text
(|00⟩A1,B1 + |11⟩A1,B1)
⊗
(|00⟩A2,B2 + |11⟩A2,B2)
```

The labels clearly identify both subsystems.

---

## 8. Labels Remain When a Tensor Product Is Expanded

The preceding expression expands to:

```text
|00⟩A1,B1 |00⟩A2,B2
+ |00⟩A1,B1 |11⟩A2,B2
+ |11⟩A1,B1 |00⟩A2,B2
+ |11⟩A1,B1 |11⟩A2,B2
```

Each label continues to identify the qubits belonging to its ket.

---

## 9. Relationship to Section 6.4

```text
6.4 → how to combine subsystems
6.5 → how to label qubits and subsystems unambiguously
```

---

## 10. Core Summary

```text
Qubit Label
│
├── identifies a specific qubit: |0⟩₁, |1⟩₂
├── is a name, not a physical location
├── permits reordered notation without ambiguity
├── can identify several qubits: |00⟩₁,₃
└── may identify owners: A1, A2, B1, B2
```

> **1. Subscripts identify which qubit a state belongs to.**

> **2. A qubit label is mathematical notation, not a physical-space coordinate.**

> **3. A multi-qubit subsystem can be labeled together, for example `|00⟩₁,₃`.**

> **4. Participant labels such as `A1, A2, B1, B2` distinguish Alice's and Bob's qubits.**

> **5. Section 6.5 introduces an unambiguous notation system, not a new quantum operation.**

