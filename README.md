# CodingBackProp

A C# console application that trains a neural network with back-propagation, based on the article *Coding Neural Network Back-Propagation Using C#*. The project also adds two modifications from the article's "What To Do" section: **cross-entropy error** and **weight decay (regularization)**.

## Modification

All settings are at the top of `Main`:

```csharp
bool useCrossEntropy = false; // Set this to true to use Cross Entropy
bool useWeightDecay = false; // Set this to true to use Weight Decay
double lambda = 0.0001;
```

| Run | `useCrossEntropy` | `useWeightDecay` |
|---|---|---|
| Baseline (squared error) | false | false |
| Cross entropy | true | false |
| Weight decay | false | true |
| Both | true | true |

## Result

| Run | Final error (epoch 900) | Train accuracy | Test accuracy | Largest weight or bias magnitude |
|---|---|---|---|---|
| Baseline | 0.0176 | 0.9900 | 0.9800 | 7.77 |
| Cross entropy | 0.0895 | 0.9675 | 0.9550 | 20.38 |
| Weight decay only (`lambda = 0.0001`) | 0.0217 | 0.9888 | 0.9800 | 6.45 |
| Both (`lambda = 0.0001`) | 0.1882 | 0.9675 | 0.9650 | 13.63 |
