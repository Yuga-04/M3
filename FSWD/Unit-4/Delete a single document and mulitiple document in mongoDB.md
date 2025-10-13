---

## 🗑️ Deleting Documents in MongoDB Using Node.js

### 🔹 Introduction
MongoDB is a NoSQL database that stores data in flexible JSON-like documents. In Node.js applications, MongoDB operations are typically handled using the **Mongoose** library or the **native MongoDB driver**. Deleting documents is a key part of CRUD operations, allowing developers to remove unwanted or obsolete data.

---

## 🔸 1. Setup: Connecting MongoDB in Node.js

Before performing delete operations, connect to MongoDB:

```js
const mongoose = require('mongoose');
mongoose.connect('mongodb://localhost:27017/mydb');
```

Define a schema and model:

```js
const userSchema = new mongoose.Schema({ name: String, age: Number });
const User = mongoose.model('User', userSchema);
```

---

## 🔸 2. Deleting a Single Document

### ✅ Method: `deleteOne()`

Deletes the **first matching document** based on the filter.

```js
User.deleteOne({ name: 'Ajitha' }, (err) => {
  if (err) console.error(err);
  else console.log('One document deleted');
});
```

### ✅ Method: `findOneAndDelete()`

Finds and deletes a document, and returns the deleted document.

```js
User.findOneAndDelete({ name: 'Ajitha' }, (err, doc) => {
  if (err) console.error(err);
  else console.log('Deleted:', doc);
});
```

---

## 🔸 3. Deleting Multiple Documents

### ✅ Method: `deleteMany()`

Deletes **all documents** that match the filter.

```js
User.deleteMany({ age: { $lt: 18 } }, (err) => {
  if (err) console.error(err);
  else console.log('Multiple documents deleted');
});
```

---

## 🔸 4. Error Handling and Confirmation

Always handle errors and confirm deletion:

```js
User.deleteOne({ name: 'Ajitha' })
  .then(result => console.log(result.deletedCount))
  .catch(err => console.error(err));
```

---

## 🔸 5. Summary Table

| Method               | Purpose                          | Returns         |
|----------------------|----------------------------------|------------------|
| `deleteOne()`        | Deletes first matching document  | Result object    |
| `findOneAndDelete()` | Deletes and returns the document | Deleted document |
| `deleteMany()`       | Deletes all matching documents   | Result object    |

---

## 🔸 Conclusion

MongoDB provides flexible methods to delete single or multiple documents using Node.js. These operations are essential for maintaining clean and relevant datasets. With proper error handling and confirmation, developers can ensure safe and efficient data deletion.

---
