## **Properties of 2D Discrete Fourier Transform (DFT)**

*(15 Marks)*

---

### **1. Introduction**

The **2D Discrete Fourier Transform (DFT)** is a mathematical tool used to convert a digital image from the **spatial domain** into the **frequency domain**.
It is widely used in **image processing** for filtering, enhancement, and analysis.

For an image ( f(x, y) ) of size ( M \times N ), the 2D DFT is given by:

[
F(u, v) = \sum_{x=0}^{M-1}\sum_{y=0}^{N-1} f(x, y) e^{-j2\pi\left(\frac{ux}{M} + \frac{vy}{N}\right)}
]

and the **Inverse DFT** is:

[
f(x, y) = \frac{1}{MN}\sum_{u=0}^{M-1}\sum_{v=0}^{N-1} F(u, v) e^{j2\pi\left(\frac{ux}{M} + \frac{vy}{N}\right)}
]

These transforms allow images to be analyzed in terms of their **frequency components** —
low frequencies correspond to smooth areas, and high frequencies correspond to edges or details.

---

### **2. Need for Studying DFT Properties**

The properties of DFT make it easier to:

* Analyze frequency content of images,
* Simplify mathematical operations like filtering and correlation,
* Develop efficient image processing algorithms.

---

### **3. Important Properties of 2D DFT**

The major properties discussed in the document include:

---

#### **(i) Linearity Property**

**Statement:**
The DFT of a linear combination of two or more images is equal to the same linear combination of their individual DFTs.

If
[
DFT{f_1(x,y)} = F_1(u,v) \quad \text{and} \quad DFT{f_2(x,y)} = F_2(u,v)
]
then,
[
DFT{a_1 f_1(x,y) + a_2 f_2(x,y)} = a_1 F_1(u,v) + a_2 F_2(u,v)
]
where ( a_1, a_2 ) are constants.

**Proof:**
[
F(u,v) = \sum_x \sum_y [a_1 f_1(x,y) + a_2 f_2(x,y)] e^{-j2\pi(ux/M + vy/N)}
]
[
= a_1 \sum_x \sum_y f_1(x,y) e^{-j2\pi(ux/M + vy/N)} + a_2 \sum_x \sum_y f_2(x,y) e^{-j2\pi(ux/M + vy/N)}
]
[
= a_1 F_1(u,v) + a_2 F_2(u,v)
]
Hence, **proved**.

**Significance:**
This property allows multiple signals or images to be combined and transformed linearly — helpful in composite filtering or image blending operations.

---

#### **(ii) Parseval’s Relation (Energy Conservation Property)**

**Statement:**
The total energy (sum of squared magnitudes) of a signal in the spatial domain is equal to the total energy in the frequency domain.

If ( f(x,y) ) ↔ ( F(u,v) ), then:
[
\sum_{x=0}^{M-1}\sum_{y=0}^{N-1} |f(x,y)|^2 = \frac{1}{MN} \sum_{u=0}^{M-1}\sum_{v=0}^{N-1} |F(u,v)|^2
]

**Proof (from document):**

Let DFT({x_1(n)} = X_1(k)) and DFT({x_2(n)} = X_2(k)).

Then Parseval’s relation is:
[
\sum_{n=0}^{N-1} x_1(n)x_2^*(n) = \frac{1}{N} \sum_{k=0}^{N-1} X_1(k)X_2^*(k)
]

For 2D images, this becomes:
[
\sum_{x}\sum_{y} f(x,y)g^*(x,y) = \frac{1}{MN} \sum_{u}\sum_{v} F(u,v)G^*(u,v)
]

If ( f = g ), then:
[
\sum_{x,y} |f(x,y)|^2 = \frac{1}{MN} \sum_{u,v} |F(u,v)|^2
]

Thus, energy in both domains remains the same.
**Hence proved.**

**Significance:**

