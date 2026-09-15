# 6.8 Controlled-U Gates

## 1. What Is a Controlled-U Gate?

A Controlled-U gate is a two-qubit gate with a **control qubit** and a **target qubit**:

```math
\text{control}=|0\rangle \Rightarrow \text{target is unchanged}
```

```math
\text{control}=|1\rangle \Rightarrow U\text{ is applied to the target}
```

The control itself is normally unchanged; it determines whether `U` is applied.

---

## 2. What Does “Apply U to the Target” Mean?

It does not always mean flipping the target. The target changes according to the particular gate `U`.

### When U = X

`X|0⟩=|1⟩`, `X|1⟩=|0⟩`; Controlled-X is CNOT.

### When U = Z

`Z|0⟩=|0⟩`, `Z|1⟩=-|1⟩`; the phase changes rather than the bit value.

### When U = H

`H|0⟩=(|0⟩+|1⟩)/√2`; the target enters a superposition.

> **The control decides whether the operation occurs; the target is the qubit on which U acts.**

---

## 3. Circuit Representation

```text
control   ──●──
            │
target    ──U──
```

---

## 4. Two-Qubit Computational Basis

`|00⟩, |01⟩, |10⟩, |11⟩`, where the first qubit is the control and the second is the target.

---

## 5. When the Control Is 0

```math
|00\rangle\rightarrow|00\rangle,
\qquad |01\rangle\rightarrow|01\rangle
```

---

## 6. When the Control Is 1

If:

```math
U=\begin{bmatrix}u_{00}&u_{01}\\u_{10}&u_{11}\end{bmatrix},
```

then:

```math
\begin{aligned}
|10\rangle&\rightarrow u_{00}|10\rangle+u_{10}|11\rangle\\
|11\rangle&\rightarrow u_{01}|10\rangle+u_{11}|11\rangle
\end{aligned}
```

---

## 7. Controlled-U Matrix

```math
CU=\begin{bmatrix}
1&0&0&0\\
0&1&0&0\\
0&0&u_{00}&u_{01}\\
0&0&u_{10}&u_{11}
\end{bmatrix}
=\begin{bmatrix}I&0\\0&U\end{bmatrix}
```

The upper block applies `I` when the control is 0; the lower block applies `U` when it is 1.

---

## 8. Most Important Formula

```math
|0\rangle|\psi\rangle\rightarrow|0\rangle|\psi\rangle
```

```math
|1\rangle|\psi\rangle\rightarrow|1\rangle U|\psi\rangle
```

---

## 9. Classic Example: CNOT

For `U=X`:

```math
|00\rangle\to|00\rangle,\quad |01\rangle\to|01\rangle,
\quad |10\rangle\to|11\rangle,\quad |11\rangle\to|10\rangle
```

---

## 10. Final Memory Aid

```text
control = 0 → target unchanged
control = 1 → apply U to target
```

`U` is not necessarily a bit flip; a flip occurs only when `U=X`.

---

## 11. Controlled-U Applies to Any Two-Qubit State

For `|ψ⟩=a|00⟩+b|01⟩+c|10⟩+d|11⟩`, including superposed or entangled states:

`|ψ'⟩ = CU|ψ⟩`.

---

## 12. Does Controlled-U Change the Control Qubit?

The standard gate does not directly apply `U` to the control. However, when the input control is in a superposition, the joint output may become entangled, so the two-qubit system should not be interpreted as two independent classical bits.

---

## 13. Control and Target Can Be Reversed

If the second qubit is the control and the first is the target, the action and matrix change according to the qubit ordering:

```math
CU_{\text{reversed}}=
\begin{bmatrix}
1&0&0&0\\
0&u_{00}&0&u_{01}\\
0&0&1&0\\
0&u_{10}&0&u_{11}
\end{bmatrix}
```

---

## 14. U May Be an n-Qubit Operation

If `U` is an n-qubit unitary, adding one control creates an `(n+1)`-qubit Controlled-U. The matrix still has block form:

```math
CU=\begin{bmatrix}I&0\\0&U\end{bmatrix}
```

where `I` and `U` are `2^n × 2^n`, and `CU` is `2^{n+1} × 2^{n+1}`.

---

## 15. Core Summary

1. Controlled-U applies to all two-qubit states, not only basis states.
2. The control determines whether `U` is applied to the target.
3. Control and target positions may be exchanged, but the matrix changes.
4. `U` may act on n target qubits, producing an `(n+1)`-qubit gate.

> **The control decides whether the operation is executed; the target receives U.**

