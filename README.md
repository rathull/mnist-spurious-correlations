# MNIST and the Spurious Correlations Problem

In classification tasks, classes often consist of smaller subclasses, leading to hidden stratification. Among these finer-grained subclasses, classification models may underperform within these, since models trained only on coarser-grained class labels only prioritize performance between classes. To mitigate the effects of this hidden stratificatio, we want to minimize the maximum loss over all of these finer-grained subclasses to ensure that our model generalizes well.

Although these subclasses are often unlabeled, this notebook (based on the paper linked below), demonstrates a model to mesaure and mitigate hidden stratification by estimating subclass labels by clustetring the feature space of a standard neural network. This notebook uses the [SpuCo package](https://spuco.readthedocs.io/en/latest/) and remedies spurious correlations in the SpuCoMNIST dataset provided.  The model follows three steps:
1. Train a model using Empirical Risk Minimization
2. Cluster inputs based on the feature space produced for ERM
3. Retrain using group balanced batch ERM with the estimated labels from clustering

Based on "No Subclass Left Behind: Fine-Grained Robustness in Coarse-Grained Classification Problems" (paper linked [here](https://arxiv.org/pdf/2011.12945.pdf))
