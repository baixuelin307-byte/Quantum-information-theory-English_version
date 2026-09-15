# 6.7 Multiplicative Property of Tensors

## 1. Relationship to the Previous Section

Local operations on subsystems A and B combine as `V ⊗ U`. Multiple operation layers produce expressions such as:

`(V2 ⊗ U2)(V1 ⊗ U1)`

Section 6.7 explains how this tensor-product matrix multiplication separates.

---

## 2. Multiplicative Property

```text
(A ⊗ B)(C ⊗ D) = (AC) ⊗ (BD)
```

This requires the matrix dimensions in `AC` and `BD` to be compatible.

---

## 3. Interpretation

On the first subsystem, `C` acts first and then `A`, giving `AC`. On the second, `D` acts first and then `B`, giving `BD`. Combining the results gives `(AC) ⊗ (BD)`.

---

## 4. Application to Local Unitary Operations

```text
(V2 ⊗ U2)(V1 ⊗ U1)
= (V2V1) ⊗ (U2U1)
```

> **We may first calculate each subsystem's evolution and then take the tensor product of the results.**

---

## 5. Proof Idea

Use identities to write:

```text
A ⊗ B = (A ⊗ I)(I ⊗ B)
C ⊗ D = (C ⊗ I)(I ⊗ D)
```

Operations on different tensor factors commute, so:

```text
(A ⊗ I)(I ⊗ B)(C ⊗ I)(I ⊗ D)
= (AC ⊗ I)(I ⊗ BD)
= (AC) ⊗ (BD)
```

---

## 6. Core Summary

```text
Tensor-Product Multiplication
│
├── (A ⊗ B)(C ⊗ D) = (AC) ⊗ (BD)
├── first subsystem: C → A → AC
├── second subsystem: D → B → BD
└── quantum circuit:
    (V2 ⊗ U2)(V1 ⊗ U1)
    = (V2V1) ⊗ (U2U1)
```

> **When tensor-product matrices are multiplied, multiply the corresponding matrices for each subsystem and then take the tensor product of the results.**

