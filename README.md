# Multi-Layer Perceptrons (MLPs) for Pima Diabetes and Iris Classification using Keras

This project demonstrates the use of Multi-Layer Perceptrons (MLPs) built with Keras to perform classification tasks on two datasets:

1. **Pima Indians Diabetes Dataset** (binary classification)
2. **Iris Dataset** (multi-class classification)

The project explores both baseline and redesigned MLP architectures, compares performance, and analyzes generalization capabilities.

---

## Dataset 1: Pima Indians Diabetes Dataset

### Model 1: Baseline MLP

**Architecture**
- Input Layer: 8 features
- Hidden Layers:
  - Dense(16), ReLU
  - Dense(8), ReLU
- Output Layer: Dense(1), Sigmoid

**Compilation & Training**
- Optimizer: Adam
- Loss Function: Binary Crossentropy
- Evaluation: Accuracy, Cross-validation

**Results**
- Training Accuracy: 81.12%
- Validation Accuracy: 75.88%
- Cross-Validation Score (10-fold): 0.7422
- Training Loss: 0.4618
- Validation Loss: 0.7128

---

### Model 2: Redesigned MLP

**Architecture**
- Input Layer: 8 features
- Hidden Layers:
  - Dense(32), ReLU
  - Dense(16), ReLU
- Output Layer: Dense(1), Sigmoid

**Results**
- Training Accuracy: 85.03%
- Validation Accuracy: 85.03%
- Cross-Validation Score (10-fold): 0.6849
- Training Loss: 0.3962
- Validation Loss: 0.3962

**Insights**
- The redesigned model demonstrated better accuracy and lower loss.
- However, lower cross-validation suggests some instability across different subsets of the data.

---

## Dataset 2: Iris Dataset

### Model 1: Baseline MLP

**Architecture**
- Input Layer: 4 features
- Hidden Layer: Dense(8), ReLU
- Output Layer: Dense(3), Softmax

**Compilation & Training**
- Optimizer: Adam
- Loss Function: Categorical Crossentropy

**Results**
- Training Accuracy: ~100%
- Validation Accuracy: ~100%
- Test Accuracy: 94.12%
- Test Loss: 0.2683

---

### Model 2: Redesigned MLP

**Architecture**
- Input Layer: 4 features
- Hidden Layers:
  - Dense(8), ReLU
  - Dense(8), ReLU
- Output Layer: Dense(3), Softmax

**Results**
- Training Accuracy: ~100%
- Validation Accuracy: ~100%
- Test Accuracy: 100%
- Test Loss: 0.1197

**Insights**
- Adding an extra hidden layer improved test accuracy from 94.12% to 100%.
- Test loss significantly dropped, indicating better performance and generalization.

---

## Comparative Summary

| Dataset | Model         | Accuracy | Test Loss | Hidden Layers |
|---------|---------------|----------|-----------|----------------|
| Pima    | Baseline MLP  | 75.88%   | 0.7128    | 2 (16, 8)       |
| Pima    | Redesigned MLP| 85.03%   | 0.3962    | 2 (32, 16)      |
| Iris    | Baseline MLP  | 94.12%   | 0.2683    | 1 (8)           |
| Iris    | Redesigned MLP| 100%     | 0.1197    | 2 (8, 8)        |

**Observations**
- The Iris dataset is simpler, allowing MLPs to reach near-perfect performance even with fewer layers.
- The Pima dataset is more complex and benefits from deeper models, though cross-validation scores suggest potential overfitting risks.
- Adding layers improves accuracy and reduces loss, but model complexity must be balanced with the size and difficulty of the dataset.

---

## Tools Used

- Python 3.x
- Keras with TensorFlow backend
- Scikit-learn
- NumPy, Matplotlib

---

## Conclusion

This project illustrates how model architecture impacts performance in neural networks. Simpler datasets may not require complex models, while more intricate datasets benefit from deeper architectures and regularization. Proper evaluation using validation and cross-validation is critical to ensure reliable generalization.
