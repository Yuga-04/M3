Here is a **clean, well-organized, exam-ready 13-mark answer** for:

# **Q13. How do you connect MongoDB database in a NodeJS application? (13 Marks)**

---

# **1. Install the MongoDB Driver**

To connect NodeJS with MongoDB, first install the official MongoDB Node.js driver:

```bash
npm install mongodb
```

---

# **2. Import MongoClient**

MongoClient is used to connect to the MongoDB server.

```js
const { MongoClient } = require('mongodb');
```

---

# **3. Define the Connection URL and Database Name**

```js
const url = 'mongodb://localhost:27017';
const dbName = 'studentDB';
const client = new MongoClient(url);
```

* `url` → Location of MongoDB server
* `dbName` → Name of the database to use

---

# **4. Connect to MongoDB and Perform an Operation**

Below is a short and clear example that connects to MongoDB and inserts one document:

```js
async function main() {
    await client.connect(); 
    console.log("Connected successfully to MongoDB");

    const db = client.db(dbName);
    const collection = db.collection('students');

    const result = await collection.insertOne({
        name: 'Rahul',
        age: 22,
        course: 'B.Tech'
    });

    console.log("Data inserted successfully:", result.insertedId);

    client.close();
}

main().catch(console.error);
```

---

# **5. Explanation of Key Steps**

* **MongoClient.connect()** → Establishes the connection between Node.js and MongoDB.
* **db.collection('name')** → Accesses or creates a collection.
* After connection, you can perform CRUD operations:

  * `insertOne()` → Insert a document
  * `find()` → Read documents
  * `updateOne()` → Update a document
  * `deleteOne()` → Delete a document

---

# **6. Sample Output**

```
Connected successfully to MongoDB
Data inserted successfully: 670dfc8e4b01c9b9b4f8c4a5
```

---

# **7. Advantages of Connecting MongoDB with NodeJS**

* Both use JavaScript → same language for backend and database logic.
* Highly scalable for real-time applications.
* Supports asynchronous, non-blocking I/O operations.

---

If you'd like, I can also compress this answer into a **10-mark** or **8-mark** format.

