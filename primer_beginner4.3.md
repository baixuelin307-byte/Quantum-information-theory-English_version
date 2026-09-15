# 4.3 Other State Distinguishing Problems

Section 4.3 mainly explains that:

> **State discrimination is not limited to the simple examples introduced earlier; it can be extended to more general quantum states.**

This section does not introduce a complete new general solution. Instead, it supplements the earlier discussion with other possible cases and uses exercises to build familiarity with state discrimination.

---

## 1. The Two Candidate States Can Be More General

The earlier discussion focused mainly on:

$|0\rangle$ vs. $|+\rangle$

Section 4.3 begins to consider more general pairs of states, such as:

$\cos\theta|0\rangle+\sin\theta|1\rangle$

and

$\cos\theta|0\rangle-\sin\theta|1\rangle$

In other words, the relationship between two states need not have the same fixed form as in the earlier examples.

---

## 2. Start by Examining the Inner Product

If it is unclear how to begin analyzing two candidate states, first calculate:

$|\langle\psi|\phi\rangle|$

This quantity indicates how close the two states are.

If:

$|\langle\psi|\phi\rangle|=0$

the states are orthogonal and can be distinguished perfectly.

If:

$|\langle\psi|\phi\rangle|\neq0$

the states are nonorthogonal and cannot be distinguished perfectly.

In general:

> **The larger the absolute value of the inner product, the closer the two states are and the harder they are to distinguish.**

---

## 3. Amplitudes Can Be Complex Numbers

In most earlier examples, the amplitudes of the quantum states were real numbers, such as:

$\frac{1}{\sqrt{2}}$

or:

$-\frac{1}{\sqrt{2}}$

However, amplitudes can also be complex numbers. For example:

$\frac{i}{\sqrt{2}}|0\rangle+\frac{1}{\sqrt{2}}|1\rangle$

where:

$i=\sqrt{-1}$

State discrimination must therefore also handle quantum states with complex amplitudes and phases.

In this case, the simple two-dimensional “upper-right/lower-right” diagram cannot completely represent the quantum state.

---

## 4. There Can Be More Than Two Candidate States

State discrimination is not necessarily a binary-choice problem.

For example, an unknown state might be one of four candidates:

$|0\rangle,\ |1\rangle,\ |+\rangle,\ |-\rangle$

With completely random guessing, the probability of success is only:

$\frac{1}{4}$

because there are four choices.

An appropriate measurement procedure can produce a success probability greater than random guessing. However:

> **State discrimination generally becomes more complicated as the number of candidate states increases.**

---

## 5. Main Purpose of Section 4.3

Section 4.3 does not propose a new complete algorithm. Instead, it shows that state discrimination extends to many settings, including:

- two quantum states of a general form
- quantum states separated by different angles
- quantum states with complex amplitudes
- three, four, or more candidate states

The overall logic remains unchanged:

`candidate quantum states → design a measurement → obtain a measurement outcome → infer the original state → maximize the probability of success`

---

## One-Sentence Summary

> **Section 4.3 broadens the scope of state discrimination rather than introducing a detailed new solution method.**
