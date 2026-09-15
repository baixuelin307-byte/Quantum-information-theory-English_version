# 6. Systems with Multiple Bits and Multiple Qubits

## 1. Multiple Classical Bits

A classical bit has two possible values: `0` or `1`.

Two bits have `00, 01, 10, 11`, or `2² = 4` possible states. Three bits have `000, 001, 010, 011, 100, 101, 110, 111`, or `2³ = 8` states.

In general:

`n bits → 2ⁿ possible bit strings`

`x ∈ {0,1}ⁿ`

---

## 2. Classical Probability State

If the current bit string is unknown, an n-bit system can be represented by a probability distribution. For two bits:

`p = (p₀₀, p₀₁, p₁₀, p₁₁)`

where `pₓ ≥ 0` and:

`p₀₀ + p₀₁ + p₁₀ + p₁₁ = 1`

Thus, an n-bit probabilistic state is a probability vector with `2ⁿ` components.

---

## 3. Simplex

All valid classical probability distributions satisfy:

`pᵢ ≥ 0`, `Σᵢ pᵢ = 1`

The geometric region formed by all such vectors is called a `simplex`.

> simplex = the set of all valid classical probability distributions.

---

# 4. Multiple Qubits

The computational basis of one qubit is `|0⟩, |1⟩`.

For two qubits it is:

`|00⟩, |01⟩, |10⟩, |11⟩`

For three qubits it is:

`|000⟩, |001⟩, |010⟩, |011⟩, |100⟩, |101⟩, |110⟩, |111⟩`

In general:

`n qubits → 2ⁿ computational basis states → a 2ⁿ-dimensional Hilbert space`

---

## 5. General State of n Qubits

An n-qubit state can be written as:

`|ψ⟩ = Σₓ αₓ|x⟩`

where `x ∈ {0,1}ⁿ`, `|x⟩` is a computational basis state, and `αₓ` is its probability amplitude.

Note: `αₓ` is not a probability. The probability is `|αₓ|²`.

---

## 6. Two-Qubit State

`|ψ⟩ = α₀₀|00⟩ + α₀₁|01⟩ + α₁₀|10⟩ + α₁₁|11⟩`

The normalization condition is:

`|α₀₀|² + |α₀₁|² + |α₁₀|² + |α₁₁|² = 1`

---

## 7. Three-Qubit State

`|ψ⟩ = α₀₀₀|000⟩ + α₀₀₁|001⟩ + ... + α₁₁₁|111⟩`

There are `2³ = 8` amplitudes. In general:

`n qubits → 2ⁿ amplitudes`, with `Σₓ |αₓ|² = 1`.

---

# 8. Measurement

If `|ψ⟩ = Σₓ αₓ|x⟩` is measured in the computational basis, the probability of obtaining bit string `x` is:

`P(x) = |αₓ|²`

After measurement, the state collapses to `|x⟩`.

For a two-qubit state, the outcomes `00, 01, 10, 11` occur with probabilities `|α₀₀|², |α₀₁|², |α₁₀|², |α₁₁|²`.

---

# 9. Multiple Qubits Can Represent More States

One qubit has a general state `α|0⟩ + β|1⟩`, where `|α|² + |β|² = 1`. With multiple qubits, the state space grows rapidly:

```text
1 qubit → 2 basis states
2 qubits → 4 basis states
3 qubits → 8 basis states
n qubits → 2ⁿ basis states
```

