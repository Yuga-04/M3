Here is a **clean, well-organized, exam-ready answer (13 marks)** for:

# **Explain deleteOne() and deleteMany() in MongoDB with examples. (13 Marks)**

---

# **1. deleteOne() – Delete a Single Document**

**Syntax:**

```js
db.collection.deleteOne(filter);
```

### **Meaning:**

* Deletes the **first document** that matches the filter condition.

### **Example:**

```js
const { MongoClient } = require('mongodb');
const client = new MongoClient('mongodb://localhost:27017');
const dbName = 'collegeDB';

async function deleteSingle() {
    await client.connect();
    console.log("Connected successfully to server");

    const db = client.db(dbName);
    const collection = db.collection('students');

    const result = await collection.deleteOne({ name: "Anita" });
    console.log("Documents deleted:", result.deletedCount);

    client.close();
}

deleteSingle();
```

### **Explanation:**

* The filter `{ name: "Anita" }` is used.
* Only one matching document is deleted.
* `deletedCount` confirms how many documents were removed.

---

# **2. deleteMany() – Delete Multiple Documents**

**Syntax:**

```js
db.collection.deleteMany(filter);
```

### **Meaning:**

* Deletes **all documents** that match the filter.

### **Example:**

```js
const { MongoClient } = require('mongodb');
const client = new MongoClient('mongodb://localhost:27017');
const dbName = 'collegeDB';

async function deleteMultiple() {
    await client.connect();

    const db = client.db(dbName);
    const collection = db.collection('students');

    const result = await collection.deleteMany({ course: "BCA" });
    console.log("Documents deleted:", result.deletedCount);

    client.close();
}

deleteMultiple();
```

### **Explanation:**

* The filter `{ course: "BCA" }` matches multiple documents.
* All are removed.
* `deletedCount` returns number of deleted documents.

---

# **3. Comparison Table**

| Method           | Purpose                            | Example             | Deletes          |
| ---------------- | ---------------------------------- | ------------------- | ---------------- |
| **deleteOne()**  | Deletes the first matched document | `{ name: "Anita" }` | First match only |
| **deleteMany()** | Deletes all matched documents      | `{ course: "BCA" }` | All matches      |

---

# **4. Output Example**

```
Connected successfully to server
Documents deleted: 3
```

---

# **5. Advantages**

* Allows targeted or bulk deletion.
* Ensures data consistency.
* Can include conditional filters for safety.

---

# **Conclusion**

* **deleteOne()** → removes a single matching document.
* **deleteMany()** → removes all matching documents.
* Both return **deletedCount** to confirm deletions.

---

If you want, I can format this answer into **10 marks**, **8 marks**, or **short notes** style.
