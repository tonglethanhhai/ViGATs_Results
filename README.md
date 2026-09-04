# ViGATs: Vision Graph Attention Networks for Enhanced Plant Leaf Disease Classification

> [!IMPORTANT]
> **DOUBLE-BLIND PEER REVIEW CONFIDENTIALITY NOTICE**  
> This repository contains supplementary implementation code, experimental artifacts, and evaluation materials submitted exclusively for **Double-Blind Peer Review** in the *Journal of Information and Telecommunication (JIT)* (Manuscript Ref.: Ms. No. 266350252).  
> All author identities and institutional affiliations have been strictly anonymized in compliance with double-blind evaluation policies. Unauthorized copying, distribution, or public dissemination is strictly prohibited prior to formal publication.

---

## 📌 Repository Overview

This repository provides the official implementation of the **ViGATs (Vision Graph Attention Network)** architecture, accompanying model verification routines, and experimental logs for reproducible research.

```text
ViGATs_Results/
├── ViGATs_Architecture.ipynb    # Complete model architecture definition, layer breakdown & FLOPs profiling
├── paper_revised/               # Revised manuscript files (Clean & Marked copies for review)
├── result/                      # Quantitative evaluation logs, performance metrics, and comparison tables
└── reviewer_coment/             # Point-by-point revision responses and review tracking
```

---

## 🔬 Architectural Summary

**ViGATs** introduces an *Edge-Difference Multi-Head Graph Attention Convolution (GATConv)* mechanism with grouped linear projections, learning adaptive, context-sensitive attention weights among neighboring image patches in dynamically constructed graphs.

* **Model Family**: Vision Graph Attention Network (Vision GNN)
* **Input Resolution**: $64 \times 64 \times 3$ (optimized for edge agricultural environments)
* **Total Parameters**: **4.67 M**
* **Computational Footprint**: **1.13 GFLOPs**
* **Primary Innovation**: Edge-Difference Multi-Head GATConv replacing conventional unweighted Max-Relative convolutions.

---

## 📊 Evaluation Benchmark Highlights

Evaluated across diverse plant disease benchmarks using **5-fold stratified cross-validation**:

| Dataset | Type / Domain | Classes | Protocol | ViGATs Accuracy |
|:---|:---|:---:|:---|:---:|
| **PlantVillage** | Controlled Laboratory | 38 | 5-Fold Stratified CV | **99.64%** |
| **Maize Leaf Disease** | Real-world Field (Smartphones) | 3 | 5-Fold Stratified CV | **99.28%** |
| **Rice Leaf V2** | Field-acquired Samples | 4 | 5-Fold Stratified CV | **98.45%** |
| **PlantRaw** | Multi-crop In-the-wild Benchmark | 35 | Standard Split | **86.12%** |
| **IIITDMJ Maize** | Cross-domain Aerial Drone Transfer | 4 | Drone Transfer OOD | **96.88%** |
| **Tiny ImageNet** | General Vision Benchmark | 200 | Pretraining / Validation | **Competitive** |

*Overall average classification accuracy across all plant disease benchmarks: **96.09%**.*

---

## 🚀 Environment Setup & Model Inspection

To verify the model architecture, parameter count, and tensor flow:

### 1. Requirements
* Python $\ge$ 3.9
* PyTorch $\ge$ 2.0 (CUDA recommended for GPU acceleration)
* torchvision
* NumPy, SciPy

### 2. Running the Architecture Inspection Notebook
Clone or open the repository directly, then run the self-contained Jupyter notebook:

```bash
jupyter notebook ViGATs_Architecture.ipynb
```

The notebook contains:
1. Complete PyTorch module implementation of **GATConv** and the **ViGATs** backbone.
2. Layer-wise parameter breakdown and tensor dimension tracking.
3. Model FLOPs verification matching the reported manuscript specifications (4.67M params, 1.13 GFLOPs).

---

## 🔒 Citation & Licensing

*This code and artifact bundle is currently under double-blind peer review. Formal bibliographic information and a permissive open-source license (MIT) will be added upon final manuscript acceptance.*
