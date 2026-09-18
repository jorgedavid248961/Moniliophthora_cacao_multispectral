<h1 align="center">
Moniliophthora Cacao Multispectral
</h1>

<p align="center">
Multispectral Red-Edge (RE) and RGN image dataset of cocoa pods for Frosty Pod Rot (<em>Moniliophthora roreri</em>) detection and instance segmentation under real field conditions.
</p>

<p align="center">
  <img src="docs/banner.png" alt="Moniliophthora Cacao Multispectral Dataset Banner" width="100%">
</p>

<p align="center">

<a href="https://doi.org/10.5281/zenodo.20836148">
    <img src="https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20836148-blue?logo=zenodo&logoColor=white" alt="DOI">
</a>

<a href="https://zenodo.org/records/20836148">
    <img src="https://img.shields.io/badge/Dataset-Zenodo-1682D4?logo=zenodo&logoColor=white" alt="Dataset">
</a>

<a href="https://creativecommons.org/licenses/by/4.0/">
    <img src="https://img.shields.io/badge/Data%20License-CC%20BY%204.0-lightgrey" alt="Data License">
</a>

<a href="LICENSE">
    <img src="https://img.shields.io/badge/Code%20License-MIT-green" alt="Code License">
</a>

<a href="#">
    <img src="https://img.shields.io/badge/Format-COCO-orange" alt="COCO Format">
</a>

<a href="https://github.com/ultralytics/ultralytics">
    <img src="https://img.shields.io/badge/Compatible-Ultralytics%20YOLO-red" alt="Ultralytics YOLO">
</a>

<a href="#">
    <img src="https://img.shields.io/badge/Python-3.10+-yellow?logo=python&logoColor=white" alt="Python">
</a>

</p>

<p align="center">

<a href="https://colab.research.google.com/github/jorgedavid248961/Moniliophthora_cacao_multispectral/blob/main/MCM_Notebook.ipynb">
<img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab">
</a>

</p>

---

# Overview

Cocoa production is a major socio-economic activity across Latin America, and *Moniliophthora roreri* — the causal agent of Frosty Pod Rot — is responsible for yield losses ranging from 30% to 90% in severely affected plantations. Conventional disease management relies on manual visual inspection, which is subjective, labor-intensive, and typically detects the disease only after visible damage has occurred. Multispectral imaging in the Red Edge (RE) and Near-Infrared bands can reveal pathogen-induced physiological stress before symptoms become visible to the naked eye, but public, annotated multispectral datasets for cocoa are scarce.

This repository accompanies the **Moniliophthora Cacao Multispectral Dataset (MCMD)**, a high-resolution multispectral image dataset of cocoa pods (*Theobroma cacao* L.) collected under real field conditions in Colombia to study the progression of Frosty Pod Rot. The dataset provides two spectral configurations — **Red Edge (RE)** and **Red-Green-Near Infrared (RGN)** — together with pixel-level instance segmentation annotations produced in the Computer Vision Annotation Tool (CVAT), released in COCO and YOLO formats.

This repository does not host the dataset itself; it provides documentation, reproducible notebooks, and utilities for exploration, splitting, augmentation, and preparation for YOLO-based training pipelines.

---

# Value of the Dataset

- Provides multispectral imagery (RE and RGN bands) beyond the visible spectrum, enabling research into spectral signatures associated with early physiological changes in cocoa pods.
- Covers healthy pods and three disease-progression stages of Frosty Pod Rot (Latent, Spots, Sporulation), supporting studies of disease progression from both visual and spectral perspectives.
- Annotations are released in COCO (.json), YOLO bounding box (.txt), and YOLO segmentation (.txt) formats for direct integration into common computer vision pipelines.
- Suitable for classification, object detection, and instance segmentation benchmarking in precision agriculture and crop disease monitoring.
- Enables direct comparison studies between multispectral and traditional RGB imagery for early disease detection in tropical agriculture.

---

# Data Collection

Images were captured during three field campaigns in February 2026 at two locations in Colombia:

| Campaign | Location | Date | Time |
|---|---|---|---|
| 1 | Maceo, Antioquia (commercial cocoa farm) | Feb 6, 2026 | 13:00–17:00 |
| 2 | Granja Yariguíes, Santander (Fedecacao / Compañía Nacional de Chocolates) | Feb 19, 2026 | 13:00–16:00 |
| 3 | Granja Yariguíes, Santander | Feb 20, 2026 | 08:00–12:00 |

The dataset includes cocoa pods from the **CNCH12**, **CNCH13**, and **SCI-1** clone varieties, selected for their representativeness of Colombian cocoa production and their differing physiological responses during Frosty Pod Rot progression.

