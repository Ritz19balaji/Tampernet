# 🛡️ TamperNet — Image Tampering Detection Using Deep Learning & Forensic Feature Analysis

**Deep learning–based digital image forensics system for detecting manipulated images using semantic and forensic feature analysis**

**Dual Branch CNN • MobileNetV2 • Forensic Attention Transformer • Computer Vision • Digital Forensics**

---

## 🎯 What It Does

TamperNet is a **deep learning-based image tampering detection system** designed to identify manipulated digital images by combining **high-level semantic information with low-level forensic evidence**.

The system uses a **Dual Branch CNN architecture** to analyze images through two complementary pathways:

* **Global Semantic Branch** — captures high-level visual and contextual features using a pre-trained **MobileNetV2** backbone.
* **Forensic Feature Branch** — analyzes manipulation-related artifacts such as **noise inconsistencies, edge artifacts, and compression traces**.

The extracted representations are combined using a **Forensic Attention Transformer**, allowing the model to focus on informative forensic signals before making the final tampering prediction.

The system achieved **93.6% accuracy across 12,615 test samples**.

---

## 📌 Project Overview

| **Category**      | **Details**                                         |
| ----------------- | --------------------------------------------------- |
| **Project**       | TamperNet                                           |
| **Duration**      | October 2024 – April 2025                           |
| **Team Size**     | 2                                                   |
| **Domain**        | Digital Forensics / Deep Learning / Computer Vision |
| **Architecture**  | Dual Branch CNN + Forensic Attention Transformer    |
| **Backbone**      | MobileNetV2                                         |
| **Datasets**      | CASIA V2, CASIA CMFD                                |
| **Best Accuracy** | **93.6%**                                           |
| **Test Samples**  | **12,615**                                          |

---

## 🏗️ System Architecture

### Pipeline Overview

```text
                         Input Image
                              │
                ┌─────────────┴─────────────┐
                │                           │
                ▼                           ▼
       Global Semantic Branch       Forensic Feature Branch
                │                           │
         MobileNetV2              ┌─────────┼─────────┐
         Feature Extraction       │         │         │
                │                Noise     Edge    Compression
                │               Analysis   Artifacts  Traces
                │                           │
                └─────────────┬─────────────┘
                              │
                              ▼
                  Forensic Attention
                      Transformer
                              │
                              ▼
                     Feature Fusion
                              │
                              ▼
                   Tampering Detection
                              │
                    ┌─────────┴─────────┐
                    ▼                   ▼
                Authentic            Tampered
                                        │
                                        ▼
                              Heatmap Visualization
```

The architecture combines **semantic understanding** and **forensic evidence** rather than relying solely on conventional image classification features.

---

## 🔬 Core Technical Approach

### ① Global Semantic Feature Extraction

A pre-trained **MobileNetV2** backbone is used to extract high-level visual representations from input images.

This branch captures contextual information such as:

* Objects and structures
* Spatial patterns
* Overall image semantics
* High-level visual representations

Transfer learning with MobileNetV2 provides a strong feature representation while reducing the amount of training required from scratch.

---

### ② Forensic Feature Analysis

The second branch focuses on subtle image artifacts that may indicate manipulation.

TamperNet incorporates:

**Noise Inconsistencies**

Analyzes differences in noise characteristics that may occur between authentic and manipulated portions of an image.

**Edge Artifacts**

Examines irregularities around object boundaries and manipulated regions that may result from editing operations.

**Compression Traces**

Uses compression-related inconsistencies as additional forensic evidence for detecting manipulated content.

These signals complement the semantic information extracted by the MobileNetV2 branch.

---

### ③ Forensic Attention Transformer

The **Forensic Attention Transformer** is used to integrate the semantic and forensic representations.

The attention mechanism allows the model to emphasize **informative forensic features** while combining them with global image representations.

This produces a richer representation for the final tampering classification stage.

---

### ④ Tampering Detection & Visualization

The fused representation is passed through the classification pipeline to determine whether an image is:

* **Authentic**
* **Tampered**

The system also supports **heatmap-based visualization** to provide an interpretable indication of regions potentially associated with manipulation.

---

# 👥 Team Collaboration

TamperNet was developed by a **two-person team**, with responsibilities divided across model development, data preparation, experimentation, evaluation, and system integration.

We worked collaboratively rather than developing isolated components. The project followed an iterative workflow:

```text
Dataset Preparation
        ↓
Preprocessing
        ↓
Feature Engineering
        ↓
Model Development
        ↓
Forensic Feature Integration
        ↓
Training & Experimentation
        ↓
Evaluation
        ↓
Inference & Visualization
        ↓
Final System Integration
```

