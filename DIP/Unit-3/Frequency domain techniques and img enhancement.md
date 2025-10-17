## **Frequency Domain Techniques and Image Enhancement (15 Marks)**

### **1. Introduction**

Image enhancement aims to improve image quality for visual interpretation or further analysis. Enhancement techniques are broadly classified into:

* **Spatial Domain Techniques** – direct manipulation of pixel values.
* **Frequency Domain Techniques** – manipulation of the image’s frequency components using the **Fourier Transform**.

---

### **2. Frequency Domain Basics**

In frequency domain processing, the image is first transformed from the spatial domain into the frequency domain using the **Discrete Fourier Transform (DFT)**.
The main steps are:

1. **Compute the Fourier Transform** of the image ( f(x, y) ).
2. **Multiply** the transform by a filter function ( H(u, v) ).
3. **Take the Inverse DFT** to obtain the enhanced image.

[
G(u,v) = H(u,v) \times F(u,v)
]
[
g(x,y) = \text{IDFT}[G(u,v)]
]

---

### **3. Comparison: Spatial vs. Frequency Domain**

| **Aspect**   | **Spatial Domain**                     | **Frequency Domain**                            |
| ------------ | -------------------------------------- | ----------------------------------------------- |
| Operation    | Directly modifies pixel values         | Modifies frequency components                   |
| Tools        | Masks or convolution filters           | Fourier Transform and filter transfer functions |
| Applications | Smoothing, sharpening, noise reduction | Periodic noise removal, edge enhancement        |
| Example      | Averaging filter                       | Low-pass or High-pass filters                   |

---

### **4. Steps for Frequency Domain Filtering**

1. Obtain image ( f(x,y) ) of size ( M \times N ).
2. Pad the image to size ( P = 2M ), ( Q = 2N ).
3. Multiply by ( (-1)^{x+y} ) to center the transform.
4. Compute DFT → ( F(u,v) ).
5. Design a real, symmetric filter ( H(u,v) ).
6. Multiply: ( G(u,v) = H(u,v) \cdot F(u,v) ).
7. Compute inverse DFT → ( g_p(x,y) ).
8. Extract the original ( M \times N ) region to obtain the final image.

---

### **5. Image Enhancement in Frequency Domain**

#### **(a) Image Smoothing (Low-Pass Filters)**

Used to remove high-frequency components such as noise or fine details.

**Types:**

1. **Ideal Low Pass Filter (ILPF):**
   [
   H(u,v) =
   \begin{cases}
   1, & D(u,v) \le D_0 \
   0, & D(u,v) > D_0
   \end{cases}
   ]

   * Sharp cutoff, causes ringing effects.

2. **Butterworth Low Pass Filter (BLPF):**
   [
   H(u,v) = \frac{1}{1 + [\frac{D(u,v)}{D_0}]^{2n}}
   ]

   * Smooth transition; order ( n ) controls sharpness.

3. **Gaussian Low Pass Filter (GLPF):**
   [
   H(u,v) = e^{-\frac{D^2(u,v)}{2D_0^2}}
   ]

   * Smooth and natural attenuation, no ringing.

---

#### **(b) Image Sharpening (High-Pass Filters)**

Used to enhance edges and fine details by removing low frequencies.

**Types:**

1. **Ideal High Pass Filter (IHPF):**
   [
   H(u,v) =
   \begin{cases}
   0, & D(u,v) \le D_0 \
   1, & D(u,v) > D_0
   \end{cases}
   ]

2. **Butterworth High Pass Filter (BHPF):**
   [
   H(u,v) = \frac{1}{1 + [\frac{D_0}{D(u,v)}]^{2n}}
   ]

3. **Gaussian High Pass Filter (GHPF):**
   [
   H(u,v) = 1 - e^{-\frac{D^2(u,v)}{2D_0^2}}
   ]

---

### **6. Selective Filtering**

Selective filters act on specific parts of the frequency domain rather than the entire range.

* **Band Reject Filter (BRF):** Removes a specific range of frequencies.
* **Band Pass Filter (BPF):** Allows only a specific range of frequencies.
* **Notch Filters:** Remove narrow bands (useful for removing periodic noise).

**Example (Ideal BRF):**
[
H(u,v) =
\begin{cases}
0, & D_1 < D(u,v) < D_2 \
1, & \text{otherwise}
\end{cases}
]

---

### **7. Advantages of Frequency Domain Techniques**

* Easier to design filters mathematically.
* Useful for periodic noise removal.
* Allows selective manipulation of frequency components.
* Efficient for large images using Fast Fourier Transform (FFT).

---

### **8. Applications**

* Noise reduction in medical or satellite images.
* Edge enhancement and restoration.
* Removing periodic patterns (e.g., scan lines).
* Contrast enhancement in low-quality images.

---

✅ **In summary**,
Frequency domain techniques enhance images by transforming them into frequency components, modifying these using **filters (low-pass, high-pass, or selective)**, and then reconstructing the image via inverse transformation. They are powerful tools for noise reduction, sharpening, and selective enhancement.

