# D7047E - Lab 0: Deep Learning Practical

## Overview
This lab covers PyTorch fundamentals, CNN training on CIFAR-10, and transfer learning experiments.

## Files

| File | Description |
|---|---|
| `Lab_0.ipynb` | Main notebook with all experiments and results |
| `cnn_cifar10_tanh.ipynb` | Separate file for the Tanh activation experiment (as required) |
| `requirements.txt` | Python dependencies |

## Experiments & Results

### Task 0.1: Simple CNN on CIFAR-10

| Experiment | Activation | Optimizer | Test Accuracy |
|---|---|---|---|
| Exp 1 (optional) | LeakyReLU | SGD (lr=0.0001) | 20.87% |
| Exp 2 | LeakyReLU | Adam (lr=0.0001) | 71.88% |
| Exp 3 | Tanh | Adam (lr=0.0001) | 73.65% |

### Task 0.2.1: Transfer Learning - AlexNet on CIFAR-10

| Experiment | Method | Test Accuracy |
|---|---|---|
| Fine-tuning | All layers trainable | 90.37% |
| Feature Extraction (optional) | Only classifier trainable | 82.90% |

### Task 0.2.2: Transfer Learning - MNIST to SVHN

| Experiment | Test Accuracy |
|---|---|
| CNN on MNIST | 99.16% |
| Transfer to SVHN (optional) | 90.34% |

## How to Run

1. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
2. Open `Lab_0.ipynb` in Jupyter Notebook or Google Colab
3. Run all cells (use GPU runtime on Colab for faster training)
4. For TensorBoard visualization:
   ```
   tensorboard --logdir runs/
   ```

## Framework
- **PyTorch** with TorchVision
- **TensorBoard** for visualization
- **Matplotlib** for inline plots