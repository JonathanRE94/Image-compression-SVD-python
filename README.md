<img width="685" alt="image" src="https://github.com/user-attachments/assets/e853cd60-cd6f-4118-b261-331d11f9f3fa" />


# Image Compression using Singular Value Decomposition (SVD)

This repository contains a **Python implementation of image compression** using the **Singular Value Decomposition (SVD)** method.  
Developed as part of **Linear Algebra coursework**, it demonstrates **low-rank approximation** of images, trade-offs between **compression ratio** and **reconstruction error**, and practical image compression.

---

## 📖 Methodology

If `Img` is an \(m \times n\) grayscale matrix, a rank-\(r_0\) approximation is:

\[
Img_{r_0} = U_{r_0} \Sigma_{r_0} V_{r_0}^T
\]

where:
- \(U_{r_0}\): first \(r_0\) left singular vectors  
- \(V_{r_0}\): first \(r_0\) right singular vectors  
- \(\Sigma_{r_0}\): diagonal matrix with first \(r_0\) singular values  

Compression ratio:

\[
CR(r_0) = \frac{r_0 \times (1+n+m)}{\text{size of Img}}
\]

---

## ⚙️ Implemented Functions
- `get_compression_ratio(img, r)` → Returns compression ratio  
- `get_threshold_rank(img, thrsld)` → Finds smallest rank \(r_0\) such that \(\sigma_{r_0}/\sigma_0 \leq thrsld\)  
- `compress_img(img, r)` → Returns \(U_r, V_r, S_r\) for given rank  
- `rebuild_img(U, V, S)` → Reconstructs image from compressed matrices  
- `get_compression_error(img, r)` → Normalized 2-norm reconstruction error  

---

## 📊 Example Results
Using a sample grayscale image:

- **Threshold:** 0.01  
- **Rank Obtained:** 48  
- **Compression Ratio:** 0.12  
- **Reconstruction Error:** 0.015  

| Rank (r) | Compression Ratio | Error |
|----------|------------------|-------|
| 10       | 0.03             | 0.08  |
| 25       | 0.07             | 0.04  |
| 50       | 0.13             | 0.015 |

---


---

## 🚀 How to Run
```bash
git clone https://github.com/yourusername/svd-image-compression.git
cd svd-image-compression
pip install -r requirements.txt
python src/mae_501_project_code.py
