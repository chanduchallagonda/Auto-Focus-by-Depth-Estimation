# 🎯 Auto Focus by Depth Estimation

This project replicates **camera auto-focus** functionality using **deep learning** to estimate scene depth from RGB images and simulate focus effects.

---

## 📊 Dataset
**Dataset:** NYU Depth v2  
- Contains **50,688 RGB–depth pairs** of indoor scenes.  
- Each image includes an RGB photo and a ground-truth depth map.  

---

## 🧠 Methodology
The pipeline predicts depth and uses it to create focus-enhanced images.

1. **Depth Prediction:**  
   - Models used: **ResNet-18** and **ResNet-50** pre-trained CNNs.  
   - Metrics: Loss, **MSE**, and **PSNR**.  
   - ResNet-50 achieved higher accuracy and smoother depth maps.  

2. **Post-Processing:**  
   - Applied **Gaussian** and **Median blurring** to refine predicted depth maps.  

3. **Depth Segmentation:**  
   - Used **K-Means clustering** to divide depth regions.  
   - Reordered clusters by depth intensity for consistency.  

4. **Focus Simulation:**  
   - Applied selective blurring based on clustered depth regions to mimic auto-focus.  

---

## ⚙️ Implementation Details
- **Framework:** PyTorch  
- **Optimizer:** Adam  
- **Loss:** MSELoss / BCELoss  
- **Evaluation Metrics:** MSE, PSNR  
- **Training Environment:** Google Colab (A100 GPU)  

---

## 📈 Results
| Model | Loss | MSE | PSNR |
|--------|------|------|------|
| **ResNet-18** | 0.5496 | 0.0010 | 32.91 |
| **ResNet-50** | **0.5486** | **0.0006** | **34.52** |

**ResNet-50** outperformed ResNet-18, producing sharper and more accurate depth predictions.

---

## 🚀 Key Insights
- Depth maps can be used to create realistic **auto-focus effects**.  
- Post-processing and clustering enhance depth-based visualization.  
- Deeper models like **ResNet-50** capture complex features better than shallow ones.  

---

## 🧰 Tech Stack
Python, PyTorch, NumPy, Pandas, Matplotlib, Scikit-learn

---

## 📜 Summary
This project demonstrates how deep learning can generate **depth maps** and apply them for **focus simulation**, bridging computer vision and photography.

