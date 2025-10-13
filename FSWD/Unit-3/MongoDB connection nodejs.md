
## Connecting MongoDB with Node.js

### 🔹 Introduction
MongoDB is a popular NoSQL database that stores data in flexible, JSON-like documents. Node.js, being asynchronous and event-driven, integrates seamlessly with MongoDB using libraries like **Mongoose** or the native **MongoDB driver**. This connection enables developers to build scalable, data-driven applications.

---

### 🔹 Prerequisites
Before connecting MongoDB to Node.js, ensure:
- Node.js is installed.
- MongoDB is installed locally or accessible via a cloud service like MongoDB Atlas.
- A project directory is initialized using `npm init`.

---

### 🔹 Step-by-Step Connection Using Mongoose

#### 1. **Install Mongoose**
```bash
npm install mongoose --save
```

#### 2. **Import Mongoose**
```javascript
const mongoose = require('mongoose');
```

#### 3. **Connect to MongoDB**
```javascript
mongoose.connect('mongodb://localhost:27017/mydatabase', {
  useNewUrlParser: true,
  useUnifiedTopology: true
});
```

#### 4. **Handle Connection Events**
```javascript
const db = mongoose.connection;

db.on('error', console.error.bind(console, 'Connection error:'));
db.once('open', () => {
  console.log('Connected to MongoDB successfully!');
});
```

---

### 🔹 Defining a Schema and Model
```javascript
const userSchema = new mongoose.Schema({
  name: String,
  email: String,
  age: Number
});

const User = mongoose.model('User', userSchema);
```

---

### 🔹 Performing CRUD Operations

#### ➤ Create
```javascript
const newUser = new User({ name: 'Ajitha', email: 'ajitha@example.com', age: 22 });
newUser.save();
```

#### ➤ Read
```javascript
User.find({}, (err, users) => {
  if (err) throw err;
  console.log(users);
});
```

#### ➤ Update
```javascript
User.updateOne({ name: 'Ajitha' }, { age: 23 });
```

#### ➤ Delete
```javascript
User.deleteOne({ name: 'Ajitha' });
```

---

### 🔹 Integration with Express.js
You can integrate MongoDB operations within Express routes:
```javascript
app.get('/users', async (req, res) => {
  const users = await User.find();
  res.json(users);
});
```

---

### 🔹 Benefits of Using MongoDB with Node.js
- **Asynchronous I/O**: Node.js handles MongoDB operations without blocking.
- **JSON Compatibility**: Both use JSON-like formats, simplifying data exchange.
- **Scalability**: Ideal for real-time apps and microservices.
- **Modularity**: Promotes clean separation of concerns using models and routes.

---

### 🔹 Conclusion
Connecting MongoDB to Node.js empowers developers to build dynamic, scalable applications. With tools like Mongoose and Express.js, the integration becomes seamless, allowing efficient data handling and robust backend development.