Images were acquired with **MAPIR Survey3N** multispectral cameras under natural ambient sunlight (no artificial illumination), at distances of 30–320 cm from the fruit, using fixed settings:

| Parameter | Value |
|---|---|
| Exposure time | 1/60 s |
| ISO sensitivity | 400 |
| Resolution | 4000 × 3000 px (12 MP) |
| Format | JPEG (.jpg) |

Prior to capture, each cocoa pod was assessed in the field by a cocoa pathology specialist and assigned to one of four disease categories, later linked to the corresponding polygon annotation.

---

# Dataset Structure

```
Moniliophthora_cacao_multispectral/
├── RE/
│   ├── images/
│   ├── coco_label/
│   ├── yolo_bbox_label/
│   └── yolo_seg_label/
├── RGN/
│   ├── images/
│   ├── coco_label/
│   ├── yolo_bbox_label/
│   └── yolo_seg_label/
├── DataAugmentation/
│   ├── RE/
│   │   ├── images/
│   │   ├── coco_label/
│   │   ├── yolo_bbox_label/
│   │   └── yolo_seg_label/
│   └── RGN/
│       ├── images/
│       ├── coco_label/
│       ├── yolo_bbox_label/
│       └── yolo_seg_label/
└── splits/
    ├── train/
    │   ├── RE_COCO.json
    │   └── RGN_COCO.json
    ├── valid/
    │   ├── RE_COCO.json
    │   └── RGN_COCO.json
    └── test/
        ├── RE_COCO.json
        └── RGN_COCO.json
```

**File naming convention**

| Type | Pattern | Example |
|---|---|---|
| Original image | `YYYY_MMDD_HHMMSS_ID.JPG` | `2026_0206_132017_008.JPG` |
| Augmented image | `YYYY_MMDD_HHMMSS_ID_aug_(uniqueID+originalID).JPG` | `2026_0219_153610_007_aug_979.JPG` |

YOLO annotation files (`.txt`, bounding box and segmentation) share the exact filename of their corresponding image.

---

# Dataset Statistics

| Property | Value |
|---|---:|
| Original images | 1,032 (RE: 441 · RGN: 591) |
| Spectral configurations | 2 (Red Edge, Red-Green-NIR) |
| Original annotated instances | 1,688 |
| Additional instances from augmentation (train split only) | 1,878 |
| Pathological classes | 4 |
| Image resolution | 4000 × 3000 px |
| Image format | JPG |
| Annotation formats | COCO (.json), YOLO bbox (.txt), YOLO segmentation (.txt) |
| Annotation tool | CVAT (Computer Vision Annotation Tool) |
| Total dataset size | 8.2 GB |

**Table 1. Distribution of original images and annotated instances by spectral band and pathological class**

| Class | RE (441 images) | RGN (591 images) | Total Instances |
|---|---:|---:|---:|
| Healthy | 333 | 578 | 911 |
| Latent | 108 | 125 | 233 |
| Spots | 152 | 187 | 339 |
| Sporulation | 70 | 135 | 205 |
| **Total** | **663** | **1,025** | **1,688** |

---

# Classes

| ID | Class | Description |
|---:|---|---|
| 1 | Healthy | Cocoa pod with no visible symptoms of Frosty Pod Rot. |
| 2 | Latent | Early stage of Frosty Pod Rot progression, prior to advanced external symptoms. |
| 3 | Spots | Intermediate stage, with visible necrotic spot lesions on the pod surface. |
| 4 | Sporulation | Advanced stage, with visible fungal sporulation on the pod surface. |

Class labels were assigned in the field by a cocoa pathology specialist prior to image capture and later linked to the corresponding polygon annotation in CVAT; bounding boxes were derived automatically from the polygon coordinates on export.

---

# Data Split and Augmentation

The dataset is partitioned at the image level, preserving class distribution, into:

- **Training:** 80%
- **Validation:** 10%
- **Testing:** 10%

To mitigate class imbalance, a geometric data augmentation pipeline (Albumentations library) was applied **exclusively to the training split**, preserving spectral integrity by avoiding radiometric transformations:

- Vertical and horizontal flips
- Random rotations (limited to 30°)
- Affine transformations (scaling 0.9–1.1, translation, shearing)
- Mild perspective changes

Augmentation targeted the underrepresented diseased classes (Latent, Spots, Sporulation); the Healthy class was left unaugmented.

**Table 2. Additional images and annotated instances generated through data augmentation (training subset only)**

| Class | RE aug (641 images) | RGN aug (1,179 images) | Total Instances |
|---|---:|---:|---:|
| Healthy | 0 | 0 | 0 |
| Latent | 225 | 411 | 636 |
| Spots | 186 | 406 | 592 |
| Sporulation | 244 | 406 | 650 |
| **Total** | **655** | **1,223** | **1,878** |

