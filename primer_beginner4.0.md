# 4: Introduction to State Distinguishing Problems

When a physical bit is converted into a quantum bit, the state of that qubit is a quantum state. Quantum states themselves can take many different forms.

## 1. Example

$|+\rangle = \frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle$

$|-\rangle = \frac{1}{\sqrt{2}}|0\rangle - \frac{1}{\sqrt{2}}|1\rangle$

The plus and minus states are orthogonal because:

$\langle + | - \rangle = 0$

<img width="218" height="205" alt="image" src="https://github.com/user-attachments/assets/ec1b9ad3-c5fd-4dde-8204-226d64211570" />

In this two-dimensional cross-section:

- $|1\rangle$ points upward
- $|0\rangle$ points right
- $|+\rangle$ points upper-right
- $|-\rangle$ points lower-right

# Additional Explanation: Inferring Direction Directly from a Quantum-State Formula

For a single-qubit state:

`|ψ⟩ = α|0⟩ + β|1⟩`

the present two-dimensional diagram treats it as coordinates:

`|ψ⟩ ↔ (α, β)`

where `|0⟩` is the horizontal axis, `|1⟩` is the vertical axis, `α` is the horizontal component, and `β` is the vertical component.

**The signs of the coefficients determine the direction; their magnitudes determine the tilt.**

---

## 1. Direction from the Signs

| α | β | Direction |
|---|---|---|
| positive | positive | upper-right ↗ |
| positive | negative | lower-right ↘ |
| negative | positive | upper-left ↖ |
| negative | negative | lower-left ↙ |

---

## 2. Example: |+⟩

`|+⟩ = (1/√2)|0⟩ + (1/√2)|1⟩`

Both coefficients are positive, so `(α,β)=(+,+)` and the direction is **upper-right ↗**.

`|+⟩ = (1/√2)[1,1]ᵀ`

---

## 3. Example: |-⟩

`|-⟩ = (1/√2)|0⟩ + (-1/√2)|1⟩`

Here `α>0` and `β<0`, so the direction is **lower-right ↘**.

`|-⟩ = (1/√2)[1,-1]ᵀ`

---

## 4. Coefficient Magnitudes Determine Which Axis Is Closer

For `|ψ⟩=(√3/2)|0⟩+(1/2)|1⟩`, both coefficients are positive, but the `|0⟩` component is larger. The vector points upper-right but lies closer to the horizontal axis.

For `|ψ⟩=(1/2)|0⟩+(√3/2)|1⟩`, it still points upper-right but lies closer to the vertical axis.

---

## 5. Quick Method

For `|ψ⟩=α|0⟩+β|1⟩`, read the coefficients as `(α,β)`:

1. `α > 0` → right
2. `α < 0` → left
3. `β > 0` → up
4. `β < 0` → down
5. `|α|` and `|β|` determine the tilt toward an axis

**Signs determine direction; magnitudes determine tilt.**

---

## 6. Do Not Look Only at the + or − in the State Name

In `|-⟩=(1/√2)|0⟩-(1/√2)|1⟩`, the minus sign means the coefficient of `|1⟩` is negative; it does not mean that the entire state points in a generic “negative direction.”

> Note: This directional shortcut applies to the real coefficients considered here. With complex coefficients such as `i` or `e^(iθ)`, phase must also be considered, and a simple two-dimensional up/down/left/right picture is insufficient.

