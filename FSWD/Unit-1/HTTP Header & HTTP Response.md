

## 💻 **Structure of HTTP Request & HTTP Response with Example**

### 🌐 Introduction

The **HyperText Transfer Protocol (HTTP)** is the foundation of data communication on the **World Wide Web (WWW)**.
It follows a **client–server model**, where the client (web browser) sends an **HTTP Request**, and the server replies with an **HTTP Response**.

---

### ⚙️ **1️⃣ HTTP Request Message Structure**

An **HTTP Request** is sent by the client to request data or perform an action on the server.

#### 🔹 General Structure:

```
<Start Line>
<Header Fields>
<Blank Line>
<Message Body>
```

#### 📘 Components Explained:

| Part              | Description                                                                                                     |
| ----------------- | --------------------------------------------------------------------------------------------------------------- |
| **Start Line**    | Specifies the **method**, **URL**, and **HTTP version**. Example: `GET /index.html HTTP/1.1`                    |
| **Header Fields** | Provide additional information like data type, host, and encoding. Each line is in `Header-Name: Value` format. |
| **Blank Line**    | Separates the headers from the body.                                                                            |
| **Message Body**  | Optional part containing data (mainly for POST and PUT methods).                                                |

#### ⚡ Common HTTP Methods

| Method      | Action                             |
| ----------- | ---------------------------------- |
| **GET**     | Request data from the server       |
| **POST**    | Send data to the server            |
| **PUT**     | Update a resource on the server    |
| **DELETE**  | Remove a resource                  |
| **HEAD**    | Same as GET but without body       |
| **OPTIONS** | Ask server about supported methods |

#### 🧠 Example – HTTP Request

```
GET /index.html HTTP/1.1
Host: www.example.com
Accept: text/html
Accept-Language: en-US
Connection: keep-alive
```

---

### ⚙️ **2️⃣ HTTP Response Message Structure**

An **HTTP Response** is sent by the server after processing the client’s request.

#### 🔹 General Structure:

```
<Status Line>
<Header Fields>
<Blank Line>
<Message Body>
```

#### 📘 Components Explained:

| Part              | Description                                                                        |
| ----------------- | ---------------------------------------------------------------------------------- |
| **Status Line**   | Indicates HTTP version, status code, and reason phrase. Example: `HTTP/1.1 200 OK` |
| **Header Fields** | Give extra information such as content type, date, or length.                      |
| **Blank Line**    | Separates headers from the body.                                                   |
| **Message Body**  | Contains the actual content (HTML, JSON, etc.) sent to the client.                 |

#### ⚡ Common Status Codes

| Code                          | Meaning                      |
| ----------------------------- | ---------------------------- |
| **200 OK**                    | Request successful           |
| **301 Moved Permanently**     | Resource moved to a new URL  |
| **400 Bad Request**           | Client sent invalid request  |
| **401 Unauthorized**          | Authentication required      |
| **404 Not Found**             | Requested resource not found |
| **500 Internal Server Error** | Generic server error         |

#### 🧠 Example – HTTP Response

```
HTTP/1.1 200 OK
Date: Mon, 13 Oct 2025 18:30:00 GMT
Content-Type: text/html
Content-Length: 1256
Connection: keep-alive

<html>
<head><title>Welcome</title></head>
<body><h1>Hello, World!</h1></body>
</html>
```

---

### 🧩 **3️⃣ Summary Table**

| Aspect           | HTTP Request           | HTTP Response                  |
| ---------------- | ---------------------- | ------------------------------ |
| **Initiated by** | Client (Browser)       | Server                         |
| **Purpose**      | To request data        | To deliver data                |
| **Start Line**   | Method + URL + Version | Version + Status Code + Phrase |
| **Headers**      | Give request info      | Give response info             |
| **Body**         | Optional (POST data)   | Contains content               |

---

### 🧾 **4️⃣ Example Flow**

1. **Client (Browser)** sends request:

   ```
   GET /home.html HTTP/1.1
   Host: www.example.com
   ```
2. **Server** responds:

   ```
   HTTP/1.1 200 OK
   Content-Type: text/html

   <html><body>Welcome!</body></html>
   ```

---

### 🏁 **Conclusion**

* HTTP uses a **request–response** model.
* The client sends a **request message**, and the server replies with a **response message**.
* Together, they form the core mechanism of how web pages are transmitted over the Internet.
