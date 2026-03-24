# Deep Learning Final Project Report

## 1. Introduction & Methodology
This project applies deep learning concepts from the weekly lab sessions to the FashionMNIST dataset. We implement an MLP model from scratch using NumPy and extend it to PyTorch. We compare activation functions, analyze regularization techniques, and optimize training dynamics.

Our approach integrates core PyTorch and NumPy frameworks, fulfilling the requirement to demonstrate code correctness and method diversity across various dimensions.

## 2. Architecture & Forward/Backward Pass (Member 1 & 2)

### NumPy & Manual Backpropagation
We built a NumPy-based MLP structure where forward and backward pass operations are manually implemented using the Chain Rule. Manual derivative calculation helps us understand exactly how gradients flow backward from the loss function to the input layer.

### PyTorch Architecture & Activations
The vanilla NumPy MLP is translated into a 5-layer DeepMLP using torch.nn.Module. We compared Sigmoid vs ReLU activation functions:
- *Vanishing Gradient:* Sigmoid saturates at the extremes. During deep backpropagation, input layers barely receive any gradient updates.
- *ReLU:* Solves this problem because its derivative is 1 for positive inputs, ensuring a healthy gradient flow through the depth of the network.

By achieving a test accuracy of 97.90% with our NumPy-based model, we have demonstrated that our manual gradient computations are highly consistent with PyTorch's automatic differentiation mechanism, which yielded an accuracy of 97.65%.


## 3. Generalization & Regularization (Member 3)
To control model generalization and prevent overfitting, we introduced a multi-layered regularization strategy:
- *L2 Regularization (Weight Decay):* We integrated weight_decay into the SGD optimizer. By penalizing large weights ($\lambda \sum w^2$), we prevented the model from focusing on noise in the training data, effectively closing the "Generalization Gap" observed in our baseline plots.
- *Dropout:* We added nn.Dropout(p=0.5) layers. This forces the network to learn redundant and robust representations by randomly deactivating neurons during each training step.
- *Early Stopping:* Following Algorithm 7.1, we implemented a patience-based system. By monitoring Validation Loss, we automatically halted training and saved the best model state (best_model.pt) before the model could enter the overfitting regime.

## 4. Conceptual Analysis (Regularization)
As part of our exploration into model stability, we address the following key concepts:
- *L2 vs L1:* L2 shrinks weights toward zero but rarely to absolute zero because the gradient decreases as the weight gets smaller. L1 provides "sparsity" by applying a constant pressure that can drive weights to exactly zero.
- *Dropout Sub-networks:* Dropout is equivalent to training an ensemble of $2^n$ subnetworks. During testing, the full network acts as an approximation of the average of all these subnetworks, leading to better generalization.

## 5. Training Dynamics & Optimization (Member 4)
We optimized our deep model by incorporating Batch Normalization and experimenting with Learning Rates and Optimizers (SGD vs Adam).

### 5.1 Batch Normalization & Covariate Shift
Batch Normalization prevents Internal Covariate Shift by normalizing intermediate inputs for each mini-batch (mean 0, variance 1). This stabilization allows for higher learning rates and faster convergence.

### 5.2 Learning Rate & Stability
We confirmed that the Learning Rate is critical for stability. While high rates can cause divergence, Adam's adaptive learning rate provided significantly more stability and faster convergence compared to the fixed-rate updates of standard SGD.

## 6. Conclusion
By combining manual NumPy implementations with advanced PyTorch regularization and optimization techniques, we achieved a robust model for FashionMNIST. The transition from an "overfitting baseline" to a "regularized optimum" was clearly demonstrated through our learning curves and validation metrics.

## 7. Members
- Member 1: Aleyna Sarıkoca
- Member 2: Ecem Sude Reis
- Member 3: Talib Yeşildal
- Member 4: Salih Özgür Seçen