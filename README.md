# 🤖 Pima Diabetes Classification using MLPs in Keras

This project explores the design, evaluation, and optimization of **Multi-Layer Perceptrons (MLPs)** for classifying diabetes using the **Pima Indians Diabetes Dataset**. Built with **Keras**, the project also compares model variations and generalization performance using **cross-validation**.

---

## 📊 Dataset Overview
- Dataset: Pima Indians Diabetes
- Samples: 768
- Features: 8 numeric input features
- Target: Binary classification (Diabetic / Non-Diabetic)

---

## 🧠 Initial MLP Design

### 🏗️ Architecture
- **Input Layer**: 8 neurons (1 per feature)
- **Hidden Layers**:
  - Layer 1: 16 neurons, ReLU activation
  - Layer 2: 8 neurons, ReLU activation
- **Output Layer**: 1 neuron with Sigmoid activation

### 🧪 Evaluation
- **Training Accuracy**: 80%
- **Validation Accuracy**: 75%
- **Cross-Validation**: 10-fold

### 🔍 Observations
- Slight overfitting observed due to a ~5% gap between training and evaluation.
- Possible causes: small dataset, class imbalance, lack of regularization.

---

## 🔁 MLP Comparison: Pima vs Iris

| Dataset       | Eval Accuracy | Notes                                    |
|---------------|---------------|------------------------------------------|
| **Pima**      | 75–80%        | More complex, possibly imbalanced        |
| **Iris**      | **94.12%**    | Simpler, well-separated, 3-class target  |

📌 **Conclusion**: Simpler datasets (Iris) enable better generalization with smaller networks. Pima’s complexity requires better tuning and regularization.

---

## 🔧  Redesigned MLP for Pima

### 🏗️ Architecture Changes
- **First Hidden Layer**: Increased to 32 neurons
- **Second Hidden Layer**: Increased to 16 neurons

### 📊 Evaluation Metrics

| Metric                  | Original MLP | Redesigned MLP |
|-------------------------|--------------|----------------|
| Training Accuracy       | 0.8112       | **0.8503**     |
| Validation Accuracy     | 0.7588       | **0.8503**     |
| Training Loss           | 0.4618       | **0.3962**     |
| Validation Loss         | 0.7128       | **0.3962**     |
| Cross-Validation (10F)  | **0.7422**   | 0.6849         |

### 📌 Insights
- Redesigned model **improved accuracy and reduced loss**, showing better learning.
- However, **lower cross-validation** score suggests inconsistent generalization across data splits.
- Highlights the importance of regularization and hyperparameter tuning.

---

## 🚀 Recommendations
- Add **dropout or L2 regularization** to reduce overfitting
- Explore **data resampling techniques** for class imbalance
- Use **GridSearchCV** for hyperparameter tuning
- Investigate **ensemble methods** to stabilize performance
- Consider **model checkpointing** and **early stopping**

---

## 🛠️ Tools & Libraries
- Python 3.x
- Keras / TensorFlow
- Scikit-learn
- NumPy, Matplotlib

## 📌 Conclusion

This project demonstrates how **MLP architecture design** and **dataset characteristics** impact model performance. While deeper networks can enhance accuracy, **generalization** still depends on balanced data, proper regularization, and careful tuning.

