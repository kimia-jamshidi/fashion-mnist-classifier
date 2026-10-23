# Fashion-MNIST Image Classifier

A beginner-level deep-learning project that classifies grayscale clothing images into 10 categories using TensorFlow/Keras and the Fashion-MNIST dataset.

## Overview

This project demonstrates an end-to-end image-classification workflow:
- Load and explore Fashion-MNIST.
- Normalize pixel values.
- Build a feed-forward neural network using `Flatten` and `Dense` layers.
- Train the model and inspect training/validation curves.
- Evaluate performance on a held-out test set.
- Run inference on test samples and optionally on a prepared custom image.

## Dataset

Fashion-MNIST is a dataset of 70,000 grayscale clothing images, each 28×28 pixels:
- 60,000 training examples
- 10,000 test examples
- 10 classes: T-shirt/top, Trouser, Pullover, Dress, Coat, Sandal, Shirt, Sneaker, Bag, and Ankle boot

The dataset is loaded through `tf.keras.datasets.fashion_mnist`. On the first run, TensorFlow/Keras may need an internet connection to download it.

## Model architecture

| Layer | Purpose |
|---|---|
| `Flatten(input_shape=(28, 28))` | Converts each image into a 784-value vector |
| `Dense(128, activation="relu")` | Learns nonlinear features |
| `Dense(10)` | Produces one logit per class |

The model uses the Adam optimizer and sparse categorical cross-entropy with `from_logits=True`.

## Getting started

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd fashion-mnist-classifier
```

Replace `<YOUR_GITHUB_REPOSITORY_URL>` with the URL of your repository.

### 2. Create and activate a virtual environment (recommended)

**Windows (PowerShell):**
```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**macOS/Linux:**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Run the notebook

```bash
jupyter notebook
```

Open `fashion_mnist_classifier.ipynb` and run the cells from top to bottom. The first run may download the dataset.

## Optional custom-image prediction

The notebook includes an optional inference cell. To use it:
1. Create a `data/` directory.
2. Place a prepared 28×28 grayscale image at `data/custom_image.png`.
3. Run the final notebook cell.

The custom image should resemble the Fashion-MNIST image style. Arbitrary photographs may require resizing, contrast adjustment, or background inversion. The notebook does not claim robust performance on real-world photographs.

## Results

The notebook prints the measured test loss and test accuracy after training. Results can vary by TensorFlow version, hardware, and training configuration. Run the notebook to obtain the actual metrics rather than relying on a hard-coded score.

## Limitations and possible improvements

- Baseline dense network; a CNN may perform better for image data.
- Custom-image prediction depends on matching the dataset's input format.
- Potential extensions: confusion matrix, per-class metrics, model checkpointing, saved-model inference, and CNN comparison.

## Technologies

- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- OpenCV (optional custom-image preprocessing)

## Project status

Educational portfolio project. This repository is intended to demonstrate a foundational machine-learning workflow, not a production-ready image-classification service.