* Ensures no loss of information in frequency transformation.
* Used to verify correctness of image transforms and filters.

---

#### **(iii) Translation (Shifting) Property**

If an image is shifted in the spatial domain, the corresponding frequency domain representation is multiplied by a **complex exponential**.

[
f(x - x_0, y - y_0) \leftrightarrow F(u,v)e^{-j2\pi(ux_0/M + vy_0/N)}
]

**Significance:**
Used in motion detection, phase correlation, and image registration.

---

#### **(iv) Convolution Property**

Convolution in the **spatial domain** is equivalent to **multiplication** in the **frequency domain**.

[
f(x,y) * h(x,y) \leftrightarrow F(u,v) \cdot H(u,v)
]

and conversely,

[
f(x,y) \cdot h(x,y) \leftrightarrow F(u,v) * H(u,v)
]

**Significance:**
This property simplifies image filtering operations (smoothing, sharpening) since convolution in spatial domain is computationally expensive.

---

#### **(v) Periodicity Property**

Both ( f(x,y) ) and its transform ( F(u,v) ) are **periodic** with periods ( M ) and ( N ) respectively:
[
F(u + M, v) = F(u,v)
]
[
F(u, v + N) = F(u,v)
]

**Significance:**
Important for understanding aliasing and frequency wrapping during digital image processing.

---

#### **(vi) Symmetry Property**

For **real-valued images**, the DFT exhibits **complex conjugate symmetry**:
[
F(u,v) = F^*(-u, -v)
]

**Significance:**
This allows only half of the spectrum to be stored or processed, saving memory and computation.

---

#### **(vii) Scaling Property**

A scaling in the spatial domain leads to an inverse scaling in the frequency domain:
[
f(ax, by) \leftrightarrow \frac{1}{|ab|}F\left(\frac{u}{a}, \frac{v}{b}\right)
]

**Significance:**
Helps analyze image resolution and frequency scaling effects.

---

### **4. Summary Table of Properties**

| **Property**        | **Mathematical Expression**                                        | **Remarks / Use**     |                       |   |      |                     |
| ------------------- | ------------------------------------------------------------------ | --------------------- | --------------------- | - | ---- | ------------------- |
| Linearity           | ( a_1f_1 + a_2f_2 \leftrightarrow a_1F_1 + a_2F_2 )                | Superposition holds   |                       |   |      |                     |
| Translation         | ( f(x-x_0,y-y_0) \leftrightarrow F(u,v)e^{-j2\pi(ux_0/M+vy_0/N)} ) | Shifting in image     |                       |   |      |                     |
| Convolution         | ( f*h \leftrightarrow FH )                                         | Simplifies filtering  |                       |   |      |                     |
| Multiplication      | ( f\cdot h \leftrightarrow F*H )                                   | Correlation analysis  |                       |   |      |                     |
| Parseval’s Relation | ( \sum                                                             | f                     | ^2 = \frac{1}{MN}\sum | F | ^2 ) | Energy conservation |
| Symmetry            | ( F(u,v)=F^*(-u,-v) )                                              | Real image property   |                       |   |      |                     |
| Periodicity         | ( F(u+M,v)=F(u,v) )                                                | Periodic in both axes |                       |   |      |                     |

---

### **5. Applications of DFT Properties**

* **Efficient Image Filtering** using convolution property
* **Edge Detection and Enhancement**
* **Noise Removal** (frequency domain operations)
* **Pattern Recognition and Image Correlation**
* **Motion Estimation and Registration** using translation property

---

### **6. Conclusion**

The **properties of the 2D DFT** provide a mathematical foundation for understanding and applying frequency domain techniques in image processing.
They simplify complex spatial operations, preserve image energy, and enable efficient filtering, transformation, and enhancement of digital images.

---

✅ **In summary:**

[
\boxed{
\text{Key Properties: Linearity, Translation, Convolution, Symmetry, Periodicity, Parseval’s Relation.}
}
]
