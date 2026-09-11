# 🛡️ TamperNet — Image Tampering Detection Using Deep Learning

**Deep Learning–Based Digital Image Forensics & Manipulation Detection System**

*Dual Branch CNN • MobileNetV2 • Forensic Attention Transformer • Computer Vision • Digital Forensics*

---

### 🚀 Automated Image Tampering Detection & Forensic Analysis

TamperNet is a **deep learning-based digital image forensics system** designed to detect manipulated images by combining **high-level semantic information with low-level forensic evidence**.

The system uses a **Dual Branch CNN architecture** to analyze images through complementary semantic and forensic pathways, followed by a **Forensic Attention Transformer** for feature fusion and tampering classification.

**93.6% accuracy across 12,615 test samples**

[Architecture](#-architecture) • [My Contribution](#-my-individual-contribution) • [Technical Approach](#-technical-approach) • [Results](#-results) • [Datasets](#-datasets) • [Technology Stack](#-technology-stack) • [Future Work](#-future-work)

---

## 🎯 What It Does

TamperNet analyzes digital images for signs of manipulation by combining **semantic image understanding** with **forensic artifact analysis**.

The system processes images through two complementary branches:

* 🧠 **Global Semantic Branch** — extracts high-level visual and contextual features using a pre-trained **MobileNetV2** backbone.
* 🔍 **Forensic Feature Branch** — analyzes manipulation-related evidence including **noise inconsistencies, edge artifacts, and compression traces**.

The extracted representations are then combined using a **Forensic Attention Transformer**, enabling the system to focus on informative forensic signals before producing the final prediction.

### Detection Output

The system classifies an image as:

* ✅ **Authentic**
* ⚠️ **Tampered**

For manipulated images, the system also supports **heatmap visualization** to highlight regions potentially associated with tampering.

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

# 🏗️ Architecture

### Pipeline Overview

```text
                           Input Image
                                │
                 ┌──────────────┴──────────────┐
                 │                             │
                 ▼                             ▼
       Global Semantic Branch        Forensic Feature Branch
                 │                             │
          MobileNetV2                ┌─────────┼─────────┐
       Feature Extraction            │         │         │
                 │                  Noise     Edge    Compression
                 │                Analysis   Artifacts   Traces
                 │                             │
                 └──────────────┬──────────────┘
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
                    ┌───────────┴───────────┐
                    ▼                       ▼
                Authentic                Tampered
                                            │
                                            ▼
                                   Heatmap Visualization
```

The architecture combines **semantic understanding and forensic evidence** rather than relying solely on conventional image classification features.

---

# 🔬 Technical Approach

## ① Global Semantic Feature Extraction

A pre-trained **MobileNetV2** backbone is used to extract high-level visual representations from input images.

This branch captures:

* Objects and structures
* Spatial patterns
* Overall image semantics
* High-level visual representations

Transfer learning allows the system to leverage an established feature representation while reducing the amount of training required from scratch.

---

## ② Forensic Feature Analysis

The second branch focuses on subtle image artifacts that can provide evidence of manipulation.

### Noise Inconsistencies

Analyzes differences in noise characteristics that may occur between authentic and manipulated regions.

### Edge Artifacts

Examines irregularities around object boundaries and manipulated regions that can result from image editing operations.

### Compression Traces

Uses compression-related inconsistencies as additional forensic evidence for detecting manipulated content.

These forensic signals complement the semantic representations generated by the MobileNetV2 branch.

---

## ③ Forensic Attention Transformer

The **Forensic Attention Transformer** integrates the semantic and forensic representations.

Its attention mechanism enables the model to emphasize **informative forensic features** while combining them with global image representations.

This produces a richer feature representation for the final tampering classification stage.

---

## ④ Tampering Detection & Visualization

The fused representation is passed through the classification pipeline to determine whether the image is:

* **Authentic**
* **Tampered**

The system also supports **heatmap-based visualization**, providing an interpretable indication of regions potentially associated with manipulation.

---

# 👩‍💻 My Individual Contribution

As one of the two developers, I was responsible for designing and implementing the **core deep learning architecture and integrating the forensic analysis components into the end-to-end detection pipeline**.

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

Developed the workflow for generating **tampering heatmaps**, providing a visual representation of areas potentially associated with image manipulation.

### 🔗 System Integration

Integrated the model components with the team's dataset preparation, experimentation, evaluation, and visualization workflows.

This required ensuring that the **forensic feature pipeline, MobileNetV2 representations, attention-based feature fusion, training process, and inference outputs** operated together as a unified end-to-end system.

---

# 👥 Team Collaboration

TamperNet was developed by a **two-person team**, with responsibilities distributed across model development, data preparation, experimentation, evaluation, and system integration.

Our development workflow followed an iterative process:

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

My primary responsibility focused on the **core deep learning architecture and forensic analysis pipeline**, while the other team member contributed to complementary project components and experimentation.

We continuously integrated our work into the same training and inference pipeline, evaluated results together, and refined the system based on model performance.

---

# 📊 Results

### 🏆 93.6% Accuracy

The final model achieved:

**93.6% accuracy on 12,615 test samples.**

The results demonstrate the potential of combining **deep semantic representations with low-level forensic features** for image tampering detection.

The forensic analysis pipeline also provides a foundation for more interpretable outputs through tampering-region visualization.

---

# 📂 Datasets

## CASIA V2

Benchmark dataset containing authentic and manipulated images for image-forensics research.

## CASIA CMFD

Dataset used to evaluate the system on **copy-move forgery detection** scenarios.

Due to dataset size and licensing restrictions, the datasets are **not included in this repository**.

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

# 🎯 Project Objective

The objective of TamperNet is to enhance **digital image forensics** by combining deep learning with traditional forensic feature analysis.

Rather than treating tampering detection purely as an image-classification problem, the project explores how **semantic information, low-level image artifacts, and attention-based feature fusion** can work together to produce a more accurate and interpretable detection system.

---

# 🚀 Future Work

* Multi-region tampering localization
* Multi-modal forgery detection
* Transformer-based forensic reasoning
* Adversarial robustness evaluation
* Improved forensic explainability
* More precise manipulated-region localization

---

# ⭐ Key Takeaways

TamperNet demonstrates practical experience in:

* 🧠 Designing deep learning architectures
* 🔄 Transfer learning with MobileNetV2
* 🔍 Feature engineering for digital forensics
* 🤖 Transformer-based attention mechanisms
* 👁️ Computer vision and image processing
* ⚙️ Building end-to-end ML pipelines
* 👥 Collaborative ML system development
* 📊 Model evaluation on benchmark datasets

### Final Result

**93.6% accuracy on 12,615 test samples**

TamperNet demonstrates how **deep learning, computer vision, and digital forensic analysis** can be combined to build an interpretable image tampering detection system.
