# 7. Superdense Coding

Superdense coding is a quantum communication protocol showing how **entanglement can enhance communication**.

The key result is:

$$
\boxed{2\text{ classical bits} \longrightarrow 1\text{ transmitted qubit}}
$$

This does **not** mean that an ordinary qubit can directly carry two classical bits.  
The protocol works because Alice and Bob **share an entangled pair of qubits in advance**.

---

## 7.1 Prelude to Superdense Coding

Suppose Alice receives two classical bits

$$
a,b\in\{0,1\}
$$

so her input is one of

$$
ab\in\{00,01,10,11\}.
$$

Bob wants to determine both bits.

### Sending One Classical Bit

If Alice can send only one classical bit to Bob, the best success probability is

$$
P_{\text{success}}=\frac{1}{2}.
$$

For example, Alice can send $a$. Bob then knows $a$ exactly but must guess $b$.

Therefore,

$$
P_{\text{success}}=\frac12.
$$

---

### Sending One Qubit

What if Alice sends one qubit instead of one classical bit?

This still does not solve the problem. Without shared entanglement, the best success probability remains

$$
P_{\text{success}}=\frac12.
$$

Therefore, simply replacing one classical bit with one qubit is not enough to transmit two classical bits perfectly.

---

### Communication in the Wrong Direction

Suppose Bob first sends one classical bit to Alice, and Alice then sends one bit back to Bob.

The success probability is still

$$
P_{\text{success}}=\frac12.
$$

This is because Bob initially has no information about Alice's bits $a$ and $b$, so the bit he sends cannot contain useful information about them.

Even if Bob sends one classical bit to Alice and Alice sends one qubit back, the best success probability is still

$$
\frac12.
$$

However, the situation changes if Bob sends Alice **one half of an entangled pair**.

This is the key idea behind superdense coding.

---

# 7.2 How Superdense Coding Works

Superdense coding uses three main steps.

## Step 1: Bob Creates an Entangled Pair

Bob prepares the Bell state



# Bell State

$$
|\Phi^+\rangle
=
\frac{1}{\sqrt2}
\left(
|00\rangle+|11\rangle
\right)
$$

Bob keeps the second qubit and sends the first qubit to Alice.

Therefore, Alice and Bob now share an entangled state.

```text
Alice                         Bob

first qubit  ← entangled →  second qubit
