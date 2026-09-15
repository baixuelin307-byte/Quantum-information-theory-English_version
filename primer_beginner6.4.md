6.4 Product States

1. What Is a Tensor Product?

To combine the states of two subsystems into a larger quantum system, we use the **tensor product**, denoted by `⊗`.

`|0⟩ ⊗ |1⟩ = |01⟩`

Here, the first qubit is in `|0⟩`, the second is in `|1⟩`, and their joint state is `|01⟩`.

2. Vector Form of the Tensor Product

```text
|0⟩ = [1, 0]ᵀ
|1⟩ = [0, 1]ᵀ
```

Therefore:

```text
|0⟩ ⊗ |1⟩ = [0, 1, 0, 0]ᵀ = |01⟩
```

Dimensions multiply:

```text
2-dimensional ⊗ 2-dimensional → 4-dimensional
n qubits → a 2^n-dimensional state vector
```

3. General Form

Let:

`|ψ⟩ = α0|0⟩ + α1|1⟩`

`|φ⟩ = β0|0⟩ + β1|1⟩`

Then:

```text
|ψ⟩ ⊗ |φ⟩
= α0β0|00⟩ + α0β1|01⟩
+ α1β0|10⟩ + α1β1|11⟩
```

with state vector `[α0β0, α0β1, α1β0, α1β1]ᵀ`.

4. What Is a Product State?

If a multi-qubit state can be written as a tensor product of subsystem states, it is a **product state**.

`|01⟩ = |0⟩ ⊗ |1⟩`

A product state can therefore be decomposed into independent subsystem states.

5. “Assembling” and “Separating”

```text
subsystem 1 ⊗ subsystem 2 → whole system
|0⟩ ⊗ |1⟩ → |01⟩
```

The reverse decomposition is possible for product states.

6. Computational-Basis Tensor Products

```text
|00⟩ = |0⟩ ⊗ |0⟩ = [1,0,0,0]ᵀ
|01⟩ = |0⟩ ⊗ |1⟩ = [0,1,0,0]ᵀ
|10⟩ = |1⟩ ⊗ |0⟩ = [0,0,1,0]ᵀ
|11⟩ = |1⟩ ⊗ |1⟩ = [0,0,0,1]ᵀ
```

These form the computational basis of a two-qubit system.

7. Tensor Product and Kronecker Product

In quantum information, **tensor product** describes the composition of systems. In matrix calculations it is implemented as the **Kronecker product**:

```text
A ⊗ B = [a11B  a12B
         a21B  a22B]
```

8. Not Every Multi-Qubit State Is a Product State

The Bell state:

`(|00⟩ + |11⟩)/√2`

cannot be written as `|ψ⟩ ⊗ |φ⟩`. It is therefore an **entangled state**.

```text
Product state = decomposable
Entangled state = not decomposable
```

9. Relationship to Subsystems

```text
Subsystem viewpoint: whole system → focus on one part
Tensor product: subsystems → combine into a whole system
```

10. Core Summary

```text
Tensor Product (⊗)
│
├── combines quantum subsystems
├── |0⟩ ⊗ |1⟩ = |01⟩
├── dimensions multiply: 2 × 2 = 4
├── decomposable whole state → product state
└── nondecomposable whole state → entangled state
```

1. A tensor product combines quantum subsystems into a larger system.
2. `|0⟩ ⊗ |1⟩ = |01⟩` assembles two single-qubit states into a two-qubit state.
3. A multi-qubit state is a product state if it factors into subsystem states.
4. Product states can be separated; entangled states cannot.
5. The state vector of n qubits has dimension `2^n`.

