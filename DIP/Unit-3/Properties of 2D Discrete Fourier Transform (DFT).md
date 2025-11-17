Here is a **short, clean 13-mark answer** with **ONLY the main formulas + brief theory** for each property.
This is exactly the way you should write in an exam.

---


<img width="928" height="649" alt="image" src="https://github.com/user-attachments/assets/c9eb3ecd-d58c-49cb-8e53-ca91f82743eb" />



# ⭐ **Properties of 2D Discrete Fourier Transform (DFT)**

### *(Main Formulas + Short Theory – 13 Marks)*

---

## **1. Linearity Property**

**Formula:**


<img width="732" height="84" alt="image" src="https://github.com/user-attachments/assets/fa0974ad-1b28-4de8-8ea5-f6bf83a01611" />


**Theory:**
The DFT is linear. A linear combination of images in the spatial domain corresponds to the same linear combination in the frequency domain. This simplifies many image operations like blending and filtering.

---

## **2. Parseval’s Relation (Energy Conservation)**

**Formula:**


<img width="458" height="102" alt="image" src="https://github.com/user-attachments/assets/bbf5a06d-97c6-4202-bc7e-2425ff6ff85b" />


**Theory:**
The total energy of an image remains the same in spatial and frequency domains. No information is lost during the Fourier transform.

---

## **3. Translation (Shifting) Property**

**Formula:**


<img width="555" height="67" alt="image" src="https://github.com/user-attachments/assets/a4b1e4f0-ace2-4b89-99e0-edfb42afcd94" />


**Theory:**
Shifting an image results in a phase shift in the frequency domain but does not change the magnitude. Useful in motion detection and image alignment.

---

## **4. Convolution Property**

**Formula:**


<img width="463" height="59" alt="image" src="https://github.com/user-attachments/assets/c7b2fdca-7987-4b4f-8bc2-74f7bcc44307" />


**Theory:**
Convolution in the spatial domain becomes simple multiplication in the frequency domain. This makes filtering faster and easier.

---

## **5. Periodicity Property**

**Formula:**


<img width="631" height="79" alt="image" src="https://github.com/user-attachments/assets/81815a85-5c45-45bf-a5bd-e23501c043ad" />


**Theory:**
The DFT is periodic in both frequency directions. The spectrum repeats at intervals equal to the image size.

---

## **6. Symmetry Property**

**Formula:**


<img width="292" height="59" alt="image" src="https://github.com/user-attachments/assets/4d629e61-7788-4abb-a7ce-503ee14dc50c" />


**Theory:**
For real images, the Fourier spectrum has conjugate symmetry. Only half the frequency data needs to be stored or processed.

---

## **7. Scaling Property**

**Formula:**


<img width="379" height="122" alt="image" src="https://github.com/user-attachments/assets/fc973bfa-ac1a-4634-ae79-7de3a8ccd183" />


**Theory:**
Shrinking an image spreads its spectrum; enlarging compresses it. This explains how image zooming affects frequency content.

---

## **3. Applications of These Properties**

* Faster and efficient filtering through convolution–multiplication property
* Edge detection and image enhancement
* Analytical study of periodic noise
* Motion estimation using shifting property
* Compression and reconstruction using symmetry and energy conservation

---
