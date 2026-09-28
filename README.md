# SPBDD: Sugarcane Pokkah Boeng Disease Dataset

## Repository Status

> **This repository is currently under preparation.**  
> The complete Sugarcane Pokkah Boeng Disease Dataset (SPBDD) used in the associated study is being organized for public release. The current repository may contain only part of the dataset or representative examples from some severity categories. The complete dataset, including all images and the corresponding plant-level training, validation, and test split information, will be released after the organization and verification process is completed.

## Overview

The **Sugarcane Pokkah Boeng Disease Dataset (SPBDD)** is an image dataset developed for **visual severity grading of visible symptoms of sugarcane pokkah boeng disease**.

The complete dataset used in the associated study contains **3,235 RGB images** divided into four visual severity grades:

- **Healthy**
- **Mild**
- **Moderate**
- **Severe**

The dataset was developed to support image-based visual severity grading using lightweight deep learning models and mobile-assisted applications.

The task is defined as predicting one of the four visual severity grades from a single RGB image. It is **not intended for etiological diagnosis or differential diagnosis** against other diseases or abiotic stresses.

---

## Dataset Summary

The complete SPBDD dataset used in the study contains:

| Severity grade | Number of images |
| --- | ---: |
| Healthy | 998 |
| Mild | 797 |
| Moderate | 720 |
| Severe | 720 |
| **Total** | **3,235** |

The images used in the model experiments were resized with padding to **224 × 224 pixels** while preserving the original image content as much as possible.

---

## Plant-Level Data Split

To reduce potential information leakage caused by multiple images acquired from the same plant, the dataset was partitioned at the **plant level**.

| Split | Images | Plants |
| --- | ---: | ---: |
| Training | 2,252 | 849 |
| Validation | 493 | 182 |
| Test | 490 | 182 |
| **Total** | **3,235** | **1,213** |

Images belonging to the same plant are assigned to only one of the training, validation, or test subsets.

---

## Repository Structure

After the complete dataset is released, the repository will follow the structure below:

```text
SPBDD-Sugarcane-Pokkah-Boeng-Dataset/
├── train/
│   ├── Healthy/
│   ├── Mild/
│   ├── Moderate/
│   └── Severe/
├── val/
│   ├── Healthy/
│   ├── Mild/
│   ├── Moderate/
│   └── Severe/
├── test/
│   ├── Healthy/
│   ├── Mild/
│   ├── Moderate/
│   └── Severe/
├── train.csv
├── val.csv
├── test.csv
└── README.md
```

During repository preparation, some folders may temporarily contain only part of the corresponding images.

---

## Split Files

The files `train.csv`, `val.csv`, and `test.csv` provide the image-level records associated with the plant-level split.

Each CSV file contains the following fields:

| Field | Description |
| --- | --- |
| `image_name` | Image filename |
| `image_path` | Relative path of the image within the corresponding split directory |
| `plant_id` | Identifier of the sampled plant |
| `severity` | Visual severity grade |

An example image path is:

```text
Healthy\Healthy001_01.jpg
```

The class label is determined by the corresponding severity category.

---

## Image Acquisition

The images were collected from a dedicated sugarcane pokkah boeng disease nursery at the **Guangxi Subtropical Agricultural Science New City, China (22°31′N, 107°47′E)**.

The experimental field contained multiple sugarcane cultivars and was established for pokkah boeng disease research.

Images were acquired under field conditions using a **HUAWEI nova 12 Vitality Edition (FIN-AL60)** smartphone.

The original photographs were captured at a resolution of **3072 × 4096 pixels**. The version used for model development and released in this repository consists of the processed **224 × 224 pixel images** used in the experiments.

---

## Visual Severity Grading

Severity grading was based on visible symptom characteristics in the acquired RGB images.

Three symptom-related visual anchors were considered during manual grading:

- **C — Chlorosis**
- **D — Deformation**
- **G — Growing-point involvement**

These visual anchors were used to support the manual definition of severity categories and are **not separate prediction targets of the model**.

The four severity grades are:

### Healthy

No visible pokkah boeng disease-related symptoms.

### Mild

Early visible symptoms, mainly characterized by limited chlorosis or other mild leaf abnormalities.

### Moderate

More apparent symptom development, including increased chlorosis and leaf deformation.

### Severe

Pronounced symptoms with visible involvement of the heart leaf or growing-point region.


---

## Annotation Protocol

Each image was independently evaluated by **two annotators**.

When the two initial annotations disagreed, an expert adjudicator reviewed the image and determined the final label.

The agreement between the two independent annotators was evaluated using **Cohen's kappa**.

The final labels therefore represent expert-reviewed **visual severity annotations**.

No pathogen isolation or molecular confirmation was conducted for every individual image. Accordingly, SPBDD should be used for the study of **visual symptom severity grading**, rather than as a pathogen-confirmed diagnostic dataset.

---

## Collection Time and Severity Labels

Images were collected during the disease-development period.

However:

- all four severity categories were represented across the collection period;
- collection time was **not used as a criterion for severity annotation**;
- collection date or month was **not provided as an input to the model**.

Severity labels were assigned according to visible symptoms in each image.

---

## Intended Use

SPBDD is intended to support research on:

- image-based visual severity grading of sugarcane pokkah boeng disease;
- lightweight image classification models;
- multi-scale feature representation;
- mobile and edge deployment of agricultural vision models;
- reproducible evaluation using plant-level dataset partitioning.

---

## Limitations

Users should consider the following limitations when using the dataset:

1. SPBDD was collected from a specific experimental field and growing environment.
2. The dataset focuses on visible severity grading rather than pathogen-confirmed etiological diagnosis.
3. Performance obtained on SPBDD should not be assumed to represent performance across different regions, cultivars, devices, seasons, or other field environments without additional evaluation.

---

## Associated Study

This dataset was developed for the study:

**Severity Grading of Early Visible Symptoms of Sugarcane Pokkah Boeng Disease Based on Multi-Scale Dynamic Feature Fusion and Channel-Spatial Interaction: An On-Device Framework**

The manuscript is associated with research submitted to **Smart Agricultural Technology**.

---

## Citation

Citation information will be added after publication of the associated article.

---

## Repository Updates

This repository is currently being organized and verified.

The complete SPBDD dataset used in the associated study will be released after dataset organization and consistency checking are completed. Future updates may also include implementation code and additional documentation.

A versioned release will be provided for the dataset corresponding to the associated study.