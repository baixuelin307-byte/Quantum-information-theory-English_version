# 4.1 State Distinguishing

## 1. What Is State Discrimination?

> Given an unknown qubit known to be one of several candidate states, how can a measurement identify its original state?

`unknown state → known candidate set → choose a measurement basis → use the outcome to guess the state`

---

## 2. Simplest Case: Distinguishing $|+\rangle$ and $|-\rangle$

$|+\rangle=(|0\rangle+|1\rangle)/\sqrt{2}$

$|-\rangle=(|0\rangle-|1\rangle)/\sqrt{2}$

Their inner product is `⟨+|−⟩=0`, so they are orthogonal.

---

## 3. Why Does a 0/1 Measurement Fail to Distinguish Them?

In the computational basis `{|0⟩,|1⟩}`, both states produce:

`P(0)=1/2`, `P(1)=1/2`.

**Different states are not necessarily distinguishable using an arbitrary measurement; the measurement basis matters.**

---

## 4. How Can They Be Distinguished Perfectly?

Measure in the `{|+⟩,|-⟩}` basis. Input `|+⟩` always gives `+`, and input `|-⟩` always gives `−`.

**Orthogonal quantum states can be distinguished perfectly, with 100% success.**

---

## 5. Harder Case: Distinguishing $|0\rangle$ and $|+\rangle$

```math
|0\rangle=\begin{bmatrix}1\\0\end{bmatrix},\qquad
|+\rangle=\frac{1}{\sqrt2}\begin{bmatrix}1\\1\end{bmatrix}
```

Their directions differ by 45°, not 90°, and:

`⟨0|+⟩=1/√2 ≠ 0`.

Thus they are nonorthogonal.

---

## 6. What Does Nonorthogonality Mean?

```text
orthogonal → perfectly distinguishable
nonorthogonal → cannot be distinguished with 100% certainty in one measurement
```

Two states may be different without being perfectly distinguishable.

---

## 7. Method 1: Measure in the 0/1 Basis

Decision rule: outcome `0` → guess `|0⟩`; outcome `1` → guess `|+⟩`.

### Case 1: The True State Is $|0\rangle$

`P(success|0)=1`.

### Case 2: The True State Is $|+\rangle$

Because both outcomes occur with probability `1/2`, only outcome `1` is correct:

`P(success|+)=1/2`.

---

## 8. Average-Case Success Probability

For equal priors:

`P_avg=(1/2)×1+(1/2)×(1/2)=3/4=75%`.

---

## 9. Worst-Case Success Probability

`P_worst=min(1,1/2)=1/2=50%`.

---

## 10. Method 2: Measure in the +/− Basis

Decision rule: `+` → guess `|+⟩`; `−` → guess `|0⟩`.

Then `P(success|+)=1` and, since `|0⟩=(|+⟩+|-⟩)/√2`, `P(success|0)=1/2`.

Therefore `P_avg=75%` and `P_worst=50%`.

---

## 11. Randomly Mix the Two Measurements

Use the 0/1 basis with probability 50% and the +/− basis with probability 50%. Then:

`P(success|0)=(1/2)×1+(1/2)×(1/2)=3/4`

`P(success|+)=(1/2)×(1/2)+(1/2)×1=3/4`

Thus `P_worst=75%`, better than 50%.

---

## 12. A Better Measurement

The text constructs the basis:

$|\psi_0\rangle=\cos(\pi/8)|0\rangle-\sin(\pi/8)|1\rangle$

$|\psi_1\rangle=\sin(\pi/8)|0\rangle+\cos(\pi/8)|1\rangle$

Since `π/8=22.5°`, the directions are:

- `ψ₀`: −22.5°
- `ψ₁`: 67.5°
- `|0⟩`: 0°
- `|+⟩`: 45°

```text
                 |ψ1> 67.5°
                /
           |+> / 45°
              /
-------------→ |0> 0°
              \
               \
                |ψ0> -22.5°
```

