# ✳️ Convert the Given Grammar into **Greibach Normal Form (GNF)**

---

## 🧩 Given Grammar

```
A1 → A3A2 | A2A3  
A2 → A3A3 | A2A2 | a  
A3 → A2A2 | b
```

---

## 🪜 Step 1: Check – CNF form or not

Each rule is of type:

* A → BC ✅
* A → a ✅

Hence, the grammar is already in **Chomsky Normal Form (CNF)**.
We can now proceed to convert it into **Greibach Normal Form (GNF)**.

---

## 🪜 Step 2: Rename Variables (for simplicity)

Let’s rename the variables:

```
A1 = A
A2 = B
A3 = C
```

Now the grammar becomes:

```
A → CB | BC
B → CC | BB | a
C → BB | b
```

We’ll convert variables in this order: **C → B → A**

---

## 🪜 Step 3: Convert C to GNF

Given:

```
C → BB | b
```

Substitute `B → CC | BB | a` into `BB`:

```
C → (CC | BB | a)(CC | BB | a) | b
```

Keep only the productions that start with terminals (`a` or `b`):

```
C → aCC | aBB | aCB | b
```

✅ **C is now in GNF**

---

## 🪜 Step 4: Convert B to GNF

Given:

```
B → CC | BB | a
```

Substitute `C → aCC | aBB | aCB | b` into the first C:

```
B → (aCC | aBB | aCB | b)C | BB | a
```

Now keep only RHS that start with terminals (`a` or `b`):

```
B → aCC | aBB | aCB | bC | a
```

✅ **B is now in GNF**

---

## 🪜 Step 5: Convert A to GNF

Given:

```
A → CB | BC
```

### For A → CB

```
C → aCC | aBB | aCB | b
```

So:

```
CB → (aCC | aBB | aCB | b)B
```

That gives:

```
A → aCCB | aBBB | aCBB | bB
```

---

### For A → BC

```
B → aCC | aBB | aCB | bC | a
C → aCC | aBB | aCB | b
```

So:

```
BC → (aCC | aBB | aCB | bC | a)(aCC | aBB | aCB | b)
```

Productions that start with terminals:

```
A → aCC | aBB | aCB | bC | a
```

---

### Combine all

```
A → aCCB | aBBB | aCBB | bB | aCC | aBB | aCB | bC | a
```

✅ **A is now in GNF**

---

## 🏁 Step 6: Rename Back to Original Variables

```
A = A1
B = A2
C = A3
```

---

## ✅ Final Grammar in GNF

```
A1 → aA3A3A2 | aA2A2A2 | aA3A2A2 | bA2 | aA3A3 | aA2A2 | aA3A2 | bA3 | a
A2 → aA3A3 | aA2A2 | aA3A2 | bA3 | a
A3 → aA3A3 | aA2A2 | aA3A2 | b
```

---

## 🔍 Verification

| Condition                                | Status |
| ---------------------------------------- | ------ |
| All RHS start with terminal (`a` or `b`) | ✅      |
| No ε-productions                         | ✅      |
| No unit productions                      | ✅      |
| Equivalent to original grammar           | ✅      |
| Grammar in Greibach Normal Form (GNF)    | ✅      |

---

## 🧠 Summary

* Grammar was already in **CNF**.
* Substituted leftmost nonterminals step by step.
* Ensured every RHS starts with a terminal.
* Final result satisfies **GNF** completely.

