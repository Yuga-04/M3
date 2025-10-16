

## **S/MIME (Secure/Multipurpose Internet Mail Extensions)**

### **1. Introduction (2 Marks)**

* **S/MIME** is an extension of **MIME** that provides **security for electronic mail**.
* It ensures **authentication, message integrity, non-repudiation, and confidentiality**.
* It allows users to **send digitally signed and/or encrypted emails** over the Internet.

---

### **2. Need for MIME (2 Marks)**

The **MIME** standard extends **RFC 822** to overcome SMTP limitations:

* SMTP cannot send **binary or executable data**.
* Cannot handle **national language (non-ASCII) characters**.
* SMTP servers may **reject large messages**.
* Translation problems occur between **ASCII and EBCDIC**.

---

### **3. MIME Features (2 Marks)**

MIME introduces:

1. **Five new message header fields:**

   * MIME-Version
   * Content-Type
   * Content-Transfer-Encoding
   * Content-ID
   * Content-Description
2. **Standard content formats** for multimedia emails.
3. **Transfer encodings** to ensure safe delivery of any data type.

---

### **4. MIME Content Types (1 Mark)**

| Type        | Subtype                  | Example                       |
| ----------- | ------------------------ | ----------------------------- |
| Text        | Plain, Enriched          | Unformatted or formatted text |
| Image       | JPEG, GIF                | Pictures                      |
| Audio       | Basic                    | Voice                         |
| Video       | MPEG                     | Video content                 |
| Application | PostScript, octet-stream | Program/binary data           |
| Multipart   | Mixed, Alternative       | Multiple message parts        |

---

### **5. MIME Transfer Encodings (1 Mark)**

| Encoding         | Description              |
| ---------------- | ------------------------ |
| 7bit             | ASCII text               |
| 8bit             | Extended ASCII           |
| Base64           | Converts binary to ASCII |
| Quoted-printable | Encodes text safely      |
| Binary           | Raw data format          |

---

### **6. S/MIME Functions (2 Marks)**

S/MIME extends MIME by adding **security features**:

* **Enveloped Data:** Encrypts content and keys for recipients.
* **Signed Data:** Digitally signs a message using sender’s private key.
* **Clear-signed Data:** Message readable without decryption, signature visible.
* **Signed & Enveloped Data:** Combines signing and encryption.

---

### **7. Working of S/MIME (2 Marks)**

**(a) Enveloped Data:**

1. Generate a random **session key**.
2. Encrypt session key using recipient’s **public key**.
3. Encrypt message using session key.
4. Send encrypted message + key info to recipient.

**(b) Signed Data:**

1. Create a **message digest (hash)** of the content.
2. Encrypt the digest with sender’s **private key**.
3. Attach signature and public key certificate.

---

### **8. Certificate Processing (1 Mark)**

Each S/MIME user must:

* Generate secure **key pairs (RSA, DSS, or DH)**.
* Register public key with **Certification Authority (CA)**.
* Store and retrieve **X.509 digital certificates**.

---

### **9. VeriSign Certificates (1 Mark)**

**VeriSign** issues **Digital IDs** that include:

* User’s public key and name
* Expiry date and serial number
* Issuing CA’s name

---

### **10. Conclusion (1 Mark)**

S/MIME provides a reliable way to ensure **secure and authenticated email communication** using **encryption and digital signatures**.
It overcomes the limitations of SMTP and MIME to support **confidential, verified, and tamper-proof messaging**.

---

✅ **Total: 13 Marks Breakdown**

| Section                    | Marks |
| -------------------------- | ----- |
| Introduction & Need        | 4     |
| MIME Features & Content    | 3     |
| S/MIME Functions & Working | 4     |
| Certificates & Conclusion  | 2     |

