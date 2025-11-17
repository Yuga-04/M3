# **IMAGE SAMPLING AND IMAGE QUANTIZATION (13-MARK ANSWER)**



In Digital Image Processing, converting an analog image into a digital image requires **digitization**. Digitization consists of two major steps:

1. **Image Sampling** – digitizing the spatial coordinates (x, y)
2. **Image Quantization** – digitizing the amplitude (gray level) values

Together, these processes convert a continuous image into a matrix of discrete pixels suitable for digital storage and processing.

---

# **1. IMAGE SAMPLING**


<img width="389" height="178" alt="image" src="https://github.com/user-attachments/assets/5194ebc3-486e-4b7e-9445-3792cbd6b9f3" />


Sampling refers to **digitizing the spatial coordinates** of an image.
In an analog image, both the spatial domain (x and y) and amplitude are continuous. Sampling is performed on the **independent variables**, i.e., the spatial coordinates.

### **Definition:**

Sampling is the process of selecting a finite number of discrete points (pixels) from the continuous image.

### **Concept:**

* Each sample corresponds to one **pixel** in the digital image.
* More sampling → more pixels → higher resolution.
* Fewer sampling points → loss of detail and distortions.

### **Relation to Pixel Resolution:**

Number of pixels = (Number of sampled rows) × (Number of sampled columns)

Example:

* 36 samples → 6×6 pixel image
* Sampling density directly equals the number of sensors in the CCD array.

### **Effect of Sampling Density:**

* **High sampling rate:** Image looks smooth, clear, and close to original.
* **Low sampling rate:** Aliasing, distortion, and loss of details occur.

### **Diagram Explanation from PDF:**

The notes explain sampling using a signal curve. By taking samples along the x-axis, the continuous signal is represented by discrete sample points. However, these points still have continuous vertical (gray) values until quantization occurs.


<img width="893" height="480" alt="image" src="https://github.com/user-attachments/assets/9609402a-6d77-44ba-b42e-d2666f7a661f" />


---

# **2. IMAGE QUANTIZATION**

Quantization refers to **digitizing the amplitude values** of the sampled image.

### **Definition:**

Quantization is the process of mapping continuous amplitude values into a finite number of discrete gray levels.


<img width="826" height="435" alt="image" src="https://github.com/user-attachments/assets/dfd753cd-7bb4-4114-a876-e442dcb3a8f2" />


### **Concept:**

After sampling, the selected points (pixels) still have real-valued continuous amplitudes. Quantization assigns each pixel to the nearest discrete level.

### **Example from the PDF:**


<img width="950" height="418" alt="image" src="https://github.com/user-attachments/assets/941e4435-5c9d-41b3-a24d-79c9e3c76664" />


In the figure, the vertically continuous values are quantized into 5 levels:

* Level 0 = black
* Level 4 = white
* Intermediate levels = gray shades

### **Relationship to Gray-Level Resolution:**

If the quantizer uses **b bits per pixel**, then the number of levels = 2^b.

Examples:

* b = 1 → 2 levels → Black and White image
* b = 8 → 256 levels → Standard grayscale image
* b = 24 → 16.7 million colors (in color images)

### **Effect of Quantization Levels:**

* **High quantization levels:** Smooth shading, no visible steps
* **Low quantization levels:** False contours appear (banding effect)

### **False Contours:**

When there are insufficient brightness levels, smooth gradient regions break into bands resembling contour lines. This is one of the main issues in poor quantization.

---

# **3. COMBINED PROCESS: DIGITIZATION**

The PDF explains that sampling alone cannot produce a digital image; quantization must follow.

* **Sampling:** Chooses spatial locations
* **Quantization:** Assigns discrete brightness values

The final output is a **2D matrix of integers**, representing the digital image.

Example:

```
128  30  123
232 123  321
123  77   89
```

Each number represents the quantized amplitude of a sampled point (pixel).

---

# **4. IMPORTANCE OF SAMPLING AND QUANTIZATION**

### **Sampling is important for:**

* Spatial resolution
* Capturing structural detail
* Avoiding aliasing

### **Quantization is important for:**

* Gray-level resolution
* Image appearance
* Avoiding false contours

Both processes determine:

* Image quality
* File size
* Processing complexity

---
