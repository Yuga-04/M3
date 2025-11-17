Below is a **13-mark answer** fully based on the contents of the uploaded PDF, with clear explanations and an example, along with proper citations.

---

# **Butterworth Low-Pass Filter (BLPF) and Ideal Low-Pass Filter (ILPF)**

(13-Marks Answer)

Low-pass filters are used in **image smoothing**, where we suppress high-frequency components (edges, noise) and preserve low-frequency components (slow intensity variations). The PDF clearly lists **Ideal LPF and Butterworth LPF** as two of the main smoothing filters in the frequency domain .

---

# **1. Ideal Low-Pass Filter (ILPF)**

An **Ideal Low-Pass Filter** allows all frequency components within a cutoff radius ( D_0 ) to pass *unchanged*, while **completely eliminating** all frequencies outside this radius.
It is defined as:<br><br>
&nbsp;&nbsp;&nbsp;&nbsp;
<img width="415" height="107" alt="image" src="https://github.com/user-attachments/assets/854e3c75-7fb6-437c-a00c-585772a06428" />
<br>
Where
<br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="497" height="55" alt="image" src="https://github.com/user-attachments/assets/d50722b1-27ae-4af8-a024-d68e651c1b81" />

### **Characteristics**

* Perfectly sharp cutoff at (D_0).
* Produces strong ringing artifacts (Gibbs phenomenon).
* Removes high-frequency noise effectively but may distort edges.

---

### **Example (from PDF context)**

The PDF states that **Image smoothing in frequency domain uses Ideal LPF** .
For example:

* Suppose we apply an **ILPF with cutoff (D_0 = 40)** to an image with periodic noise.
* In the frequency spectrum, components beyond radius 40 are removed.
* The output becomes highly smoothed but suffers from ringing near edges due to the abrupt transition of the ILPF.

---

# **2. Butterworth Low-Pass Filter (BLPF)**

A **Butterworth LPF** provides a **smooth transition** between passed and blocked frequencies, avoiding the sharp cutoff of ILPF.

Its transfer function is:
<br><br>
<img width="350" height="148" alt="image" src="https://github.com/user-attachments/assets/032879d2-5c45-4fb2-b21e-554ef66c24cd" />
<br>

where

* (D_0) = cutoff frequency
* (n) = filter order (controls sharpness)

### **Characteristics**

* No abrupt cutoff; transition is gradual.
* Reduces ringing significantly.
* Higher order (n) makes the filter behave more like an ideal filter.
* Better balance between smoothing and edge preservation.

The PDF lists **Butterworth LPF** as one of the major smoothing filters in frequency domain image processing .

---

### **Example (based on PDF’s problem requirement)**

The PDF asks to *“Discuss Butterworth lowpass filter with a suitable example”* .

Example explanation:

* A noisy image is transformed into the frequency domain using DFT.
* A **Butterworth LPF with order (n=2)** and cutoff **(D_0 = 50)** is applied.
* Frequencies close to the origin are preserved with values close to 1.
* Frequencies gradually decrease as they move away from the center.
* The output image becomes smooth with **less ringing** compared to ILPF.

Thus, the Butterworth filter provides **better visual results** because of its smooth roll-off instead of an abrupt cutoff.

---

# **Comparison: ILPF vs BLPF**

| Feature           | ILPF                      | BLPF                                    |
| ----------------- | ------------------------- | --------------------------------------- |
| Cutoff nature     | Abrupt (ideal)            | Smooth transition                       |
| Ringing           | High (Gibbs effect)       | Very low                                |
| Computation       | Simple                    | Slightly more complex                   |
| Edge preservation | Poor                      | Better                                  |
| Used when         | Strong smoothing required | Balanced smoothing with fewer artifacts |

---

# **3. Example Illustration (Suitable for 13-mark answer)**

**Consider a grayscale image with periodic high-frequency noise:**

* Applying **ILPF with ( D_0 = 30 )** →

  * All frequencies beyond 30 removed
  * Output: Strongly smoothed but has visible ringing near edges
* Applying **BLPF with ( D_0 = 30, n = 3 )** →

  * Frequencies smoothly attenuated
  * Output: Smooth image with minimal ringing and better natural appearance

Thus **Butterworth LPF** is preferred for practical applications, such as medical image smoothing or removing sinusoidal noise, due to its more realistic behavior.

---

# **Conclusion**

* ILPF has a **perfect cutoff** but produces significant ringing artifacts.
* BLPF offers a **smooth roll-off**, producing better visual quality.
* The PDF clearly lists these filters under *frequency domain image smoothing* and also asks for detailed discussion, which is covered here thoroughly ✔️ .

---

If you want, I can also prepare **diagrams**, a **13-mark formatted answer PDF**, or **numerical examples**.
