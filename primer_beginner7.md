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

# $|\Phi^+\rangle = \frac{1}{\sqrt2}\left(|00\rangle+|11\rangle\right)$

Bob keeps the second qubit and sends the first qubit to Alice.

Therefore, Alice and Bob now share an entangled state.

```text
Alice                         Bob

first qubit  ← entangled →  second qubit



## Superdense Coding Process

1. Bob prepares a pair of entangled qubits.

   ↓

2. Bob keeps one qubit and sends the other qubit to Alice.

   ↓

3. Alice and Bob agree on the encoding rule in advance:

   - `00` → apply \(I\)
   - `01` → apply \(Z\)
   - `10` → apply \(X\)
   - `11` → apply \(XZ\)

   ↓

4. Alice applies the corresponding operation according to her two classical bits.

   ↓

5. The original Bell state is transformed into a different Bell state.

   ↓

6. Alice sends her qubit back to Bob.

   ↓

7. Bob performs a Bell measurement on the two qubits.

   ↓

8. Bob identifies which Bell state he obtained and recovers Alice's original two classical bits:

   `00 / 01 / 10 / 11`


1. Alice and Bob initially each hold one qubit.

2. The two qubits are jointly in a **Bell state**.

3. Alice applies an operation only to her own qubit.

4. Because the two qubits are entangled, Alice's operation changes the **joint Bell state of the two qubits**.

5. Alice sends her qubit to Bob.

6. Bob now holds both qubits and performs a Bell-state measurement to determine which Bell state the two qubits are in.
