
# 💻 **If, Else, Ternary Operator, and Switch Statement in JavaScript**

---

## 🌐 **Introduction**

In **JavaScript**, **decision-making statements** are used to execute different blocks of code depending on certain conditions.
They help control the flow of a program based on **boolean expressions** (true or false).

The major conditional statements are:

1. `if` statement
2. `if–else` statement
3. `if–else if` ladder
4. **Ternary (Conditional) Operator**
5. **Switch statement**

---

## ⚙️ **1️⃣ if Statement**

### 📘 **Definition**

The **if statement** is used to test a condition.
If the condition is **true**, the statements inside the `if` block are executed.

### 🧠 **Syntax**

```javascript
if (condition) {
   // statements to execute if condition is true
}
```

### 💡 **Example**

```javascript
let age = 18;

if (age >= 18) {
   console.log("You are eligible to vote.");
}
```

### ✅ **Output**

```
You are eligible to vote.
```

**Explanation:**
Since `age >= 18` is **true**, the message is displayed.

---

## ⚙️ **2️⃣ if–else Statement**

### 📘 **Definition**

The **if–else statement** executes one block of code if the condition is **true** and another block if it is **false**.

### 🧠 **Syntax**

```javascript
if (condition) {
   // executed if condition is true
} else {
   // executed if condition is false
}
```

### 💡 **Example**

```javascript
let number = 7;

if (number % 2 == 0) {
   console.log("Even Number");
} else {
   console.log("Odd Number");
}
```

### ✅ **Output**

```
Odd Number
```

**Explanation:**
The condition `number % 2 == 0` is **false**, so the `else` block executes.

---

## ⚙️ **3️⃣ if–else if Ladder**

### 📘 **Definition**

When there are multiple conditions to check, **if–else if ladder** is used.

### 🧠 **Syntax**

```javascript
if (condition1) {
   // code block 1
} else if (condition2) {
   // code block 2
} else {
   // default block
}
```

### 💡 **Example**

```javascript
let marks = 85;

if (marks >= 90) {
   console.log("Grade A");
} else if (marks >= 75) {
   console.log("Grade B");
} else {
   console.log("Grade C");
}
```

### ✅ **Output**

```
Grade B
```

**Explanation:**
Since `marks >= 75` is **true**, "Grade B" is printed.

---

## ⚙️ **4️⃣ Ternary Operator**

### 📘 **Definition**

The **ternary operator (`? :`)** is a shorthand for `if–else` statements.
It evaluates a condition and returns one of two values.

### 🧠 **Syntax**

```javascript
condition ? expressionIfTrue : expressionIfFalse;
```

### 💡 **Example**

```javascript
let age = 20;
let result = (age >= 18) ? "Adult" : "Minor";
console.log(result);
```

### ✅ **Output**

```
Adult
```

**Explanation:**
If the condition `age >= 18` is true, `"Adult"` is assigned; otherwise `"Minor"`.

---

## ⚙️ **5️⃣ Switch Statement**

### 📘 **Definition**

The **switch statement** is used to execute one block of code out of many options, based on the value of an expression.
It works like multiple `if–else if` conditions.

### 🧠 **Syntax**

```javascript
switch(expression) {
   case value1:
      // block of code
      break;
   case value2:
      // block of code
      break;
   default:
      // block of code if no cases match
}
```

### 💡 **Example**

```javascript
let day = 3;
let dayName;

switch (day) {
   case 1:
      dayName = "Monday";
      break;
   case 2:
      dayName = "Tuesday";
      break;
   case 3:
      dayName = "Wednesday";
      break;
   case 4:
      dayName = "Thursday";
      break;
   case 5:
      dayName = "Friday";
      break;
   case 6:
      dayName = "Saturday";
      break;
   case 7:
      dayName = "Sunday";
      break;
   default:
      dayName = "Invalid Day";
}

console.log(dayName);
```

### ✅ **Output**

```
Wednesday
```

**Explanation:**
Since `day` equals `3`, the statement under **case 3** executes.

---

## 🧩 **6️⃣ Comparison Table**

| Statement Type       | Purpose                         | Example Output      | Use Case                      |
| -------------------- | ------------------------------- | ------------------- | ----------------------------- |
| **if**               | Executes code if condition true | `You are eligible.` | Single condition check        |
| **if–else**          | Executes one of two blocks      | `Even Number`       | Binary decision               |
| **if–else if**       | Multiple condition check        | `Grade B`           | Multi-level logic             |
| **Ternary Operator** | Short form of if–else           | `Adult`             | Simple conditional assignment |
| **Switch**           | Selects from multiple cases     | `Wednesday`         | Multiple fixed options        |

---

## 🧾 **7️⃣ Key Features**

1. **Control Flow** – Directs the program based on conditions.
2. **Readable Code** – Improves clarity for multiple decisions.
3. **Performance** – Switch statements are faster for constant checks.
4. **Compact Syntax** – Ternary operator reduces code length.
5. **Scalability** – Nested if–else and switch allow complex decision-making.

---

## 🏁 **Conclusion**

* **If, else, and ternary operators** handle conditional logic efficiently.
* **Switch statements** simplify multiple option handling.
  Together, these constructs provide **decision control**, making JavaScript programs **dynamic and interactive**.


