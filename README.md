# D7047E - Lab 0: Deep Learning Practical

## Overview
This lab covers PyTorch fundamentals, CNN training on CIFAR-10, and transfer learning experiments.

## Files

| File | Description |
|---|---|
| `Lab_0.ipynb` | Main notebook with all experiments and results |
| `requirements.txt` | Python dependencies |

## Key Implementation Details

- **Train/Validation/Test Split**: CIFAR-10 training set (50,000) is split into train (40,000) and validation (10,000). The test set (10,000) is kept separate for final evaluation.
- **Best Model Selection**: `run_experiment` tracks the lowest validation loss and restores the best model using `copy.deepcopy`.
- **Learning Rate Scheduler**: StepLR (drops LR by 10x every 40 epochs) is used for SGD to ensure convergence.
- **Convergence**: All models are trained until validation loss plateaus, verified by the best epoch being well before the final epoch.

## Experiments & Results

### Task 0.1: Simple CNN on CIFAR-10

| Experiment | Activation | Optimizer | LR | Epochs | Best Epoch | Test Accuracy |
|---|---|---|---|---|---|---|
| Exp 1 | LeakyReLU | SGD (momentum=0.9) + StepLR | 0.01 | 120 | 85 | 85.96% |
| Exp 2 | LeakyReLU | Adam | 0.001 | 80 | 75 | 85.78% |
| Exp 3 | Tanh | Adam | 0.001 | 160 | 147 | 81.69% |

### Task 0.2.1: Transfer Learning - AlexNet on CIFAR-10

| Experiment | Method | Epochs | Best Epoch | Test Accuracy |
|---|---|---|---|---|
| Fine-tuning | All layers trainable | 10 | 5 | 90.23% |
| Feature Extraction | Only classifier trainable | 40 | 34 | 83.74% |

### Task 0.2.2: Transfer Learning - MNIST to SVHN

| Experiment | Epochs | Best Epoch | Test Accuracy |
|---|---|---|---|
| CNN on MNIST | 20 | 6 | 99.08% |
| Transfer to SVHN | 20 | 3 | 90.51% |

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
