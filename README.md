# AIGC-PanoIQA

<div align="center">

<h3>AIGC-PanoIQA: A Comprehensive Benchmark and Decoupled Multi-modal Fusion Network for AI-Generated Panorama Quality Assessment</h3>

[![Paper](https://img.shields.io/badge/Paper-To_be_published-blue.svg)](#)
[![Dataset](https://img.shields.io/badge/Dataset-AIGC--PanoIQA-green.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

*Official PyTorch Implementation & Dataset Repository*

</div>

---

## 📢 News
- **[2026.03]** The AIGC-PanoIQA dataset and the official implementation code have been released! 
- **[2026.03]** The paper is currently under review.

## 📖 Introduction
This repository contains the official implementation of the **AIGC-PanoIQA** framework and the corresponding large-scale benchmark dataset. We introduce a novel pipeline specifically designed to evaluate the objective quality of AI-generated panoramas across three critical dimensions: **Visual Quality (Perception)**, **Comfortability**, and **Consistency**.

### 🌟 Key Features
- **Large-Scale Benchmark**: The first comprehensive dataset comprising **1,440 AIGC panorama pairs** generated via Stable Diffusion, alongside tens of thousands of extracted viewports.
- **Immersive VR MOS Collection**: Subjective Mean Opinion Scores (MOS) were rigorously collected using a custom-developed VR IQA application built on **Unity**, ensuring genuine immersive evaluation.
- **Tri-Pathway Decoupled Fusion Network**: 
  - Employs a **"1 Global + 6 Local"** viewport splitting strategy combined with Saliency Guidance to capture fine-grained spatial distortions.
  - Aligns image and text into a high-dimensional semantic space via **CLIP**.
  - Utilizes **Self-Attention** to aggregate global visual structures among viewports, and **Cross-Attention** to deeply interact with text-image semantics and reference fidelity.
- **State-of-the-Art Performance**: Achieves leading PLCC/SROCC metrics across multiple scenarios.

---

## 📊 The AIGC-PanoIQA Dataset

Our dataset is the foundation of this work, providing rich, multi-dimensional annotations for omnidirectional generative content.

- **Size**: 1,440 panorama pairs & 10,000+ viewport patches.
- **Generator**: Advanced AIGC models (e.g., Stable Diffusion).
- **Subjective Study**: Conducted via our custom **Unity VR App** in head-mounted displays to capture authentic user experience (Visual Quality, Comfortability, Consistency).

> **[Download the Dataset Here]** *(Link to be added - e.g., Google Drive / Baidu Netdisk / HuggingFace)*

---

## 🚀 Model Architecture

*(You can add an architecture diagram image here by replacing the path)*
The proposed model relies on an image-centric decoupled architecture:
1. **Viewport Extraction & Saliency**: Extracts 1 global and 6 local viewports, weighted by visual saliency.
2. **Feature Extraction**: Leverages CLIP for robust cross-modal alignment.
3. **Decoupled Fusion**:
   - *Vision-to-Vision (Self-Attention)*
   - *Image-to-Text (Cross-Attention)*
   - *Image-to-Reference (Cross-Attention)*

---

## 💻 Installation

```bash
# Clone the repository
git clone [https://github.com/shuaibilx/AIGC-PanoIQA.git](https://github.com/shuaibilx/AIGC-PanoIQA.git)
cd AIGC-PanoIQA

# Create a conda environment
conda create -n pano_iqa python=3.9 -y
conda activate pano_iqa

# Install dependencies
pip install -r requirements.txt
