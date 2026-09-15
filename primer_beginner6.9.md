# 6.9 Controlled-NOT Gate (CNOT)

## 1. What Is CNOT?

CNOT stands for **Controlled-NOT Gate**. It is the special case of Controlled-U in which `U=X`, the Pauli-X gate:

```math
\text{Controlled-}U=\text{Controlled-}X=\text{CNOT}
```

```text
control ──●──
          │
target  ──X──
```

```text
control = 0 → target unchanged
control = 1 → target flipped
```

where the flip is `0 ↔ 1`.

---

## 2. Action on Basis States

```math
|00\rangle\rightarrow|00\rangle
```

```math
|01\rangle\rightarrow|01\rangle
```

```math
|10\rangle\rightarrow|11\rangle
```

```math
|11\rangle\rightarrow|10\rangle
```

The first two states have control 0, so the target is unchanged. The last two have control 1, so the target flips.

---

## 3. CNOT and XOR

If the control is `a` and the target is `b`, then:

```math
(a,b)\rightarrow(a,a\oplus b)
```

| Control `a` | Target `b` | `a⊕b` |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

Thus `0⊕b=b`, while `1⊕b` flips `b`.

---

## 4. CNOT Matrix

CNOT is a two-qubit gate and therefore has a `4 × 4` matrix:

```math
\mathrm{CNOT}=
\begin{bmatrix}
1&0&0&0\\
0&1&0&0\\
0&0&0&1\\
0&0&1&0
\end{bmatrix}
```

---

## 5. CNOT Also Acts on Superpositions

Let:

```math
|+\rangle=\frac{|0\rangle+|1\rangle}{\sqrt{2}}
```

Then:

```math
|+\rangle|0\rangle
=\frac{|00\rangle+|10\rangle}{\sqrt{2}}
```

Here `+` denotes a superposition, not XOR. Applying CNOT gives:

```math
\frac{|00\rangle+|10\rangle}{\sqrt{2}}
\rightarrow
\frac{|00\rangle+|11\rangle}{\sqrt{2}}
```

---

## 6. Superposition and Entanglement

The input is separable:

```math
\frac{|00\rangle+|10\rangle}{\sqrt{2}}
=\left(\frac{|0\rangle+|1\rangle}{\sqrt{2}}\right)\otimes|0\rangle
```

The output `(|00⟩+|11⟩)/√2` cannot be written as `|ψ₁⟩⊗|ψ₂⟩`, so it is entangled.

```text
can be written as a tensor product → separable
cannot be written as a tensor product → entangled
```

> Superposition is not the same as entanglement. One qubit may be in a superposition; entanglement concerns a joint state of multiple qubits that cannot be separated.

---

## 7. Why Can CNOT Generate Entanglement?

If the control is fixed, for example `|1⟩|0⟩ → |1⟩|1⟩`, the output remains a product state.

If the control is in a superposition, its different components produce different conditional changes in the target:

```text
control = 0 → target unchanged
control = 1 → target flipped
```

Therefore:

```text
superposed control + conditional operation → may generate entanglement
```

---

## 8. CNOT Can Construct More Complex Controlled-U Gates

More complex controlled operations can be decomposed into:

```text
single-qubit gates + CNOT gates
```

This is called **quantum circuit decomposition**.

---

# 9. Final Memory Aid

```text
CNOT = Controlled-X

control = 0 → target unchanged
control = 1 → target flipped
```

```math
\boxed{(a,b)\rightarrow(a,a\oplus b)}
```

For a superposition:

```math
\boxed{
\frac{|00\rangle+|10\rangle}{\sqrt{2}}
\rightarrow
\frac{|00\rangle+|11\rangle}{\sqrt{2}}
}
```

The input is separable; the output is entangled.

