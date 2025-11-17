---

# **Image Compression and Variable Length Coding Schemes (13 Marks)**

---

## **1. Introduction to Image Compression (3 Marks)**

### **Definition:**

Image compression is the process of reducing the number of bits required to represent an image, without significant loss in visual quality.
It removes redundant or irrelevant data to make image storage and transmission more efficient.

### **Need for Compression:**

* Reduces file size for storage.
* Speeds up transmission of images.
* Saves bandwidth and memory space.
* Used in multimedia systems, internet, video conferencing, etc.

---

## **Types of Compression**

### **1. Lossless Compression**

* No data loss.
* Exact reconstruction of original image.
* Examples: Huffman Coding, Run-Length Coding (RLC), Arithmetic Coding, LZW.

### **2. Lossy Compression**

* Some data is lost.
* Achieves high compression ratio with good visual quality.
* Examples: JPEG, MPEG.

---

# **2. Variable Length Coding (VLC) (10 Marks)**

### **Definition:**

Variable Length Coding assigns **shorter binary codes** to frequently occurring symbols and **longer codes** to rare symbols.
This reduces the **average code length** and improves **compression efficiency**.

---

## **(i) Huffman Coding (2.5 Marks)**

* Developed by D. A. Huffman (1952).
* Based on symbol probabilities.
* Creates a binary tree: shorter codes → frequent symbols.

### **Steps:**

a. Find frequencies/probabilities of each symbol.
b. Combine the two least frequent symbols into a new node.
c. Repeat until only one node remains (root).
d. Assign binary codes along tree branches.

### **Example:**

Symbol: A B C D
Prob: 0.4, 0.3, 0.2, 0.1
Codes: 0, 10, 110, 111

### **Type:** Lossless

### **Used in:** JPEG, MPEG

---

## **(ii) Run-Length Coding (RLC) (2.5 Marks)**

* Simplest lossless method.
* Replaces repeated pixel values (runs) with a single value and count.

### **Example:**

AAAA BBB → (4A)(3B)
000001111 → (5,0)(5,1)

### **Works well for:**

Binary or simple images with large uniform areas.

### **Type:** Lossless

### **Used in:** Fax, BMP, TIFF

---

## **(iii) Arithmetic Coding (2.5 Marks)**

* Encodes the entire message as a single fraction between 0 and 1.
* Works by dividing intervals based on symbol probabilities.
* More efficient than Huffman when probabilities are uneven.

### **Example:**

Symbols: A(0.6), B(0.3), C(0.1)
Message “AB” encoded as a number in interval [0.0, 0.18].

### **Type:** Lossless

### **Used in:** JPEG2000, MPEG-2, H.264

---

## **(iv) Lempel-Ziv-Welch (LZW) Coding (2.5 Marks)**

* Builds dictionary of symbol sequences dynamically.
* Replaces repeated patterns with shorter dictionary codes.
* The dictionary does not need to be sent (generated automatically).

### **Example:**

Input: ABAABABAAB
Codes: [A, B, AB, AAB, …]

### **Type:** Lossless

### **Used in:** GIF, TIFF, PDF, Unix compress utility

---

# **3. Diagram (Optional for Extra Marks)**

```
[Input Image]
       ↓
[Encoder: Huffman / RLC / Arithmetic / LZW]
       ↓
[Compressed Data]
       ↓
[Decoder]
       ↓
[Reconstructed Image]
```

---

If you want, I can also format this into **PDF**, **Word**, or **exam-ready notes**.
