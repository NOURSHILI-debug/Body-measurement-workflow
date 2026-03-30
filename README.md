# Body-measurement-n8n-workflow

AI-powered system that extracts body measurements from **front + side images** using **Gemini Vision API** and an **A4 paper as scale reference**.

---

## 🚀 How It Works

1. Upload **front + side images**
2. Detect **A4 paper (21 × 29.7 cm)** for scaling
3. Gemini AI estimates body dimensions in pixels
4. Convert pixels → **cm using scale factor**
5. Generate a **clean HTML report**

---

## ⚙️ Workflow

### 1. Webhook
- `POST /measure-body`
- Inputs:
  - `front` (image)
  - `side` (image)

---

### 2. Preprocessing (Code Node)
- Validates inputs
- Converts images → Base64

---

### 3. AI Analysis (Gemini)

**Front view:**
- Shoulder width
- Chest / Waist / Hips
- Total height

**Side view:**
- Chest depth
- Stomach depth
- Back length
- Arm length
- Inseam

---

### 4. Measurement Conversion

scale = real_cm / reference_px
- Width → ×2 (circumference approx)
- Height → direct scaling

---

### 5. Output

- 📄 HTML report (downloadable)
- 📊 JSON measurements
## 🛠️ Setup

1. Import workflow into n8n  
2. Add Gemini API key
3. Activate workflow

---

## ⚠️ Notes

- Requires visible **A4 paper**
- Results are **estimates**
- Accuracy depends on pose, lighting, and camera angle

---

## 💡 Next Steps

- Improve accuracy with segmentation models
- Integrate into fashion platform 
- Build mobile/web UI
