Perfect ✅ Yuga — this is a **frequently asked 15-mark question** in *Compiler Design / TOC exams*:

> “Explain in detail about the role of lexical analyzer with the possible error recovery actions.”

Here’s the **full-mark structured answer**, written exactly like your exam notes (definition ➜ functions ➜ working ➜ error handling ➜ conclusion).

---

# ✳️ **Role of Lexical Analyzer and Error Recovery Actions**

---

## 🔹 **Definition**

A **Lexical Analyzer** (also called **Scanner**) is the **first phase of a compiler**.
Its main role is to **read the source code** character by character and **convert** it into a sequence of **tokens** that can be understood by the next phase (Syntax Analyzer or Parser).

---

## 🔹 **Position of Lexical Analyzer in Compiler**

```
Source Program
     ↓
Lexical Analyzer → Tokens → Syntax Analyzer → Semantic Analyzer → Code Generation
```

The **Lexical Analyzer** acts as a **bridge** between the source program and the parser.

---

## 🔹 **Main Roles / Functions of Lexical Analyzer**

| Function                                | Description                                                                                                  |
| :-------------------------------------- | :----------------------------------------------------------------------------------------------------------- |
| **1. Scanning / Reading Input**         | Reads the source program character by character.                                                             |
| **2. Tokenization**                     | Groups characters into meaningful sequences called **tokens** (like keywords, identifiers, operators, etc.). |
| **3. Removing Whitespace and Comments** | Ignores blank spaces, tabs, and comments.                                                                    |
| **4. Maintaining Symbol Table**         | Stores identifiers, constants, and their attributes (data type, address, etc.).                              |
| **5. Communication with Parser**        | Sends the next token to the parser when requested.                                                           |
| **6. Error Detection and Recovery**     | Detects lexical errors such as invalid characters or malformed numbers and recovers gracefully.              |

---

## 🔹 **Token Representation**

Each token is represented as a **pair:**
[
<token-name, attribute-value>
]
Example:

```
id, x
num, 20
relop, ≤
```

---

## 🔹 **Example**

Input Code:

```c
sum = a + b * 5;
```

Output Tokens by Lexical Analyzer:

| Lexeme | Token         |
| :----- | :------------ |
| sum    | <id,1>        |
| =      | <assign,->    |
| a      | <id,2>        |
| +      | <plus,->      |
| b      | <id,3>        |
| *      | <mul,->       |
| 5      | <num,5>       |
| ;      | <semicolon,-> |

---

## 🔹 **Architecture of Lexical Analyzer**

```
          ┌──────────────────────┐
Source →  │  Lexical Analyzer   │  → Tokens
Program   │ (Scanner / Lexer)   │
          └──────────────────────┘
                  ↓
           Symbol Table
                  ↓
           Error Handling
```

---

## 🔹 **Interaction with Symbol Table**

* Every **identifier or literal** recognized by the lexer is entered in the **symbol table**.
* The **attribute-value** in the token points to its corresponding symbol table entry.

Example:

| Symbol | Type  | Value |
| :----- | :---- | :---- |
| x      | int   | 10    |
| y      | float | 5.2   |

---

## 🔹 **Lexical Errors**

Lexical errors occur when the lexical analyzer cannot recognize a sequence of characters as a valid token.

### 🔸 Common Types of Lexical Errors:

1. **Invalid Characters**
   → Example: `@`, `#` in normal code.
2. **Unclosed Strings**
   → Example: `"Hello`
3. **Malformed Numbers**
   → Example: `12.34.56`
4. **Invalid Identifier Names**
   → Example: `9abc` (cannot start with digit)
5. **Extra or Missing Characters**
   → Example: `intt` instead of `int`

---

# ✳️ **Error Recovery Actions in Lexical Analysis**

The goal of **error recovery** is not just to detect errors but to **continue scanning** the rest of the program to report more errors instead of stopping.

---

## 🔹 **Common Error Recovery Strategies**

| Method                                 | Description                                                                                                   | Example                              |
| :------------------------------------- | :------------------------------------------------------------------------------------------------------------ | :----------------------------------- |
| **1. Panic Mode Recovery**             | The analyzer skips all input symbols until it finds a known delimiter (like `;` or `}`) and resumes scanning. | On detecting `@`, skip to next `;`.  |
| **2. Deletion of Extra Characters**    | Removes unwanted or illegal characters and continues scanning.                                                | `inta` → remove `a`, treat as `int`. |
| **3. Insertion of Missing Characters** | Inserts a missing character if the context makes it clear.                                                    | `flo at` → insert `o` → `float`.     |
| **4. Substitution of Characters**      | Replaces an incorrect character with the most probable one.                                                   | `fi` → replace `i` with `f` → `if`.  |
| **5. Transposition of Characters**     | Corrects two adjacent interchanged characters.                                                                | `fi` → swap → `if`.                  |

---

## 🔹 **Example:**

Source Code:

```c
intt x = 10
```

Lexical Analyzer detects:

* Invalid token `intt`
* Possible recovery: delete extra `t` and continue as `int`.

---

## 🔹 **Role of Error Recovery**

* Ensures **compiler continues** scanning after an error.
* Prevents multiple cascading errors.
* Helps **report more errors in one compilation**.
* Improves overall **user experience** in debugging.

---

## 🔹 **Conclusion**

The **Lexical Analyzer** plays a vital role as the **foundation phase** of compilation.
It transforms raw source code into a clean stream of tokens, manages the symbol table, and handles lexical errors using efficient recovery strategies.

Thus, it ensures that only **syntactically valid tokens** are passed to the parser, making the rest of compilation faster and more reliable.

---

### 🟩 **Marks Distribution (15 Marks)**

| Section                | Description                      |     Marks    |
| :--------------------- | :------------------------------- | :----------: |
| Definition & Role      | Overview + Diagram               |       3      |
| Functions              | Tokenization, symbol table, etc. |       4      |
| Lexical Errors         | Types and examples               |       3      |
| Error Recovery Methods | Table + explanation              |       4      |
| **Total**              |                                  | **15 Marks** |

---

Would you like me to add a **block diagram of the Lexical Analyzer** (with arrows to symbol table and parser) for your notes? It helps score full marks when you include it visually.
