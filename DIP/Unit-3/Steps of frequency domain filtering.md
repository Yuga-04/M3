

## **Steps of Frequency Domain Filtering**

*(15 Marks)*

---

### **1. Introduction**

Frequency domain filtering is a powerful image enhancement technique where an image is transformed from the **spatial domain** into the **frequency domain** using the **Fourier Transform**.
Filtering is performed by modifying the **Fourier coefficients** of the image, and then transforming the result back to the spatial domain using the **Inverse Fourier Transform**.

The main idea is:
[
G(u,v) = H(u,v) \cdot F(u,v)
]
[
g(x,y) = \text{IDFT}[G(u,v)]
]

where:

* ( f(x,y) ): Input image
* ( F(u,v) ): Fourier transform of input image
* ( H(u,v) ): Filter transfer function
* ( G(u,v) ): Filtered image in frequency domain
* ( g(x,y) ): Enhanced output image

---

### **2. Basic Steps Involved in Frequency Domain Filtering**

According to the document, the **steps involved in the process of filtering in the frequency domain** are as follows:

---

#### **Step 1: Compute the Fourier Transform of the Image**

The input image ( f(x, y) ) is converted from the spatial domain to the frequency domain using the **Discrete Fourier Transform (DFT)**:
[
F(u,v) = \sum_x \sum_y f(x,y) e^{-j2\pi(ux/M + vy/N)}
]
This step separates the image into its **frequency components**, where:

* Low frequencies represent **smooth regions**, and
* High frequencies represent **edges and fine details**.

---

#### **Step 2: Multiply the Result by a Filter Transfer Function**

A **filter function** ( H(u,v) ) is designed to achieve a specific enhancement objective (for example, smoothing, sharpening, or noise removal).
The image spectrum is modified by:
[
G(u,v) = H(u,v) \times F(u,v)
]
Here, multiplication in the frequency domain corresponds to **convolution in the spatial domain**.

---

#### **Step 3: Compute the Inverse Fourier Transform**

After applying the desired filtering, the result is converted back to the spatial domain by computing the **Inverse DFT**:
[
g(x,y) = \text{IDFT}[G(u,v)]
]
This step yields the **processed (enhanced) image**.

---

### **3. Detailed Procedure (with Preprocessing Steps)**

In practical implementation, the following detailed steps are used:

1. **Obtain an input image** ( f(x,y) ) of size ( M \times N ).
2. **Pad the image** to size ( P = 2M ), ( Q = 2N ) to reduce edge effects in the transform.
3. **Multiply by** ( (-1)^{x+y} ) to center the Fourier transform.
4. **Compute the DFT**, obtaining ( F(u,v) ).
5. **Generate a filter function** ( H(u,v) ) of size ( P \times Q ) (centered at ( P/2, Q/2 )).
6. **Multiply the spectra:** ( G(u,v) = H(u,v) \cdot F(u,v) ).
7. **Compute the inverse DFT** to get the filtered image ( g_p(x,y) ).
8. **Extract the top-left ( M \times N )** portion of ( g_p(x,y) ) as the **final processed image**.

---

### **4. Flow Diagram of Frequency Domain Filtering**

```
Input Image f(x, y)
        │
        ▼
  Preprocessing (Padding + Centering)
        │
        ▼
Fourier Transform → F(u, v)
        │
        ▼
Multiply by Filter Function → H(u, v)
        │
        ▼
Product → G(u, v) = H(u, v)F(u, v)
        │
        ▼
Inverse Fourier Transform
        │
        ▼
Enhanced Image g(x, y)
```

---

### **5. Explanation of Each Component**

| **Term**   | **Meaning**                                             |
| ---------- | ------------------------------------------------------- |
| ( F(u,v) ) | Frequency representation of the image                   |
| ( H(u,v) ) | Filter transfer function (determines type of filtering) |
| ( G(u,v) ) | Filtered image in frequency domain                      |
| ( g(x,y) ) | Enhanced image after inverse transform                  |

---

### **6. Applications of Frequency Domain Filtering**

* **Image smoothing** (using low-pass filters)
* **Image sharpening** (using high-pass filters)
* **Noise removal** (removing specific frequency components)
* **Edge enhancement and restoration**

---

### **7. Advantages**

* Mathematical design of filters is simple and flexible.
* Efficient for large images (using FFT algorithms).
* Allows **selective enhancement** of certain frequency ranges.
* Useful for **periodic noise suppression**.

---

### **8. Conclusion**

Frequency domain filtering modifies the image’s frequency content to achieve enhancement goals such as smoothing or sharpening.
The process involves:

1. Transforming to the frequency domain,
2. Applying a suitable filter, and
3. Returning to the spatial domain.

This method provides a robust approach for manipulating the image’s frequency characteristics and is widely used in image processing applications like **noise reduction**, **edge detection**, and **image restoration**.

---

✅ **Summary (Key Formula):**
[
\boxed{
\begin{aligned}
F(u,v) &= \text{DFT}[f(x,y)] \
G(u,v) &= H(u,v) \cdot F(u,v) \
g(x,y) &= \text{IDFT}[G(u,v)]
\end{aligned}
}
]

