<h1 align="center">
CocoaMoniliaDataSet / Moniliophthora Cacao Multispectral
</h1>

<p align="center">
A cocoa pod dataset to detect and classify Monilia roreri in real conditions[cite: 2].
</p>

<p align="center">
  <img src="docs/banner.png" alt="Dataset Banner" width="100%">
</p>

<p align="center">
<a href="https://doi.org/10.5281/zenodo.17716661">
    <img src="https://img.shields.io/badge/DOI-10.5281%2Fzenodo.17716661-blue?logo=zenodo&logoColor=white" alt="DOI">
</a>

<a href="https://zenodo.org/records/17716661">
    <img src="https://img.shields.io/badge/Dataset-Zenodo-1682D4?logo=zenodo&logoColor=white" alt="Dataset">
</a>

<a href="LICENSE">
    <img src="https://img.shields.io/badge/License-CC%20BY%204.0-green" alt="License">
</a>

<a href="https://github.com/joanfco30/CocoaMoniliaDataSet">
    <img src="https://img.shields.io/badge/GitHub-Repository-black?logo=github" alt="GitHub">
</a>
</p>

---

# 📖 Overview

The **CocoaMoniliaDataSet** is a dataset created to detect and classify *Monilia roreri* in real conditions[cite: 2]. 

The dataset comprises 1953 images in total[cite: 2]. It includes RGB images of cocoa pods affected by *Monilia roreri* and healthy cocoa pods, along with their respective annotation files[cite: 2]. The images were collected from cocoa crops in Santander, Colombia, and a local farm "Bosque Adentro" located in San Luis, Antioquia, Colombia[cite: 2].

For a more comprehensive and detailed description of the methodology and the dataset, please refer to the file named Articulo.

---

# ✨ Features

*   **Hierarchical Organization:** The repository is organized into a hierarchical structure designed for immediate integration into computer vision pipelines[cite: 1].
*   **Standardized Splits:** The dataset is partitioned into Training (80%), Validation (10%), and Testing (10%) sets to support standardized machine learning workflows[cite: 1]. These predefined splits are provided in `.txt` files within the repository to ensure reproducible and comparable evaluations[cite: 2].
*   **Traceable Naming:** To ensure consistency and facilitate data traceability, a standardized naming convention was applied to all files[cite: 1]. Original images are named using a timestamp-based structure `YYYY_MMDD_HHMMSS_ID.JPG` (e.g., `2026_0206_132017_008.JPG`)[cite: 1]. 
*   **Data Augmentation:** For the Data Augmentation subset, the original timestamp is preserved, and a suffix is appended to identify the transformed version[cite: 1].

---

# 📥 Download

The dataset developed in this study is publicly available in the Zenodo repository[cite: 2].

> **DOI:** 10.5281/zenodo.17716661[cite: 2]

📦 **Dataset download:**
https://zenodo.org/records/17716661[cite: 2]

You can also visit the associated GitHub Repository at:
https://github.com/joanfco30/CocoaMoniliaDataSet[cite: 2]

---

# 📂 Dataset Structure

At the root level, the dataset is divided into three main directories: `RE`, `RGN`, and `DataAugmentation`[cite: 1]. 
*   The `RE` and `RGN` directories correspond to the two spectral configurations[cite: 1]. 
*   Each contains an `images` directory and three annotation directories: `coco_label`, `yolo_bbox_label`, and `yolo_seg_label`[cite: 1]. 
*   This structure provides the corresponding annotations in COCO, YOLO bounding box, and YOLO segmentation formats[cite: 1].

Additionally, the dataset includes specific directories for images and masks:
*   `COCO_annotations`: This directory contains the annotations of the cocoa pods represented in four JSON files[cite: 2].
*   `YOLO_annotations`: Contains four directories (`h0`, `m1`, `m2`, and `m3`) with the YOLO annotations inside them in `.txt` format[cite: 2].
*   `mask_segmentation`: Includes the annotations in segmentation mask 1.1 format using `.png` images[cite: 2].
*   `cocoapod_images`: Split into four directories (`h0`, `m1`, `m2`, and `m3`) which store the original images in `.jpg` format linked to the respective annotation files[cite: 2].

The dataset splits are available in the `splits/` directory, which contains subfolders for `train`, `valid`, and `test`[cite: 1]. Each folder includes specific COCO-formatted files (`RE_COCO.json` and `RGN_COCO.json`)[cite: 1].

---

# 🏷 Classes

The dataset comprises four labeled classes[cite: 2]:

| ID | Class | Description |
|---:|--------|-------------|
| 1 | **h0** | Healthy cocoa pod[cite: 2]. |
| 2 | **m1** | First Monlilia cycle, humps[cite: 2]. |
| 3 | **m2** | Second - third Monilia cycle of the disease[cite: 2]. |
| 4 | **m3** | Fourth cycle[cite: 2]. |

---

# 📜 License

The dataset is distributed under the **Creative Commons Attribution 4.0 International License (CC BY 4.0)**[cite: 2].

---

# 🙏 Acknowledgements

**Funding:** This research and the APC were funded by Universidad EAFIT under grant number 819430[cite: 9].

---

# 📖 Citation

If you use this dataset in your research, please cite the associated article:

Alvarado, J., Restrepo-Arias, J. F., Velásquez, D., Branch-Bedoya, J. W., & Maiza, M. (2026). *CocoaMoniliaDataSet: A cocoa pod dataset to detect and classify Monilia roreri in real conditions*. Data in Brief[cite: 2].
