# 4.2 Global Phases

## 1. What Is a Global Phase?

Multiplying an entire quantum state by a complex phase `e^{iθ}` does not change its physical state:

$|\psi\rangle \sim e^{i\theta}|\psi\rangle$, where `$|e^{i\theta}|=1$`.

---

## 2. Example: $|+\rangle$ and $-|+\rangle$

$|+\rangle=(|0\rangle+|1\rangle)/\sqrt2$

$-|+\rangle=(-|0\rangle-|1\rangle)/\sqrt2$

Because `−1=e^{iπ}`, these vectors differ only by a global phase and represent the same physical state.

---

## 3. Why Does a Global Phase Not Affect Measurement?

An amplitude `α` becomes `e^{iθ}α`, but:

$|e^{i\theta}\alpha|^2=|e^{i\theta}|^2|\alpha|^2=|\alpha|^2$.

Therefore, a global phase changes no measurement probability and is unobservable.

---

## 4. Global Phase vs. Relative Phase

### Global Phase

Multiplying every component by the same phase, such as:

$|+\rangle\rightarrow-|+\rangle$

does not change the physical state.

### Relative Phase

Changing only one component:

$\frac{|0\rangle+|1\rangle}{\sqrt2}\rightarrow\frac{|0\rangle-|1\rangle}{\sqrt2}$

changes `|+⟩` into `|-⟩`. This changes the relative phase and therefore the physical state.

---

## 5. Why Does Relative Phase Affect Measurement?

In the computational basis, both `|+⟩` and `|-⟩` give `P(0)=P(1)=1/2`. In the `{|+⟩,|-⟩}` basis, however, `|+⟩` always gives `+` and `|-⟩` always gives `−`. A suitable measurement can therefore reveal relative phase.

---

## 6. Relationship to State Discrimination

Global phase does not affect state discrimination. For example, `|1⟩` and `−|1⟩` are the same physical state. Global phases can be ignored, and some discrimination problems can be reduced to known cases using unitary rotations.

---

## 7. Most Important Conclusions

1. `$|\psi\rangle$` and `$e^{i\theta}|\psi\rangle$` represent the same physical state.
2. Global phase does not change measurement probabilities.
3. Global phase is unobservable.
4. Relative phase changes the relationship between components.
5. Relative phase can change the physical state.
6. Relative phase can affect interference and measurement outcomes.

---

## One-Sentence Summary

**Global phase changes neither the physical state nor measurement outcomes; relative phase can change both.**