My primary responsibility was the **core deep learning architecture and forensic analysis pipeline**, while the other team member contributed to complementary project components and experimentation.

We continuously integrated our work into the same training and inference pipeline, evaluated results together, and refined the system based on model performance.

---

# 👩‍💻 My Individual Contribution

As one of the two developers, I was responsible for designing and implementing the **core detection architecture and integrating the forensic analysis components into the end-to-end system**.

### 🧠 Model Architecture

* Designed and implemented the **Dual Branch CNN architecture**
* Integrated **MobileNetV2** as the pre-trained feature extraction backbone
* Developed the semantic and forensic feature-processing branches
* Implemented the **Forensic Attention Transformer** for feature integration

### 🔍 Forensic Analysis

Integrated multiple forensic signals into the deep learning pipeline:

* Noise inconsistencies
* Edge artifacts
* Compression traces

These features were incorporated alongside semantic representations to strengthen the model's ability to identify subtle manipulation artifacts.

### ⚙️ Training & Inference Pipeline

Developed the training and inference workflows using **Python and TensorFlow/Keras**, including:

* Image preprocessing
* Pixel normalization
* Image resizing
* Dataset preparation
* Data augmentation
* Model training
* Fine-tuning
* Validation
* Inference and prediction
* Model evaluation

### 📊 Visualization

Developed the workflow for generating **tampering heatmaps**, providing a visual representation of areas potentially associated with manipulation.

### 🔗 Integration With the Team's Work

My model components were integrated with the team's dataset preparation, experimentation, evaluation, and visualization workflows.

This required ensuring that the forensic feature pipeline, MobileNetV2 representations, attention-based feature fusion, training process, and inference outputs worked together as a single end-to-end system.

---

# 📊 Results

The final model achieved:

### **93.6% Accuracy**

on **12,615 test samples**.

The results demonstrated the potential of combining **deep semantic representations with low-level forensic features** for image tampering detection.

The addition of forensic analysis also provided a basis for producing more interpretable outputs through tampering-region visualization.

---

# 📂 Datasets

### CASIA V2

Benchmark dataset containing authentic and manipulated images for image-forensics research.

### CASIA CMFD

Dataset used to evaluate the system on **copy-move forgery detection** scenarios.

Due to dataset size and licensing restrictions, the datasets are not included in this repository.

---

# ⚙️ Preprocessing

The image preprocessing pipeline includes:

* Pixel normalization to `[0,1]`
* Resizing to the required MobileNetV2 input dimensions
* Authentic / Tampered labeling
* Dataset preparation and validation

Recommended augmentation techniques include:

* Random cropping
* Flipping
* Rotation
* Gaussian noise

---

# 🛠️ Technology Stack

| **Category**         | **Technologies**                                             |
| -------------------- | ------------------------------------------------------------ |
| **Programming**      | Python                                                       |
| **Deep Learning**    | TensorFlow, Keras, PyTorch                                   |
| **Architecture**     | Dual Branch CNN, MobileNetV2, Forensic Attention Transformer |
| **Computer Vision**  | OpenCV, scikit-image                                         |
| **Machine Learning** | scikit-learn                                                 |
| **Data Processing**  | NumPy, Pandas                                                |
| **Visualization**    | Matplotlib, Seaborn                                          |

---

# 📁 Repository Contents

```text
TamperNet/
│
├── model/
│   └── Dual Branch CNN implementation
│
├── training/
│   └── Training and fine-tuning scripts
│
├── inference/
│   └── Prediction and inference pipeline
│
├── visualization/
│   └── Tampering heatmap generation
│
├── notebooks/
│   └── Experiments and analysis
│
├── configs/
│   └── Experiment configurations
│
└── README.md
```

---

# 🎯 Project Objective

The objective of TamperNet is to enhance **digital image forensics** by combining deep learning with traditional forensic feature analysis.

Rather than treating tampering detection purely as an image-classification problem, the project explores how **semantic information, low-level image artifacts, and attention-based feature fusion** can work together to produce a more accurate and interpretable detection system.

---

# 🚀 Future Work

* **Multi-region tampering localization**
* **Multi-modal forgery detection**
* **Transformer-based forensic reasoning**
* **Adversarial robustness evaluation**
* Improved forensic explainability
* More precise manipulated-region localization

---

## ⭐ Key Takeaways

**TamperNet demonstrates practical experience in:**

* Designing deep learning architectures
* Transfer learning with MobileNetV2
* Feature engineering for digital forensics
* Transformer-based attention mechanisms
* Computer vision and image processing
* Building end-to-end ML pipelines
* Team-based ML system development
* Model evaluation on large benchmark datasets

**Final Result: 93.6% accuracy on 12,615 test samples**
