# Hybrid Transformer-Attention U-Net++ for Medical Image Segmentation

This repository implements a novel hybrid deep learning architecture for medical image segmentation, evaluated on the ISIC 2018 skin lesion segmentation dataset. The model extends the classical U-Net framework by integrating Transformer-based self-attention, convolutional self-attention, and frequency-domain attention to improve both global and local feature representation.

## Model Architecture

The proposed TransAttU-Net++ architecture consists of:
- A U-Net encoder–decoder backbone for precise spatial localization
- Transformer Self-Attention (TSA) blocks to capture long-range dependencies
- Convolutional Self-Attention (CSA) blocks for enhanced local context modeling
- FFT-based Adaptive Channel and Domain Attention (ACDA) for spatial–frequency feature fusion
- Multi-scale skip connections with residual and dense pathways to strengthen contextual learning and gradient flow

## Dataset

- ISIC 2018 Challenge – Task 1 (Skin Lesion Segmentation)
- The dataset is automatically downloaded using kagglehub
- RGB dermoscopic images with corresponding binary segmentation masks

## Training Configuration

- Framework: PyTorch
- Input size: 64 × 64
- Epochs: 150
- Batch size: 8 (GPU) / 4 (CPU fallback)
- Optimizer: Adam
- Learning rate: 2e-4
- Weight decay: 1e-4
- Loss function: BCE + Dice (weighted combination)
- Learning rate scheduler: Cosine Annealing with Warm Restarts
- Gradient clipping: Enabled
- Mixed precision: Optional

## Performance

The model achieves the following results on the ISIC 2018 dataset:
- Dice Coefficient: 88.14%
- Segmentation Accuracy: 95.32%

These results outperform standard U-Net baselines.

## License

This project is intended for academic and research purposes. Please cite appropriately if used in published work.
