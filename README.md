# GenX-FuseNet: Alzheimer's Disease Classification from MRI

## Title
GenX-FuseNet: Multimodal-inspired fusion network for multi-class Alzheimer stage classification

## Description
This repository contains the implementation of GenX-FuseNet, a deep learning framework for multi-class Alzheimer's disease classification using structural MRI images. The model generates PET-like features and performs cross-modal fusion for enhanced classification accuracy.

## Dataset Information
- **Source:** Open Access Series of Imaging Studies (OASIS)
- **URL:** https://sites.wustl.edu/oasisbrains/
- **Classes:** Non Demented, Very Mild Dementia, Mild Dementia, Moderate Dementia
- **Preprocessing:** Images resized to 224×224, affine registration for alignment, patient-level stratification

## Code Information
- **Framework:** TensorFlow 2.x with Keras API
- **Backbone:** EfficientNetB0 (ImageNet-pretrained, frozen)
- **Key Components:** 
  - PET-like feature generator
  - Cross-modal attention fusion
  - Transformer-based contextual fusion

## Usage Instructions
1. Clone repository
2. Install dependencies: `pip install -r requirements.txt`
3. Download OASIS dataset from https://sites.wustl.edu/oasisbrains/
4. Run preprocessing: `python preprocess.py --data_dir /path/to/data`
5. Train model: `python train.py --config config.yaml`
6. Evaluate: `python evaluate.py --checkpoint best_model.h5`
7. Generate explanations: `python explain.py --input sample_mri.nii`

## Requirements
- Python 3.9+
- TensorFlow 2.13+
- CUDA-capable GPU (optional)
- NumPy, scikit-learn, matplotlib
- nibabel (for NIfTI processing)

## Methodology
1. MRI feature extraction using EfficientNetB0
2. PET-like feature generation using convolutional generator
3. Cross-modal feature fusion with attention mechanism
4. Classification with softmax output layer
5. Explainability via Grad-CAM and LIME

## Citations
If using this code, please cite:
Sharma, N.K., Koganti, C. GenX-FuseNet: A multimodal-inspired fusion network with generative PET-like features for multi-class Alzheimer stage classification with explainable AI. PeerJ Computer Science (2026).

## License
MIT License
