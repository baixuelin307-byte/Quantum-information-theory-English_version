# 6.2 Subsystems of n-bit Systems

## 1. Whole Systems and Subsystems

An `n-bit system` can be viewed as a whole, or we can focus on only some of its bits. The selected part is called a **subsystem**.

A 3-bit system has:

```text
000, 001, 010, 011,
100, 101, 110, 111
```

Its eight-dimensional probability vector is:

```text
[p000, p001, p010, p011,
 p100, p101, p110, p111]
```

and all entries sum to 1.

---

## 2. The State of One Bit

If we focus only on the first bit:

```text
P(first bit = 0) = p000 + p001 + p010 + p011
P(first bit = 1) = p100 + p101 + p110 + p111
```

Thus, the subsystem probability vector is:

```text
[p000 + p001 + p010 + p011
 p100 + p101 + p110 + p111]
```

---

## 3. Marginalization

Obtaining a subsystem distribution from the whole distribution is called `marginalization`.

> Sum over the probabilities associated with the bits that are not of interest.

```text
Whole probability distribution
        ↓
Retain the bits of interest
        ↓
Sum over the other bits
        ↓
Subsystem probability distribution
```

The subsystem state is not obtained by simply extracting a few entries from the original vector.

---

## 4. Arbitrary Subsystems

The same method applies when retaining the second bit, third bit, first two bits, or first and third bits. Sum over every bit outside the chosen subsystem.

---

## 5. Operations on a Subsystem

If an operation `S` acts only on the first bit:

```text
bit 1 → S
bit 2 → unchanged
bit 3 → unchanged
```

the whole-system operation is:

```text
S ⊗ I ⊗ I
```

where `I` is the identity operation.

---

## 6. Local Operations

Different operations may act on different bits:

```text
S → first bit
T → second bit
U → third bit
```

These are **local operations**. The symbols denote general operations and do not necessarily mean a bit flip.

---

## 7. Core Summary

```text
n-bit system
│
├── Whole system: 2^n-dimensional probability vector
├── Subsystem: only selected bits
├── Subsystem state: marginalize over other bits
└── Local operation: acts on only one subsystem
```

> **A subsystem state is obtained by marginalization—summing the probabilities associated with bits that are not of interest—not by directly extracting entries from the full vector.**

