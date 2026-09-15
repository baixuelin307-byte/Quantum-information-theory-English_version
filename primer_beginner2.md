# What Is a Qubit?

## 1. Classical Bit

A bit can be understood from two perspectives.

### 1.1 Operational Perspective

A bit can be viewed as:

> A system that can store either 0 or 1 and from which the stored information can be read.

A classical bit has only two states: `$0$` or `$1$`. We can also operate on it. For example, a NOT gate performs:

$0 \rightarrow 1$

$1 \rightarrow 0$

Thus, a bit can store, expose, and modify information.

---

### 1.2 Information Perspective

Complex information can be encoded as a sequence of zeros and ones, for example:

`01001101...`

Together, these symbols form an information system. Therefore:

> **A classical bit is the basic unit used to store, read, and modify information using 0 and 1.**

---

# 2. A Simple Analog Model of Information

Unlike a digital bit, which can only be `0` or `1`, an analog model can take values throughout a continuous interval, such as `0.1265`, `0.7895`, or `0.5321`.

Its state is continuous rather than one of only two discrete possibilities.

---

## 2.1 Analog Set Device

An analog set device can set the system to any value between 0 and 1, for example `0.2`, `0.73`, or `0.999`.

---

## 2.2 Analog Read Device

An analog read device reports the continuous value currently stored in the system:

`readout = 0.7895`

---

## 2.3 Analog Transformation

Analog information can be transformed by a function:

$x \rightarrow f(x)$

with `$x\in[0,1]$` and `$f(x)\in[0,1]$`.

Thus analog information can be set, read, and modified, but its state space is continuous.

---

# 3. A Simple Probabilistic Digital Model of Information

This is still a digital model: the true state of the bit remains either `0` or `1`. However, we may not know which state it has.

For example:

$P(0)=0.3$

$P(1)=0.7$

This means there is a 30% probability of 0 and a 70% probability of 1. The probability vector is `(0.3,0.7)`, with `$P(0)+P(1)=1$`.

---

## 3.1 Key Point

> **A probabilistic description does not change the bit itself.**

The true bit remains `0` or `1`; probability describes our uncertainty about its current state.

`probabilistic bit = classical bit + probability description`

---

# 4. A Simple Quantum Model of Information

The quantum-information model is fundamentally different from the classical models. Comparing a qubit with analog and probabilistic models nevertheless helps clarify its structure.

---

## 4.1 Basic Representation of a Qubit

A general qubit state is:

$|\psi\rangle=\alpha_0|0\rangle+\alpha_1|1\rangle$

where:

- `$\alpha_0$` is the probability amplitude of `$|0\rangle$`
- `$\alpha_1$` is the probability amplitude of `$|1\rangle$`

> **A probability amplitude is not itself a probability.**

The measurement probabilities are:

$P(0)=|\alpha_0|^2$

$P(1)=|\alpha_1|^2$

---

# 5. Probability Amplitude

An ordinary probability has only a magnitude, such as `0.3` or `0.7`. A probability amplitude is generally a complex number and therefore contains both a magnitude and a **phase**.

This is a major distinction between classical probabilities and quantum probability amplitudes.

---

## 5.1 Probability-Amplitude Vector

A qubit can be represented by the vector `$(\alpha_0,\alpha_1)$`, equivalently:

$|\psi\rangle=\alpha_0|0\rangle+\alpha_1|1\rangle$

where `$\alpha_0,\alpha_1\in\mathbb{C}$`.

---

## 5.2 Normalization

The probability-amplitude vector must satisfy:

$|\alpha_0|^2+|\alpha_1|^2=1$

because:

$P(0)=|\alpha_0|^2$, `$P(1)=|\alpha_1|^2$`, and `$P(0)+P(1)=1$`.

---

# 6. Phase

A complex amplitude can be written as:

$re^{i\phi}$

where `r` is its magnitude, `φ` is its phase, and `$i^2=-1$`. A probability amplitude therefore contains both magnitude and phase.

---

# 7. Angular Representation of a Qubit

A single qubit can be written as:

$|\psi\rangle=\sin(\theta)|0\rangle+e^{i\phi}\cos(\theta)|1\rangle$

where `$\alpha_0=\sin(\theta)$` and `$\alpha_1=e^{i\phi}\cos(\theta)$`.

Normalization follows automatically from `$\sin^2\theta+\cos^2\theta=1$`.

---

## 7.1 Role of $\theta$

`θ` determines the relative magnitudes of the `|0⟩` and `|1⟩` components and therefore mainly affects `P(0)` and `P(1)`.

---

## 7.2 Role of $\phi$

`φ` determines the **relative phase** between the two probability amplitudes. It does not merely control how much probability belongs to 0 or 1. Relative phase affects:

- interference
- state discrimination
- quantum computation
- measurement outcomes in different bases

---

# 8. What Is a Qubit Before Measurement?

Before measurement, a qubit may be in the state:

$|\psi\rangle=\alpha_0|0\rangle+\alpha_1|1\rangle$

It can be in a superposition of `|0⟩` and `|1⟩`. This does not mean that it secretly has a predetermined value of 0 or 1. Rather:

> The qubit itself is in a quantum state described by probability amplitudes and phase.

---

# 9. Measuring a Qubit

Measurement in the computational basis `{|0⟩,|1⟩}` produces only outcome `0` or `1`, with:

$P(0)=|\alpha_0|^2$

$P(1)=|\alpha_1|^2$

After measurement, the state collapses to the corresponding basis state:

`$|\psi\rangle\rightarrow|0\rangle$` or `$|\psi\rangle\rightarrow|1\rangle$`.

---

# 10. Classical Probability vs. Quantum Probability Amplitude

### Classical Probabilistic Model

`P(0),P(1)` describe uncertainty about a bit whose actual state is already either `0` or `1`.

### Quantum Model

`α₀,α₁` describe a qubit, with `$P(0)=|\alpha_0|^2$` and `$P(1)=|\alpha_1|^2$`. The amplitudes also contain phase, so a quantum state is more than an ordinary probability distribution.

---

# 11. Most Fundamental Difference

### Classical Bit

`0 or 1`

### Probabilistic Classical Bit

`0 or 1 + probability`

### Qubit

`probability amplitude + phase`

$|\psi\rangle=\alpha_0|0\rangle+\alpha_1|1\rangle$, with `$|\alpha_0|^2+|\alpha_1|^2=1$`.

---

# 12. A Qubit in One Sentence

> **A qubit is the basic unit of quantum information described by complex probability amplitudes. It can be in a superposition of `$|0\rangle$` and `$|1\rangle$`, and its measurement probabilities are the squared magnitudes of those amplitudes.**

The basic expression is:

$|\psi\rangle=\alpha_0|0\rangle+\alpha_1|1\rangle$

where:

- `$\alpha_0,\alpha_1$`: probability amplitudes
- `$|\alpha_0|^2$`: probability of measuring 0
- `$|\alpha_1|^2$`: probability of measuring 1
- phase: contained in the complex amplitudes
- `$|\alpha_0|^2+|\alpha_1|^2=1$`

---

## Simplest Memory Aid

```text
bit = 0 or 1
probabilistic bit = 0 or 1 + probability
qubit = probability amplitude + phase + superposition

qubit → measurement → 0 or 1
```

