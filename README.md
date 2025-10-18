# Distributed Training for Digits dataset using Ray with different optimizers for Hyperparameter Tuning (MLOps Lab 3)

## Objective

Understand grid search mechanics on a classification problem by comparing different optimizers (SGD, Adam, RMSprop) with various hyperparameters using Ray Tune for distributed hyperparameter optimization.

## Problem Statement

Train a neural network on the **Digits Dataset** (handwritten digit classification) and systematically explore:
- **3 Optimizers:** SGD, Adam, RMSprop
- **4 Learning Rates:** 0.0001, 0.0005, 0.001, 0.005
- **3 Momentum Values:** 0.0, 0.5, 0.9 (for SGD only)

**Challenge:** Different optimizers have different hyperparameters - SGD uses momentum while Adam/RMSprop don't.

## Dataset: Digits (8x8 Images)

- **Samples:** 1,797 handwritten digits (0-9)
- **Features:** 64 (8×8 grayscale pixels)
- **Classes:** 10 (balanced distribution)
- **Split:** 80% train (1,437), 20% test (360)

## Key Findings

### Performance Results

| Optimizer | Best Accuracy | Average Accuracy | Std Dev |
|-----------|---------------|------------------|---------|
| **RMSprop** | **98.61%** | 97.99% | 0.92% |
| **Adam** | 97.78% | 97.29% | **0.62%** |
| **SGD** | 98.06% | 76.23% | 25.47% |

## Ray Grid Search vs Sequential Training

### Advantages of Ray Tune

| Aspect | Sequential | Ray Grid Search |
|--------|-----------|-----------------|
| **Time** | 20 trials × 45s = 15 min | ~15-20 min (parallel) |
| **Exploration** | Manual, limited | Systematic, exhaustive |
| **Tracking** | Manual logging | Automatic metrics |
| **Reproducibility** | Difficult | Built-in |
| **Resource Usage** | Inefficient | Parallel CPU/GPU |
| **Insights** | Single point | Statistical analysis |

### Grid Search Benefits

1. **Parallelization:** Run multiple trials simultaneously across CPU cores
2. **Automatic tracking:** All metrics saved automatically with timestamps
3. **Systematic exploration:** No missed configurations, eliminates human bias
4. **Statistical robustness:** Mean, std, min, max across multiple runs
5. **Handling different hyperparameters:** Elegant solution for momentum (SGD-only parameter)

**Author:** [Your Name]  
**Date:** October 2025  
**Course:** [Your Course]
