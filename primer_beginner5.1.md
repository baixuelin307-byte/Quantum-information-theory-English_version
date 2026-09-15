5.1 Communicating a Trit Using a Qubit

1. Goal

Alice has a trit:

`a ∈ {0, 1, 2}`

and wants to send it to Bob. A single classical bit can carry only `0` or `1`, so it cannot perfectly distinguish all three trit values.

2. Classical-Bit Strategy

One deterministic strategy is:

```text
trit 0 → send bit 0
trit 1 → send bit 1
trit 2 → also send bit 1
```

Bob guesses trit 0 after receiving 0 and trit 1 after receiving 1. The three conditional success probabilities are `1, 1, 0`, so:

`P_worst = 0`

One input is completely sacrificed.

3. Randomized-Bit Strategy

Randomization can prevent any one trit from always failing. With an appropriate randomized strategy, every input can attain worst-case success probability:

`P_worst(bit) = 1/2 = 50%`

This is the optimal classical-bit benchmark.

4. Qubit Strategy

Alice encodes the three trits as three distinct qubit states:

```text
0 → |φ₀⟩
1 → |φ₁⟩
2 → |φ₂⟩
```

These are symmetric **trine states**, separated by 120° in a real two-dimensional representation:

```text
            |φ₁⟩
           /
          /
         O------> |φ₀⟩
          \
           \
            |φ₂⟩
```

A two-dimensional qubit space cannot contain three pairwise orthogonal states, so one qubit cannot encode and distinguish a trit perfectly. A suitable measurement can nevertheless outperform a classical bit.

5. Important Property of Trine States

The three symmetric states satisfy:

`|ψ₀⟩⟨ψ₀| + |ψ₁⟩⟨ψ₁| + |ψ₂⟩⟨ψ₂| = (3/2)I`

For example, take:

```text
|ψ₀⟩ = (1, 0)
|ψ₁⟩ = (-1/2, √3/2)
|ψ₂⟩ = (-1/2, -√3/2)
```

Their projectors are:

```text
|ψ₀⟩⟨ψ₀| = [1  0]
             [0  0]

|ψ₁⟩⟨ψ₁| = [ 1/4   -√3/4]
             [-√3/4   3/4 ]

|ψ₂⟩⟨ψ₂| = [1/4   √3/4]
             [√3/4  3/4 ]
```

The off-diagonal entries cancel, leaving:

```text
[3/2   0 ]
[ 0   3/2] = (3/2)I
```

Thus `(3/2)I` is obtained by actually summing the trine-state projectors; it is not imposed by definition.

6. Why Does 2/3 Appear?

A valid POVM must satisfy:

`E₀ + E₁ + E₂ = I`

Because the projectors sum to `(3/2)I`, multiply them by the normalization factor `2/3`:

`Eᵢ = (2/3)|ψᵢ⟩⟨ψᵢ|`

Then:

`ΣᵢEᵢ = (2/3)Σᵢ|ψᵢ⟩⟨ψᵢ| = (2/3)(3/2)I = I`

7. Why Can the Success Probability Reach 2/3?

If Alice sends `|ψᵢ⟩`, the probability that Bob obtains outcome `i` is:

`P(i|i)=⟨ψᵢ|Eᵢ|ψᵢ⟩`

Substituting the POVM element gives:

`P(i|i)=(2/3)⟨ψᵢ|ψᵢ⟩⟨ψᵢ|ψᵢ⟩=2/3`

because each state is normalized. Therefore:

```text
P(success|0)=2/3
P(success|1)=2/3
P(success|2)=2/3
```

and:

`P_worst(qubit)=2/3≈66.7%`

8. Classical Bit vs. Qubit

```text
Classical bit: P_worst = 1/2 = 50%
Qubit:        P_worst = 2/3 ≈ 66.7%
```

Since `2/3 > 1/2`, a qubit cannot perfectly store a trit, but in this communication task it preserves more useful information about the trit than a classical bit.

9. Purple and Red Directions in the Figure

The purple directions are Alice's encoding states `|φ₀⟩,|φ₁⟩,|φ₂⟩`. The red directions are Bob's measurement directions `|φ₀⊥⟩,|φ₁⊥⟩,|φ₂⊥⟩`.

```text
purple = candidate quantum states
red = measurement directions
```

They are not the same concept.

10. A Simple Measurement Strategy from the Text

Bob chooses `k ∈ {0,1,2}` uniformly at random and measures in the orthogonal basis `{|φₖ⟩,|φₖ⊥⟩}`. This tests whether the received qubit lies along the candidate direction `|φₖ⟩` or its orthogonal direction.

11. Bob's Decision Rule

If the outcome is `|φₖ⟩`, Bob guesses `ℓ=k`. If it is `|φₖ⊥⟩`, he rules out `k` and randomly chooses one of the other two trits.

12. Success Probability of the Simple Strategy

Case 1: k Equals the True Trit ℓ

This occurs with probability `1/3`. Measuring `|φℓ⟩` in its own basis succeeds with probability 1, contributing `(1/3)×1`.

Case 2: k Does Not Equal ℓ

This occurs with probability `2/3`. The probability of obtaining `|φₖ⊥⟩` is `3/4`; Bob then guesses correctly among the two remaining trits with probability `1/2`. The contribution is:

`(2/3)×(3/4)×(1/2)`

13. Total Success Probability

```text
P_success = (1/3)×1 + (2/3)×(3/4)×(1/2)
          = 1/3 + 1/4
          = 7/12 ≈ 58.3%
```

14. Why Does 7/12 Already Demonstrate a Qubit Advantage?

The optimal classical worst-case probability is `1/2`, while this simple qubit strategy achieves `7/12`. Since `58.3% > 50%`, at least one qubit strategy outperforms every classical-bit strategy under this metric.

15. But 7/12 Is Not Optimal

The text then shows that a better measurement can raise the success probability. The role of `7/12` is to establish a quantum advantage before deriving the optimal symmetric POVM result.

16. Complete Communication Process

```text
Alice receives trit 0/1/2
→ encodes it as one of three qubit states
→ sends the qubit to Bob
→ Bob chooses a measurement
→ obtains an outcome
→ uses the outcome to guess the original trit
```

17. Core Difference

A classical bit has only two perfectly distinguishable encodings, while Alice has three possible inputs. A qubit is also two-dimensional and cannot provide three pairwise orthogonal states, but it can use nonorthogonal states, probability amplitudes, phase, and quantum measurement to encode the three inputs more evenly.

Thus, for some task metrics:

`P_qubit > P_bit`

18. One-Sentence Summary

A qubit cannot transmit a trit perfectly because a two-dimensional Hilbert space has no three pairwise orthogonal states. However, encoding the trits as three symmetric nonorthogonal states and using an appropriate measurement yields a worst-case success probability greater than that of a classical bit.

```text
P_worst(bit) = 1/2 = 50%
simple qubit strategy: P_success = 7/12 ≈ 58.3%
symmetric POVM: P_success = 2/3 ≈ 66.7%
```

The trine projectors satisfy:

`Σᵢ|ψᵢ⟩⟨ψᵢ|=(3/2)I`

Defining `$E_i=(2/3)|\psi_i\rangle\langle\psi_i|$` gives `$\Sigma_iE_i=I$` and:

`P(i|i)=2/3=66.7%`