Resulting class balance in the final training subset (original + augmented):

| Band | Healthy | Latent | Spots | Sporulation |
|---|---:|---:|---:|---:|
| RGN | 22.61% | 25.01% | 27.21% | 25.16% |
| RE | 22.45% | 26.24% | 25.99% | 25.32% |

---

# Download

The complete dataset is publicly available through **Zenodo**.

> **DOI:** 10.5281/zenodo.20836148

**Dataset download:** https://doi.org/10.5281/zenodo.20836148

This GitHub repository does not host the dataset files. It provides documentation, notebooks, dataset preparation scripts, and utilities for YOLO training.

---

# Quick Start

## Clone repository

```bash
git clone https://github.com/jorgedavid248961/Moniliophthora_cacao_multispectral.git
cd Moniliophthora_cacao_multispectral
```

## Download dataset

1. Visit the dataset record on Zenodo: https://zenodo.org/records/20836148
2. Download the compressed dataset archive.
3. Extract it into a `data/` folder at the root of the repository (or update the paths referenced in the notebooks).

## Open notebooks

```bash
jupyter notebook notebooks/
```

Alternatively, use the **Open in Colab** badge above.

---

# Notebooks

| Notebook | Description |
|---|---|
| 0 | Introduction to the dataset and repository |
| 1 | Download the dataset from Zenodo |
| 2 | Exploration and visualization of class and band distributions |
| 3 | Reproduction of the 80/10/10 train/validation/test split |
| 4 | Geometric data augmentation pipeline (Albumentations) |
| 5 | Conversion of COCO annotations to YOLO detection/segmentation format |

---

# Workflow

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

# Results

*(Optional — add benchmark metrics and figures here once available.)*

---

# Limitations

- The dataset addresses Frosty Pod Rot (*Moniliophthora roreri*) exclusively; other common cocoa pathogens such as *Phytophthora* and Witches' Broom are not covered.
- Data collection was geographically limited to Colombia (Santander and Antioquia).
- Spectral data is constrained to the band-pass filters and sensitivity of the MAPIR Survey3N sensor in the RE and RGN configurations; other regions of the spectrum remain unexplored in this resource.

---

# Citation

```bibtex
@dataset{david_rodriguez_2026_mcmd,
  author    = {David Rodríguez, Jorge Alexander and
               Alvarado Molina, Joan Francisco and
               Velásquez, David and
               Arias-Correa, Mauricio and
               Restrepo-Arias, Juan F and
               Sanin-Villa, Daniel and
               Giraldo-Pérez, Juan Pablo.},
  title     = {Multispectral Red-Edge and RGN image dataset of cocoa pods for
               Frosty Pod Rot (Moniliophthora roreri) detection and segmentation},
  year      = {2026},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.20836148},
  url       = {https://doi.org/10.5281/zenodo.20836148}
}
```

---

# License

- **Dataset** (images and annotations, hosted on Zenodo): [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
- **Code** in this repository (notebooks and utilities): MIT License — see the [LICENSE](LICENSE) file.

---

# Ethics and Declarations

This work does not involve human subjects, animal experiments, or data collected from social media platforms. The authors declare no known competing financial interests or personal relationships that could have influenced the work reported.

---

# Acknowledgements

**Funding:** This work was supported by Universidad EAFIT through the *Becas Talento en Investigación* program.

The authors also thank **Compañía Nacional de Chocolates** for its continuous support and contributions to this research.

---

# Authors

| Author | Role (CRediT) | ORCID |
|---|---|---|
| Jorge Alexander David Rodríguez * | Investigation, Data curation, Writing – Original draft | 0009-0002-6718-9955 |
| Joan Francisco Alvarado Molina | Conceptualization, Methodology | 0009-0008-5611-3553 |
| Mauricio Arias-Correa | Supervision, Conceptualization | 0000-0003-0619-235X |
| Juan F. Restrepo-Arias | Supervision | 0000-0002-9689-1017 |
| Daniel Sanin-Villa | Supervision | 0000-0001-6853-340X |
| Juan Pablo Giraldo-Pérez | Supervision | 0000-0001-6499-5906 |
| David Velásquez | Supervision, Writing – Review & Editing | 0000-0002-9949-8915 |

*\* Corresponding author*

All authors are affiliated with the Escuela de Ciencias Aplicadas e Ingeniería, Universidad EAFIT, 050022 Medellín, Colombia.

---

# Contact

**Jorge Alexander David Rodríguez**
Escuela de Ciencias Aplicadas e Ingeniería, Universidad EAFIT, Medellín, Colombia
jadavidr@eafit.edu.co
