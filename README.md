# Flower Classification

A TensorFlow/Keras image-classification project that trains a convolutional neural network (CNN) to identify five flower classes:

- Lilly
- Lotus
- Orchid
- Sunflower
- Tulip

The complete workflow—data loading, training, prediction, and a Gradio interface—is in [main.ipynb](main.ipynb).

## Dataset

The dataset is stored in `flower_images/`, with one folder per class. The notebook uses an 80/20 training-validation split and trains on 4,000 images with 1,000 validation images.

## Model

The notebook builds a CNN with four convolution/max-pooling blocks, a 512-unit dense layer, and a five-class softmax output. Training is configured for 15 epochs with the Adam optimizer and categorical cross-entropy loss.

The recorded run reached approximately **79.1% validation accuracy** after 15 epochs.

## Getting started

1. Clone the repository.
2. Create and activate a Python virtual environment.
3. Install the core dependencies:

   ```bash
   pip install -r requirements.txt
   pip install gradio opencv-python pillow
   ```

4. Open `main.ipynb` in Jupyter Notebook or JupyterLab.
5. Update `base_dir` in the first cell if the project is located somewhere other than its original local Windows path. For a cloned repository, use:

   ```python
   base_dir = "flower_images"
   ```

6. Run the cells in order to train the model and start the optional Gradio prediction interface.

## Project structure

```text
.
├── flower_images/       # Training images, organized by flower class
├── main.ipynb           # Training and Gradio inference workflow
├── requirements.txt     # Core Python dependencies
└── README.md
```

## Notes

- Training can take several minutes, depending on your hardware.
- The notebook trains a model in memory; no pre-trained model file is included.
- Native Windows TensorFlow installations may use CPU only. Use a supported GPU setup such as WSL2 if GPU acceleration is needed.
