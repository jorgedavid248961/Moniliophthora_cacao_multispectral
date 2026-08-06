<h1 align="center">
Moniliophthora Cacao Multispectral
</h1>

<p align="center">
A public multispectral dataset for cacao pod detection and instance segmentation under real field conditions.
</p>

<p align="center">
  <img src="docs/banner.png" alt="Moniliophthora Cacao Multispectral Dataset Banner" width="100%">
</p>

<p align="center">

<a href="#"><img src="https://img.shields.io/badge/DOI-Zenodo-blue"></a>
<a href="#"><img src="https://img.shields.io/badge/License-MIT-green"></a>
<a href="#"><img src="https://img.shields.io/badge/Format-COCO-orange"></a>
<a href="#"><img src="https://img.shields.io/badge/Compatible-YOLO-red"></a>
<a href="#"><img src="https://img.shields.io/badge/Python-3.10+-yellow"></a>

</p>

<p align="center">

<a href="https://colab.research.google.com/github/jorgedavid248961/Moniliophthora_cacao_multispectral/blob/main/MCM_Notebook.ipynb">
<img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab">
</a>

---

# 📖 Overview

The **Moniliophthora Cacao Multispectral Dataset (MCMD)** is a publicly available dataset designed for object detection and instance segmentation of cacao pods affected by *Moniliophthora* diseases under real field conditions.

The dataset contains multispectral imagery acquired in two spectral modalities (**RGN** and **Red Edge**) together with high-quality COCO annotations, including bounding boxes and instance segmentation masks. It is intended to support the development and evaluation of computer vision models for precision agriculture, plant disease detection, and automated crop monitoring.

In addition to the dataset, this repository provides documentation, reproducible notebooks, and utilities for data exploration, train/validation/test splitting, data augmentation, and preparation for YOLO-based training pipelines.

---

# ✨ Features

## ✨ Key Features

- 🌈 **Multispectral imagery:** Two spectral modalities are provided (**RGN** and **Red Edge**) to support research on spectral analysis for plant disease detection.

- 🎯 **High-quality annotations:** All images are manually annotated using the COCO format, including bounding boxes and instance segmentation masks.

- 🍫 **Real field conditions:** Images were acquired under natural illumination and field environments, providing realistic scenarios for computer vision applications.

- 🤖 **Deep learning ready:** Compatible with modern object detection and instance segmentation frameworks such as Ultralytics YOLO.

- 📚 **Reproducible workflow:** This repository includes Jupyter notebooks for dataset exploration, train/validation/test splitting, data augmentation, and YOLO dataset preparation.

- 📖 **Open access:** The dataset is publicly available through Zenodo and can be freely used for research and educational purposes according to its license.

---

# 📥 Download

The complete dataset is publicly available through **Zenodo**.

> **DOI:** 10.5281/zenodo.20836148

📦 **Dataset download:**

https://doi.org/10.5281/zenodo.20836148

This GitHub repository **does not host the dataset files**. Instead, it provides:

- 📖 Documentation
- 📚 Jupyter notebooks
- 🛠 Dataset preparation scripts
- 📊 Examples and visualizations
- 🤖 Utilities for YOLO training

The complete dataset, including multispectral images and COCO annotations, can be downloaded from Zenodo using the DOI above.

---

# 📂 Dataset Structure

```text
Dataset/

├── RE/
├── RGN/
├── annotations/
└── ...
```

Or include an image

```markdown
![Structure](docs/dataset_structure.png)
```

---

# 📊 Dataset Statistics

| Property | Value |
|-----------|------:|
| Images | |
| Classes | |
| Annotations | |
| Format | COCO |
| Bands | |

---

# 🏷 Classes

| ID | Class | Description |
|---:|--------|-------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |

---

# 🖼 Examples

Original image

Segmentation

Bounding boxes

Example images

---

# 🚀 Quick Start

## Clone repository

```bash
git clone https://github.com/username/repository.git
```

---

## Download dataset

Instructions...

---

## Open notebooks

```
notebooks/
```

---

# 📚 Notebooks

| Notebook | Description |
|-----------|-------------|
| 0 | Introduction |
| 1 | Download |
| 2 | Explore |
| 3 | Split |
| 4 | Data Augmentation |
| 5 | Prepare YOLO |

---

# ⚙ Workflow

```text
Zenodo
    │
    ▼
Download
    │
    ▼
Explore
    │
    ▼
Train / Validation / Test Split
    │
    ▼
Augmentation
    │
    ▼
YOLO Dataset
    │
    ▼
Training
```

---

# 📈 Results

(Optional)

Benchmark

Example results

Figures

---

# 📖 Citation

```bibtex
@dataset{
...
}
```

---

# 📜 License

Specify the license.

---

# 🙏 Acknowledgements

Funding

University

Collaborators

---

# 📧 Contact

Name

Institution

Email

LinkedIn
