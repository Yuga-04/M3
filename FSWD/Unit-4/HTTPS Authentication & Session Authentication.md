Here is a clean, well-structured **13-mark answer** based on the text in your screenshots.
(I've rewritten it neatly and in exam-ready format.)

---

# **Q14. Describe Basic HTTPS Authentication and Session Authentication in ExpressJS. (13 Marks)**

ExpressJS supports multiple authentication methods. Two commonly used techniques are **Basic HTTPS Authentication** and **Session-based Authentication**.

---

## **1. Basic HTTPS Authentication**

*(6 marks)*

### **Definition:**

Basic Authentication is the simplest authentication method where the client sends a username and password encoded in **Base64** through the HTTP `Authorization` header.

---

### **Working:**

1. The client sends credentials using the `Authorization` header.

   * Format:

     ```
     Authorization: Basic base64(username:password)
     ```
2. The server decodes the Base64 string.
3. If the username and password match the server’s stored values, access is granted.
4. Otherwise, the server returns a **401 Unauthorized** response.

---

### **Example (ExpressJS Code):**

```js
const express = require('express');
const app = express();

app.get('/', (req, res) => {
    const auth = { login: 'admin', password: '1234' };

    const b64auth = (req.headers.authorization || '').split(' ')[1] || '';
    const [login, password] = Buffer.from(b64auth, 'base64').toString().split(':');

    if (login === auth.login && password === auth.password) {
        res.send('Access Granted: Welcome Admin!');
    } 
    else {
        res.set('WWW-Authenticate', 'Basic realm="401"');
        res.status(401).send('Authentication Required.');
    }
});

app.listen(3000, () => console.log('Server running on http://localhost:3000'));
```

---

### **Advantages:**

* Very simple to implement.
* Does not require cookies or session storage.

### **Disadvantages:**

* Credentials are sent with every request (risk of exposure).
* Must be used with **HTTPS**; otherwise, credentials can be intercepted.

---

## **2. Session Authentication**

*(7 marks)*

### **Definition:**

Session-based authentication stores user information on the server after a successful login. A **session ID** is sent to the client in a cookie, and this ID is used to validate the user's identity for future requests.

---

### **Steps:**

1. Install required packages:

   ```
   npm install express express-session cookie-parser
   ```

---

### **Example (ExpressJS Code):**

```js
const express = require('express');
const session = require('express-session');
const app = express();

app.use(session({
    secret: 'mysecretkey',
    resave: false,
    saveUninitialized: true
}));

app.get('/login', (req, res) => {
    req.session.user = 'Admin';
    res.send('User logged in successfully.');
});

app.get('/dashboard', (req, res) => {
    if (req.session.user) {
        res.send(`Welcome ${req.session.user}, to the Dashboard.`);
    } 
    else {
        res.send('Please login first.');
    }
});

app.listen(3000, () => console.log('Server running...'));
```

---

### **Advantages:**

* More secure than Basic Authentication.
* Credentials are sent only once during login.
* Server-side session storage prevents tampering by clients.

### **Disadvantages:**

* Requires additional server resources to manage sessions.
* Cookies must be enabled in the browser.

---

If you'd like, I can also format this into a **15-mark version** or a **very short exam answer**.
