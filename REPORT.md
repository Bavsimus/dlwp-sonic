# Deep Learning Project: Methodological Depth & Comparative Analysis

This project is developed for the 'Deep Learning' course at Istinye University. The primary focus is on 'Methodological Depth' and the comparative analysis of techniques (Weeks 2, 3, and 4) learned in laboratory sessions.

---

## 1. Methodological Rigor

The performance of Deep Learning models is not merely a matter of hyperparameter tuning. In this project, methodological rigor is emphasized through:
- **Reproducibility:** All experiments are conducted with fixed *seed* values for consistent results.
- **Ablation Studies:** Isolating and observing the effect of each architectural change (e.g., transitioning from ReLU to Tanh or adding Batch Normalization).
- **Gradient Flow Analysis:** Understanding how vanishing or exploding gradients during backpropagation influence architectural decisions.

---

## 2. Methodologies

### 2.1 MLP Architecture
- Number of layers designed: [X]
- Hidden units: [Y]
- Impact of Fully Connected layers on data representation.

### 2.2 Activation Functions: ReLU, Sigmoid, Tanh
- **ReLU:** Prevents gradient saturation and accelerates training by being linear in the positive domain.
- **Sigmoid & Tanh:** Comparative analysis of training dynamics, focusing on the [0, 1] range of Sigmoid vs. the zero-centered [-1, 1] range of Tanh.

---

## 3. Regularization Experiments

Techniques used to prevent overfitting in our experiments:
- **L1 & L2 (Weight Decay):** Comparing L2's tendency to keep all weights small vs. L1's tendency to create sparsity by penalizing the absolute values of weights.
- **Dropout:** Reducing reliance on specific neurons and improving generalization by randomly "dropping" nodes during training.

---

## 4. Optimization & Training

### 4.1 Batch Normalization
- **Internal Covariate Shift:** Stabilizing and accelerating training by normalizing the input distributions of each layer.

### 4.2 Early Stopping
- Minimizing generalization error by terminating training when validation loss begins to increase.

---

## 5. Hyperparameter Decisions

| Hyperparameter | Value | Rational |
| :--- | :--- | :--- |
| Learning Rate | [e.g., 0.001] | Stability of gradient descent... |
| Batch Size | [e.g., 64] | Balance between memory efficiency and gradient noise... |
| Epochs | [e.g., 50] | Managed via Early Stopping... |

---

## 6. Comparison Table

| Scenario | Test Accuracy | Test Loss | Observations |
| :--- | :---: | :---: | :--- |
| Baseline (ReLU, No Reg) | % XX.X | X.XX | Overfitting observed. |
| Dropout + L2 | % XX.X | X.XX | Improved generalization achieved. |
| Batch Norm + ReLU | % XX.X | X.XX | Fastest convergence observed. |

---

## 7. Conclusion
The experiments conducted throughout the project demonstrate that...
