# ⭐ **Color Models – Explanation with Diagrams (13-Mark Answer)**

*(Based entirely on the PDF Section 1.10: Color Models)*

A **color model** is a mathematical system for representing colors in a standardized way so that computers, cameras, printers, and display devices can process color information.
Your PDF discusses the following three major models:

### **1. RGB Color Model**

### **2. CMY / CMYK Color Model**

### **3. HSI Color Model**

Below is the full explanation with diagrams as given in the PDF.

---

# ⭐ **1. RGB Color Model (Red–Green–Blue)**



### **Definition**

RGB is an **additive color model** in which colors are produced by adding varying intensities of **red, green, and blue** light.

### **Additive Mixing Principle (PDF content)**

* Red + Green = Yellow
* Red + Blue = Magenta
* Green + Blue = Cyan
* Red + Green + Blue = **White**

### **Diagram of RGB Color Cube**

*(Described from PDF)*
The RGB model is represented as a **3D cube**:

* Origin (0,0,0) = Black
* Opposite corner (255,255,255) = White
* Other corners = Primary & Secondary colors

```
         White (1,1,1)
          /---------/
         /         /
        /         /
Red----/-------- Yellow
 |    /         | 
 |   /          |
 |  /           |
Black --------- Green
```

### **Properties**

* Used for: **TV screens, computer monitors, digital cameras**
* Pixel value stored as:

  * R (8 bits)
  * G (8 bits)
  * B (8 bits)
    → Total = **24-bit color (16.7 million colors)**

---

# ⭐ **2. CMY and CMYK Color Model**



The PDF explains CMY/CMYK as **subtractive color models** used in printing devices.

## **A) CMY (Cyan–Magenta–Yellow)**

### **Definition**

CMY is a **subtractive color model**, meaning colors are obtained by **subtracting** (absorbing) light using pigments.

### **Subtraction Principle (PDF Examples)**

* Cyan absorbs Red
* Magenta absorbs Green
* Yellow absorbs Blue

**White light** = R + G + B
When white light strikes a colored pigment:

* Yellow pigment absorbs Blue → reflects Red + Green
* Cyan pigment absorbs Red → reflects Green + Blue
* Magenta pigment absorbs Green → reflects Red + Blue

Thus, CMY is the **inverse of RGB**:

[
CMY = 1 - RGB
]

### **CMY Diagram (PDF based)**

Three colored regions overlapping:

```
      Cyan
     /    \
    /      \
Green------Blue
   \       /
    \     /
    Yellow
```

---

## **B) CMYK (Cyan–Magenta–Yellow–Black)**

### **Why K (Black) is Added**

According to the PDF:
Mixing 100% cyan + 100% magenta + 100% yellow *should* produce black, but in practice produces a “muddy” dark brown.

Hence, printers add **K = Black**.

### **Applications**

* Used in **printing**, **newspapers**, **hard copies**, etc.

---

# ⭐ **3. HSI Color Model (Hue–Saturation–Intensity)**



The PDF explains that RGB is excellent for machines but not intuitive for humans.
HSI is **best for human interpretation**, because humans describe colors using:

* **Hue** → type of color
* **Saturation** → purity or whiteness in color
* **Intensity** → brightness level

---

## **A) Hue (H)**

* Represents **actual color** (Red, Blue, Yellow, etc.)
* Measured as an **angle (0°–360°)** on the color wheel.

## **B) Saturation (S)**

* Degree to which a color is diluted by white light.
* 0 = gray (no color)
* 1 = fully saturated (pure color)

## **C) Intensity (I)**

* Measure of **brightness**, ranging from black → white.
* Computed as average of RGB values.

---

## ⭐ HSI Diagram (from the PDF)

### **Top View: Hexagon Representation**

```
       Red (0°)
        *
    *       *
Magenta     Yellow
    *       *
        *
      Cyan
```

### **3D Double-Cone or Triangle Model**

Shown in the PDF: Intensity on vertical axis, hue around the circle, saturation as distance from center.

---

# ⭐ **Conversion Formulas (from PDF Figure 7)**



HSI is computed from RGB using:

### **Intensity**

[
I = \frac{R + G + B}{3}
]

### **Saturation**

[
S = 1 - \frac{3}{R + G + B} \min(R,G,B)
]

### **Hue**

[
H = \cos^{-1} \left( \frac{1}{2 [(R-G)^2 + (R-B)(G-B)]^{1/2}} \right)
]

---

# ⭐ 13-Mark Ready Comparison Table

*(Helpful for scoring full marks)*

| Feature       | RGB               | CMY/CMYK                | HSI                            |
| ------------- | ----------------- | ----------------------- | ------------------------------ |
| Type          | Additive          | Subtractive             | Perceptual                     |
| Based on      | Light emission    | Pigments/ink absorption | Human vision                   |
| Used in       | Displays, cameras | Printing                | Image processing, segmentation |
| Diagram       | Cube              | Overlapping circles     | Hexagon/cone                   |
| Colors formed | Combine R, G, B   | Subtract R, G, B        | Hue, saturation, brightness    |

