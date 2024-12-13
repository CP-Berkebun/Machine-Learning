# Berkebun+ Machine Learning 🌱

This repository contains Machine Learning’s data preparation and model development for Berkebun+ mobile application to detect plant disease based on user input’s image. 


## 📂 Project Structure

```plaintext
Machine Learning/
│
├── model.ipynb
|── nyoba.ipynb
|── dataset/
│   ├── treatment.xlsx
|   |── plant_images
│        ├── apple__rot
│         ...
│        ├── wheat__rot
|── disease.json
```

## 📊 Dataset
<ol>
  <li> Diseased Plant Images
    <ul>
      <li type="a">The image dataset was sourced from <a href="https://www.kaggle.com/datasets/alinedobrovsky/plant-disease-classification-merged-dataset">Kaggle Dataset</a></li>
      <li type="a">
        This project utilizes images of 9 plant types (e.g., apple, grape, etc.) from the dataset.
      </li>
      <li type="a">
        The dataset is organized into directories for each plant type, with subdirectories for individual diseases.
      </li>
    </ul>
  </li>
  <li>
    Plant Disease Description and Treatment
    <ul>
      <li type="a">
        This dataset is a .xlsx file.
      </li>
      <li type="a">
        It includes:
        <ul>
          <li type="I">Disease IDs</li>
          <li type="I">Disease descriptions</li>
          <li type="I">Treatment suggestions for each disease.</li>
        </ul>
      </li>
    </ul>
  </li>
</ol>

## 🛠️ Technologies used

This machine learning model uses the following technologies:

<ol>
  <li>TensorFlow/Keras: For creating, training, and evaluating deep learning models</li>
  <li>ImageDataGenerator: For image augmentation, allowing for rotation, shifting, shearing, zooming, and flipping of images to increase dataset diversity</li>
  <li>ResNet50: A pre-trained model that serves as the base for feature extraction through transfer learning</li>
  <li>Dense, GlobalAveragePooling2D: Layers used in the custom model for classification</li>
</ol>

## ⚙️ Setup Instructions
To set up local environment, follow these steps:

**1. Install Python**
<ul>
  <li type="a">Download the Python installer from the official website.</li>
  <li type="a">During the installation:
    <ul>
      <li type="i">Select "Add Python to PATH".</li>
      <li type="i">Choose "Install Now" or customize the installation as needed.</li>
    </ul>
  </li>
</ul>

**2. Install Required Libraries**

Open Command Prompt and run the following commands:<br>
:: Upgrade pip (optional but recommended)
```
  python -m pip install --upgrade pip
```

:: Install Jupyter Notebook
```
  python -m pip install notebook  
```

:: Install TensorFlow (including Keras)
```
  python -m pip install tensorflow  
```

:: Install Pillow (PIL library)
```
  python -m pip install pillow
```

**3. Verify Installation**

Run these commands in Command Prompt to confirm successful installations:
:: Verify Jupyter Notebook
```
  jupyter --version
```

:: Verify TensorFlow
```
  python -c "import tensorflow as tf; print(tf.__version__)"  
```

:: Verify Pillow
```
  python -c "from PIL import Image; print('Pillow installed successfully')"  
```

This model can also be set up in online notebooks such as Google Colab, Kaggle, and similar platforms.



## 📈 Usage and Results

To train the model, follow these steps:

<ol>
  <li>Import libraries needed inside the notebook</li>
  <li>Validate all the data</li>
  <li>Preproccess
    <ul>
      <li type="a">Will get augmented data etc.</li>
    </ul>
  </li>
  <li>Training, dst</li>
</ol>

After the training process, these are the outputs we get:
<ol>
  <li>Accuracy</li>
  <li>Result Example, dll</li>
</ol>
