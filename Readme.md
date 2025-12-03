# H-003 | The AI Creative Studio
**Tagline:** A generative AI pipeline that transforms a single logo + product image into 10+ high-quality marketing creatives with AI-written captions — fully automated in under 60 seconds.

---

## 1. The Problem (Real-World Scenario)

### **Context**  
Modern marketing teams spend countless hours creating multiple ad variations for campaigns — social ads, display banners, A/B tests, retargeting creatives, etc. Designers have to manually adjust backgrounds, lighting, and compositions to produce 10–20 versions of the same product photo.

### **The Pain Point**  
This repetitive creative production:

- Slows down campaign launches  
- Blocks fast experimentation  
- Introduces inconsistency across creatives  
- Requires constant designer bandwidth even for simple variations  

A brand wanting 15 creatives for 5 products → **75 manual images**.

### **My Solution**  
I built **CreativeForge**, a fully automated pipeline.  
A user simply uploads a product image and brand logo, and the system:

- Generates **10+ ad-ready creative variations**  
- Writes **matching advertising captions**  
- Exports everything as a **ZIP file**  
- Works end-to-end **without any manual editing**

Marketing teams get studio-quality visuals instantly, accelerating iteration and improving brand consistency.

---

## 2. Expected End Result

### **For the User**

**Input:**  
Upload two files:

- `logo.png`  
- `product.jpg`  

**Action:**  
Click “Generate Creatives”.

**Output:**  
A downloadable ZIP file containing:

- 10+ high-resolution AI-generated creatives  
- A `captions.json` (or CSV) file mapping each image → caption  
- Brand-consistent looks  
- Optional transparent or composited variants  

---

## 3. Technical Approach

This project goes beyond a simple *“text-to-image prompt generator.”*  
It mimics a real creative-production pipeline with:

- Preprocessing  
- Prompt engineering  
- Controlled variation sampling  
- Caption generation  
- Packaging  
- Distribution  

---

## **System Architecture**

### **1. Preprocessing (Image Normalization)**  
- Resize images with preserved aspect ratio  
- Convert logo to RGBA  
- Background removal for product images  
- Save canonical assets:  
  - `preprocessed_logo.png`  
  - `preprocessed_product.png`  
  - `preprocessed_product_no_bg.png`

### **2. Prompt Templates & Variation Strategy**  
We define themes such as:

- Minimal studio  
- Dark premium  
- Neon modern  
- Pastel soft  
- Nature green  
- Geometry shapes  
- Summer vibe  
- Winter frost  
- Abstract art  
- Luxury glass render  

Each theme ensures a unique creative variation.

### **3. Image Generation (DALL·E 3 or Stable Diffusion)**  
- Generate 10+ creatives  
- Img2Img conditioning for product retention  
- Deterministic seeds for reproducibility  
- High-resolution output

### **4. Caption Generation (GPT-4o / Gemini)**  
Each creative is passed to an LLM with a marketing-optimized prompt:

> “Write an 8–12 word premium advertising caption for this product creative.”

### **5. Packaging**  
- All creatives saved in `/outputs/creatives/`  
- Captions saved in `captions.json`  
- Everything compressed into `creative_package.zip`

---

## 4. Tech Stack

- **Language:** Python 3.11  
- **Image Generation:** DALL·E 3 API / Stable Diffusion XL  
- **Text Generation:** GPT-4o / Gemini  
- **Image Processing:** Pillow, NumPy  
- **Interface:** Colab / Gradio (optional)  
- **Packaging:** Python `zipfile` module  

---
## colab link
https://colab.research.google.com/drive/1RR85gvs3WMzTEt8TKwe-xbx80H7LC2ff?usp=sharing
