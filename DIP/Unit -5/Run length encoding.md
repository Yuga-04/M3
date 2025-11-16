Below is the **complete, clean, properly arranged, exam-ready “Run-Length Encoding (RLE) Approach”** in correct order (full 13-mark answer).

---

# **Image Compression – Run Length Encoding (RLE) Approach (13 Marks)**

---

## **1. Introduction to Image Compression (3 Marks)**

### **Definition:**

Image compression is the process of reducing the amount of data required to represent an image by removing redundant information.

### **Purpose:**

* To reduce file size for storage and transmission.
* To save bandwidth in communication systems.
* To make faster transfer and processing of images possible.

### **Types of Compression:**

1. **Lossless Compression** – No data or quality is lost (e.g., Huffman, RLE).
2. **Lossy Compression** – Some data is lost but visual quality remains acceptable (e.g., JPEG, MPEG).

---

# **2. Run-Length Encoding (RLE) Approach (8 Marks)**

## **Definition:**

Run-Length Encoding is a **lossless image compression method** that reduces the size of data by replacing **repeated pixel values (runs)** with a single value and a count.

Works best for **binary or simple images** with long runs of identical pixels (e.g., black-and-white icons, scanned documents).

---

## **3. Working Principle:**

RLE replaces consecutive repeating symbols (pixels) with:

```
<Pixel Value, Run Length>
```

### **Example 1 (Characters):**

Original sequence:

```
AAA ABBB CC AA
```

Encoded as:

```
(4A)(3B)(2C)(2A)
```

---

### **Example 2 (Binary Pixels):**

Original:

```
00000111110000
```

Encoded as:

```
(5,0)(5,1)(4,0)
```

So instead of storing 14 bits, we store only 6 numbers → **compression**.

---

## **4. Steps in RLE:**

1. Scan the image row by row (or column by column).
2. Count consecutive pixels with same value.
3. Store the pair: **(count, pixel value)**.
4. Repeat for whole image.
5. Decode by expanding runs back into original pixels.

---

## **5. Advantages:**

* Very simple and fast to implement.
* Lossless compression (no data lost).
* Best for simple, repetitive images like text, icons, line drawings.
* Used in fax machines, BMP, TIFF formats.

---

## **6. Disadvantages:**

* Not efficient for complex images (e.g., photographs).
* Compression ratio decreases when few pixels repeat.

---

## **7. Is RLE Lossy or Lossless?**

* **RLE is a Lossless Compression Method.**
* The original image can be exactly reconstructed from compressed data.

---

## **8. Example Calculation:**

### **Original 8×8 binary image:**

Size = **64 bits**

### **After RLE compression:**

29 runs × 6 bits/run = **174 bits total**
= **2.72 bits/pixel**

### **Compression ratio:**

```
192 / 174 = 1.10 : 1
```

A small reduction, but **no quality loss**.

---

# **9. Diagram (optional for extra marks):**

```
[Input Image]
      ↓
[Run-Length Encoder]
      ↓
[Compressed Data]
      ↓
[Run-Length Decoder]
      ↓
[Reconstructed Image]
```

---

If you want, I can combine **both topics (VLC + RLE)** into one full 25-mark answer in perfect order.
