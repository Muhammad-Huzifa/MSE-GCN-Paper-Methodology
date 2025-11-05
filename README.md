# 🧠 MSE-GCN — Sign Language Recognition (Paper Methodology)

This repository reproduces the **MSE-GCN (Multi-Stream Enhanced Graph Convolutional Network)** methodology for **Sign Language Recognition (SLR)** using skeleton-based landmarks extracted from videos.
It provides an efficient and interpretable approach to model **spatial-temporal motion patterns** for isolated sign recognition tasks.

---

## 🚀 Highlights

* **Multi-Stream Enhanced GCN (MSE-GCN):** Models **Joint**, **Bone**, and **Motion** streams for robust spatio-temporal representation.
* **Efficient Landmark Extraction:** Uses **MediaPipe Holistic** to extract 65 landmarks per frame.
* **Feature Engineering:** Computes joint positions, bone vectors, and angles for dynamic body motion understanding.
* **Optimized for Lightweight Deployment:** Achieves strong accuracy–efficiency trade-off with moderate parameters.
* **Reproducible Implementation:** Includes both landmark extraction and model training notebooks.

---

## 📁 Project Structure

```
MSE-GCN-Paper-Methodology/
│
├── src/
│   ├── landmarks extraction.ipynb     # Landmark extraction pipeline using MediaPipe Holistic
│   ├── mse-gcn-67-3500k.ipynb         # Full training notebook (MSE-GCN architecture and pipeline)
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## 📦 Dataset

This implementation uses the **WLASL2000** dataset (resized version):
🔗 **[Kaggle – WLASL2000 Resized Dataset](https://www.kaggle.com/datasets/sttaseen/wlasl2000-resized)**

Each video contains sign language gestures annotated with gloss labels.
The dataset supports **300+ isolated sign classes**, ideal for benchmark evaluation of lightweight SLR models.

---

## 🧩 Pipeline Overview

### 1️⃣ **Landmark Extraction**

* Extracts **65 skeletal keypoints per frame**:

  * 23 body landmarks
  * 21 left-hand landmarks
  * 21 right-hand landmarks
* Generates two feature streams:

  * **Joint Stream:** Raw (x, y, z, visibility) coordinates
  * **Bone Stream:** Computed from joint connectivity (lengths + angles)
* Saves outputs in `.npz` format for each video.

### 2️⃣ **MSE-GCN Training**

* Multi-stream network combining **GCNs** for spatial learning and **temporal convolutions** for sequence modeling.
* Integrates:

  * **Multi-stream fusion** (joint + bone + motion)
  * **Residual graph units** for stability
  * **Label smoothing, dropout, mixup augmentation**
* Tested on **NSLT-300** and **WLASL subsets**, achieving accuracy close to SOTA baselines.

---

## ⚙️ Installation

```bash
git clone https://github.com/Muhammad-Huzifa/MSE-GCN-Paper-Methodology.git
cd MSE-GCN-Paper-Methodology
pip install -r requirements.txt
```

---

## 📊 Performance Summary

| Dataset  | # Classes | Parameters | Top-1 Accuracy |
| -------- | --------- | ---------- | -------------- |
| NSLT-300 | 300       | ~0.35M      | **67.0%**      |

> Results reproduced using MSE-GCN training configuration (`mse-gcn-67-3500k.ipynb`)
> and landmarks extracted via MediaPipe Holistic (`landmarks extraction.ipynb`).

---

## 🔍 Applications

* Isolated Sign Language Recognition (ISLR)
* Continuous Sign Language Recognition (CSLR)
* Gesture / Action Recognition
* Real-time Sign Understanding Systems

---

## 👨‍🔬 Author

**Muhammad Huzaifa**
Sign Language Recognition Researcher | Deep Learning Engineer
🎓 BS Computer Science (2021–2025) — *Islamia College University, Peshawar*
📬 **[mhuzaifa3202@gmail.com](mailto:mhuzaifa3202@gmail.com)**
🌐 **[GitHub Profile](https://github.com/Muhammad-Huzifa)**

---

## 🧾 Citation (if used in research)

If this project helps your research or experiments, please cite:

```
@misc{huzaifa2025msegcn,
  author = {Muhammad Huzaifa},
  title = {MSE-GCN for Sign Language Recognition (Paper Methodology)},
  year = {2025},
  url = {https://github.com/Muhammad-Huzifa/MSE-GCN-Paper-Methodology}
}
```

---

✨ *An efficient multi-stream graph-based framework designed to advance Sign Language Recognition with precise spatial-temporal feature modeling.*
