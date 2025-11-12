Here’s a **clear and summarized explanation** of **Pretty Good Privacy (PGP)** based on your notes — ideal for quick revision or 13-mark exam answers 👇

---

## **Pretty Good Privacy (PGP)**

**Definition:**
PGP (Pretty Good Privacy) is an encryption program developed by **Philip Zimmermann** that provides **confidentiality** and **authentication** services for **electronic mail (e-mail)** and **file storage**.

---

### **Key Features**

Zimmermann’s main contributions:

1. Selected the **best cryptographic algorithms** as building blocks.
2. Integrated them into a **general-purpose, OS-independent** application.
3. Made **source code freely available** online.
4. Partnered with a company to offer a **commercial version** of PGP.

---

### **Reasons for PGP’s Popularity**

1. **Free and available worldwide** across many platforms.
2. **Highly secure** algorithms.
3. **Versatile applicability** (e-mail, files, etc.).
4. **Independent** of government or standards bodies.
5. **Adopted as an Internet standard.**

---

## **Operational Description**

PGP operation involves six major functions:

---

### **(i) Authentication**

Used to verify the sender’s identity and message integrity.

**Steps:**

1. Sender creates a message.
2. **SHA-1** generates a **160-bit hash code** of the message.
3. Hash is **encrypted with sender’s private RSA key** → forms the **digital signature**.
4. Signature is **attached (prepended)** to the message.
5. Receiver **decrypts** signature using **sender’s public key**.
6. Receiver computes a new hash and **compares** — if both match → message is authentic.

---

### **(ii) Confidentiality**

Used to ensure only the intended recipient can read the message.

**Steps:**

1. Sender creates message and a **random 128-bit session key**.
2. Message is **encrypted** using **CAST-128 (or IDEA / 3DES)** with the session key.
3. The **session key** is then **encrypted with recipient’s public RSA key** and attached to the message.
4. Receiver uses **private RSA key** to **decrypt session key**.
5. Session key is used to **decrypt the message**.

---

### **(iii) Confidentiality + Authentication**

To provide both:

* Sender first **signs** the message (authentication).
* Then **encrypts** it with session key (confidentiality).
* Finally, the **session key** is **encrypted** using recipient’s public key.

---

### **(iv) Compression**

* PGP **compresses the message after signing** but **before encryption**.
* Uses **Z** for compression and **Z-1** for decompression.

**Reasons:**

1. Signature on uncompressed data allows easy verification later.
2. Compression algorithm is **non-deterministic**, so signing compressed data is impractical.
3. **Encrypted compressed data** has less redundancy → **stronger security**.

---

### **(v) E-Mail Compatibility**

* E-mails typically can’t handle raw binary data.
* PGP converts the binary data into **ASCII** using **Radix-64 conversion**.
* Every **3 octets** → **4 ASCII characters** (≈33% size increase).
* Ensures message is safely transmitted over e-mail.

---

### **(vi) Segmentation and Reassembly**

* If a message > **50,000 octets**, it’s **broken into smaller parts** (segmented) after all processing.
* Each segment is mailed separately.
* Receiver **reassembles** segments, removes headers, and **retrieves the original message**.

---

✅ **In short:**
PGP provides:

* **Authentication** via digital signatures.
* **Confidentiality** via hybrid encryption.
* **Compression** for efficiency.
* **ASCII conversion** for e-mail transfer.
* **Segmentation** for large messages.

---

Would you like me to make this into a **formatted 13-mark answer PDF** (with diagrams for encryption/authentication flow)? It’ll be great for last-minute study notes.
