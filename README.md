# Few-Shot Object Detection on Pascal VOC Dataset

## 🎯 Overview

This project implements a few-shot object detection system using the Pascal VOC 2012 dataset. The solution employs a two-stage training approach with Faster R-CNN architecture and cosine similarity-based classification to achieve effective object detection with limited training samples (K=3 per class).

## 🚀 Features

- **Two-Stage Training**: Base training + Few-shot fine-tuning
- **Cosine Similarity Classifier**: Better performance for few-shot scenarios
- **Comprehensive Visualization**: Ground truth vs predictions comparison
- **Efficient Implementation**: Optimized for limited computational resources
- **Detailed Analysis**: Performance metrics and pattern analysis

## 📋 Requirements

```bash
torch>=1.9.0
torchvision>=0.10.0
albumentations>=1.0.0
opencv-python>=4.5.0
matplotlib>=3.3.0
numpy>=1.21.0
kagglehub
lxml
```

## 📊 Dataset

The project uses the **Pascal VOC 2012** dataset:
- **20 object classes**: aeroplane, bicycle, bird, boat, bottle, bus, car, cat, chair, cow, diningtable, dog, horse, motorbike, person, pottedplant, sheep, sofa, train, tvmonitor
- **Few-shot setup**: K=3 samples per class
- **Input size**: 400x400 pixels

## 🏗️ Architecture

```
Faster R-CNN Architecture:
├── Backbone: ResNet-18 (Pre-trained)
├── RPN: Region Proposal Network  
├── ROI Pooler: Multi-Scale ROI Align
└── Classifier: Cosine Similarity Classifier
```

## 🔧 Training Configuration

### Stage 1: Base Training
- **Epochs**: 15
- **Batch Size**: 4
- **Learning Rate**: 0.02
- **Optimizer**: SGD (momentum=0.9)

### Stage 2: Few-Shot Fine-tuning
- **Epochs**: 5
- **Batch Size**: 4
- **Learning Rate**: 0.025
- **Frozen**: Backbone + RPN

## 📈 Results

### Training Progress
```
Stage 1 - Final Loss: 0.4067
Stage 2 - Final Loss: 0.5567
```


=
