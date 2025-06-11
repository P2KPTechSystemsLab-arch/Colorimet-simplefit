

# 🌈 Simplified Optode-Based Soil pH Estimation Toolkit

This script performs calibrated **pH mapping from optode images** using R/G ratio analytics and colorimetric transformation. It is designed for environmental scientists, agronomists, and developers working in soil chemistry, pH dynamics, and digital soil mapping.

---

## 🎯 Purpose

This toolkit estimates pH from RGB optode sensor images using a **logistic calibration model**. It visualizes:

* The original RGB image
* R/G intensity ratio map (divergent colormap)
* Estimated pH map with continuous gradient scale

It supports reproducible workflows in soil monitoring, rhizosphere research, and environmental diagnostics.

---

## 🧠 Methodology

1. **Calibration Curve**
   Converts R/G ratios to pH using a logistic model:

  

2. **Image Processing Pipeline**

   * RGB channel extraction
   * R/G ratio computation with clipping
   * pH transformation and visualization

3. **Visualization**

   * RGB image
   * Diverging color map (R/G)
   * pH-mapped custom legend and plasma visualization

---

## 📦 Requirements

| Package         | Version |
| --------------- | ------- |
| `opencv-python` | ≥4.5    |
| `numpy`         | ≥1.21   |
| `matplotlib`    | ≥3.4    |
| `scikit-image`  | ≥0.19   |

Install with:

```bash
pip install opencv-python numpy matplotlib scikit-image
```

---

## 🚀 Usage Example

```python
from skimage import io
import cv2 as cv
import numpy as np

# Load & resize image
image = io.imread("path/to/image.png")
image = cv.resize(image[:, :, :3], (512, 512))

# Compute R/G ratio
R = image[:, :, 0].astype(np.float32)
G = image[:, :, 1].astype(np.float32)
ratio = R / (G + 1e-6)

# Apply pH calibration
def ratio_to_pH(r): return X0 - dx * np.log10((A1 - A2)/(r - A2) - 1)
```

Full script available in [`Main_model_Optode_pH.ipynb`](https://github.com/P2KPTechSystemsLab-arch/pHChromoCODE/blob/main/Main%20model_Optode_pH%20%28Fast%20run_Group%29.ipynb)

---

## 📊 Output

* **Original RGB optode image** 
* **R/G ratio heatmap**  (
* **Plasma color map for R/G** 
* **Calibrated pH gradient from 4.0 to 8.5** 

