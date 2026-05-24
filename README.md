# driveLM_nuscene

A Jupyter-notebook-based pipeline for fine-tuning and evaluating a Vision-Language Model (VLM) on the **DriveLM-nuScenes** dataset — enabling graph-structured visual question answering for end-to-end autonomous driving.

---

## Overview

This project implements the full ML lifecycle — data preparation, exploratory analysis, training, inference, and evaluation — using the [DriveLM](https://github.com/OpenDriveLab/DriveLM) framework on top of the [nuScenes](https://www.nuscenes.org/) multimodal driving dataset.

---

## Repository Structure

```
driveLM_nuscene/
├── data_preparation.ipynb   # parse and format DriveLM-nuScenes data --> Only front camera image included; can be updated to include others
├── Data_analysis.ipynb      # Exploratory data analysis and dataset statistics
├── Training.ipynb           # Fine-tune a VLM (QwenVL) on the prepared data
├── Inference.ipynb          # Run inference and generate predictions
├── evaluation.ipynb         # Compute BLUE/BertF1 Score predictions against ground truth
└── README.md
```

---

## Notebooks

### 1. `data_preparation.ipynb`
Loads the nuScenes dataset and the DriveLM annotations. Parses scene-level descriptions and frame-level QA pairs, and formats everything into a training-ready structure compatible with the chosen VLM.

### 2. `Data_analysis.ipynb`
Explores the prepared dataset — question/answer distributions,  understanding question answer types and gaps in the dataset.

### 3. `Training.ipynb`
Fine-tunes a VLM (QwenVL) on the DriveLM-nuScenes dataset. 

### 4. `Inference.ipynb`
Loads a trained checkpoint and runs predictions on user inputs.

### 5. `evaluation.ipynb`
Evaluates model outputs using standard DriveLM metrics — language similarity (BertF1, BLEU), accuracy on classification-type questions.

---

## Dataset


Download links:
- [nuScenes dataset](https://www.nuscenes.org/nuscenes#download) (mini set used here)
- [DriveLM annotations](https://github.com/OpenDriveLab/DriveLM#data)

---

## Getting Started

### Prerequisites
Required installations are mentioned above each collab notebook. 

### Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/nsreeprem/driveLM_nuscene.git
   cd driveLM_nuscene
   ```

2. Download the nuScenes mini or full dataset and place it under `data/nuscenes/`.

3. Download the DriveLM-nuScenes annotation file and place it under `data/drivelm/`.

4. Run the notebooks in order:
   ```
   data_preparation.ipynb → Data_analysis.ipynb → evaluation.ipynb → Training.ipynb → evaluation.ipynb → Inference.ipynb 
   ```

---


This project is intended for research and educational use. Please refer to the respective licenses of nuScenes and DriveLM before using their data in your work.
