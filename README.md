# Machine Learning II: Automated Planning for a Warehouse and CNN + Boosting Classification

Two independent exercises for the MSc in Artificial Intelligence (UTAMED). They are set in a fictional logistics company called *AutoLogistics*.

| Part | Topic | Notebook |
|---|---|---|
| 1 | Classical AI planning: BFS vs A* for a warehouse robot | `parte1_planificacion_almacen.ipynb` |
| 2 | Image classification: CNN embeddings + XGBoost / LightGBM | `parte2_colab.ipynb` |

## Part 1: Automated planning for an autonomous warehouse

**Problem.** A robot must move a heavy box from Zone A to Zone C. The box needs a hand truck, the truck is parked in the storage room, and Zone C is blocked. The robot has to find a coherent sequence of actions on its own.

**Modelling.** The domain is formulated in the STRIPS / PDDL style and implemented in plain Python:
- **State**: robot position, box position, truck position, whether the robot holds the truck, what it is carrying, and whether Zone C is blocked.
- **Actions** (5): move between adjacent zones, pick up the truck, load the box, clear Zone C, and unload the box. Each action has preconditions and effects.
- **Map**: storage room ↔ A ↔ B ↔ C.

**Planners.**
- **Breadth-first search (BFS)**: complete and optimal in number of actions.
- **A\*** with a hand-written admissible heuristic that counts the pending sub-goals (get the truck, load the box, clear C, reach C).

**Result.** The optimal plan has **8 actions**: go to the storage room, take the truck, return to A, load the box, move to B, clear Zone C, move to C and unload. The notebook compares both planners on time, nodes expanded and plan length. It also discusses what happens when the goal is inverted or a different zone is blocked.

## Part 2: CNN + boosting for fruit classification

**Data.** [Fruits-360](https://www.kaggle.com/datasets/moltean/fruits) (Kaggle), restricted to three classes: Apple, Banana and Avocado. Images are resized to 128×128.

**Pipeline.**
1. **CNN** (Keras): three `Conv2D` blocks with batch normalisation and dropout, trained with data augmentation (rotation, shifts, flips) and early stopping.
2. **Embeddings**: the penultimate dense layer of the CNN is used as a 128-dimensional feature extractor.
3. **Hand-crafted features** (OpenCV): brightness mean and std, Sobel edge mean and std, and Canny edge density.
4. **Boosting**: embeddings and hand-crafted features are concatenated and scaled, then used to train **XGBoost** and **LightGBM**.
5. **Comparison**: the three models are compared on accuracy, precision, recall and F1.

The notebook closes with a discussion of the trade-offs between an end-to-end CNN and boosting on top of learned features: accuracy, interpretability, training cost and data requirements.

## Repository contents

```
├── parte1_planificacion_almacen.ipynb   # Part 1: planning (BFS, A*)
└── parte2_colab.ipynb                   # Part 2: CNN + XGBoost / LightGBM (Google Colab)
```

> The notebooks are saved without execution outputs. Part 2 is designed for Google Colab and downloads the dataset with the Kaggle API, so it needs a `kaggle.json` token. Comments are in Spanish.

## Tech stack

Python · `collections.deque` / `heapq` (search) · TensorFlow / Keras · OpenCV · XGBoost · LightGBM · scikit-learn · pandas · Google Colab

## Author

**Víctor Ferrer**, MSc in Artificial Intelligence, UTAMED
