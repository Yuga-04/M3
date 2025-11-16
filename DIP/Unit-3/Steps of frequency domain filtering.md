Here’s a **13-mark concise and clear answer** on
🎯 **Steps for Filtering in the Frequency Domain**
from your *UNIT III notes* — perfectly written for **13 marks** in university exams 👇

---

## **Steps for Filtering in the Frequency Domain**

---

### **1. Introduction**

Filtering in the **frequency domain** is an important image enhancement technique in **Digital Image Processing**.
It is based on modifying the **Fourier Transform** of an image to achieve a specific enhancement objective — such as **smoothing**, **sharpening**, or **noise removal**.

Instead of directly changing pixel values, the image is transformed to the **frequency domain**, processed using a **filter function**, and then converted back to the **spatial domain**.

---

### **2. Basic Model**

The basic formula for frequency domain filtering is:

[
G(u, v) = H(u, v) \cdot F(u, v)
]

where:

* ( F(u, v) ) → Fourier Transform of input image ( f(x, y) )
* ( H(u, v) ) → Filter transfer function
* ( G(u, v) ) → Filtered image in frequency domain
* ( g(x, y) ) → Final enhanced image after applying inverse Fourier Transform

---

### **3. Basic Steps Involved in Frequency Domain Filtering**

#### **Step 1 – Compute the Fourier Transform**

Convert the input image ( f(x, y) ) from the spatial domain to the frequency domain using the **2D Fourier Transform**.

[
F(u, v) = \sum_x \sum_y f(x, y)e^{-j2\pi(ux/M + vy/N)}
]

---

#### **Step 2 – Multiply by Filter Transfer Function**

Multiply the transformed image ( F(u, v) ) by a **filter function** ( H(u, v) ) that represents the required enhancement.

[
G(u, v) = H(u, v) \times F(u, v)
]

Types of filters used:

* **Low-Pass Filter (LPF):** For image smoothing or noise reduction
* **High-Pass Filter (HPF):** For sharpening and edge enhancement
* **Band-Pass / Band-Reject Filters:** For selective filtering

---

#### **Step 3 – Compute the Inverse Fourier Transform**

Apply **Inverse Fourier Transform** to the filtered image to get the final enhanced image in the spatial domain:

[
g(x, y) = \text{IDFT}[G(u, v)]
]

This step converts the image back into a viewable form.

---

### **4. Detailed Procedure (Expanded Steps from Notes)**

To perform accurate frequency domain filtering, the following **detailed 8 steps** are generally followed:

1. **Input the image** ( f(x, y) ) of size ( M \times N ).
2. **Pad** the image to size ( P = 2M, Q = 2N ) to avoid wraparound effects.
3. **Multiply by** ( (-1)^{x+y} ) to center the transform.
4. **Compute the DFT** of the centered image.
5. **Design the filter** ( H(u, v) ) (e.g., LPF, HPF, etc.).
6. **Multiply** ( H(u, v) ) with ( F(u, v) ) → ( G(u, v) = H(u, v)F(u, v) ).
7. **Apply Inverse DFT** to get ( g_p(x, y) ).
8. **Extract** the top-left ( M \times N ) region to get the final result ( g(x, y) ).

---

### **5. Flow Diagram**

```
Input Image f(x,y)
        ↓
Zero Padding → Centering (-1)^(x+y)
        ↓
Fourier Transform → F(u,v)
        ↓
Apply Filter H(u,v)
        ↓
G(u,v) = H(u,v) × F(u,v)
        ↓
Inverse Fourier Transform
        ↓
Final Enhanced Image g(x,y)
```

---

### **6. Applications**

* Image smoothing and denoising
* Edge and detail enhancement
* Periodic noise removal
* Illumination correction

---

### **7. Advantages**

* Accurate control of frequency components
* Effective for global image enhancement
* Efficient for removing periodic noise

---

### **8. Disadvantages**

* Computationally complex
* Loss of spatial localization
* Requires proper filter design

---

### **9. Conclusion**

Filtering in the frequency domain enhances images by modifying their frequency components using Fourier transform techniques.
It allows powerful operations like **smoothing**, **sharpening**, and **noise reduction**, making it an essential technique in **Digital Image Processing**.

---

✅ **13-Mark Structure Summary:**

1. Introduction – 2 marks
2. Basic Model – 1 mark
3. 3 Main Steps – 3 marks
4. Detailed 8 Steps – 3 marks
5. Diagram – 2 marks
6. Applications, Advantages, and Conclusion – 2 marks

---

Would you like me to include a **neat labeled image (flow + frequency domain filtering steps)** for your answer sheet? It’ll visually strengthen your 13-mark answer.
