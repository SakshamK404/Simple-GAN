# Simple-GAN
This code is a JSON representation of a Jupyter Notebook containing Python code for implementing a Generative Adversarial Network (GAN) using TensorFlow and Keras. Let's break down its structure and functionality:

1. **Notebook Metadata**:
   - `nbformat` and `nbformat_minor`: The notebook format version.
   - `metadata`: Additional metadata including information about the notebook's origin, kernel specification, and language information.

2. **Cells**:
   - The notebook contains a single code cell.
   - `cell_type`: Specifies that the cell contains code.
   - `execution_count`: Indicates that the cell has not been executed yet.
   - `metadata`: Contains an identifier for the cell.
   - `outputs`: Empty list to store the cell's output.
   - `source`: Contains the Python code to be executed.

3. **Python Code**:
   - **Imports**: The code imports necessary libraries including TensorFlow, Keras, NumPy, and Matplotlib.
   - **Data Loading**: CIFAR-10 dataset is loaded using TensorFlow's built-in function. The data is then normalized to the range [0, 1].
   - **Generator Model Definition**: Defines a generator model using Keras Sequential API. The generator takes random noise as input and outputs generated images.
   - **Discriminator Model Definition**: Defines a discriminator model using Keras Sequential API. The discriminator takes images as input and predicts whether they are real or fake.
   - **GAN Model Definition**: Combines the generator and discriminator into a GAN model. The discriminator is frozen during training of the GAN.
   - **Model Compilation**: Compiles both the discriminator and GAN models with appropriate optimizers and loss functions.
   - **Training Loop**: Iterates over a specified number of epochs and training steps per epoch. In each step:
     - Random noise vectors are generated as input to the generator.
     - Fake images are generated using the generator.
     - Real images are sampled from the dataset.
     - Discriminator is trained on both real and fake images with corresponding labels.
     - Generator is trained via the GAN model with misleading targets.
     - Progress is printed periodically.
   - **Image Generation**: After each epoch, a set number of sample images are generated using the trained generator and displayed using Matplotlib.

This code demonstrates the implementation of a GAN model for generating synthetic images. It trains the generator and discriminator models simultaneously in an adversarial manner to produce realistic images. The output includes the loss values for both the discriminator and generator during training, as well as sample images generated at the end of each epoch for visual inspection.
