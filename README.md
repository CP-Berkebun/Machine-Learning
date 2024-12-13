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
Verify Jupyter Notebook
```
  jupyter --version
```

Verify TensorFlow
```
  python -c "import tensorflow as tf; print(tf.__version__)"  
```

Verify Pillow
```
  python -c "from PIL import Image; print('Pillow installed successfully')"  
```

This model can also be set up in online notebooks such as Google Colab, Kaggle, and similar platforms.


## 📈 Usage and Results

To train the model, follow these steps:

<ol>
  <li>Import Libraries  
    Begin by importing all necessary libraries to handle image loading, preprocessing, augmentation, and model building, such as <code>ImageDataGenerator</code>, <code>ResNet50</code>, <code>GlobalAveragePooling2D</code>, and others.
  </li>
  <li>Validate and Filter Data  
    <ul>
      <li>Ensure that only valid image files (JPG, PNG, JPEG) are considered for the dataset.</li>
      <li>Skip any corrupted or invalid images to ensure the data is clean for training.</li>
      <li>Filter the dataset to include only the selected crops, ensuring each category is properly labeled in the dataset.</li>
    </ul>
  </li>
  <li>Data Augmentation and Preprocessing  
    <ul>
      <li>Apply image augmentation (rotation, width/height shift, shear, zoom, and horizontal flip) to enrich the training dataset.</li>
      <li>The dataset is augmented until each crop class reaches a minimum number of 2000 images. If the original number of images in a class is less than 2000, augmentation is performed to reach the required size.</li>
      <li>Resize images to 224x224 pixels as the input size for the model.</li>
    </ul>
  </li>
  <li>Dataset Splitting  
    <ul>
      <li>Split the dataset into training, validation, and testing sets with a ratio of 80%, 10%, and 10% respectively.</li>
      <li>Save the data in separate directories for each split (train, val, test), organized by the Indonesian crop labels.</li>
    </ul>
  </li>
  <li>Model Training  
    <ul>
      <li>Use a <code>ResNet50</code> model (without the top layer) as the base for feature extraction.</li>
      <li>Add custom dense layers on top to classify the crops and diseases.</li>
      <li>Train the model using the augmented training data with the Adam optimizer and categorical cross-entropy loss function.</li>
      <li>Apply callbacks like early stopping and model checkpointing to ensure optimal model performance.</li>
    </ul>
  </li>
  <li>Model Evaluation  
    <ul>
      <li>After training, evaluate the model using the test dataset to measure its accuracy.</li>
      <li>The model's performance is reported as a test accuracy percentage.</li>
    </ul>
  </li>
</ol>

After the training process, these are the outputs we get:

<ol>
  <li>Accuracy  
    The final test accuracy is reported after evaluating the model on the test dataset.
  </li>
  <li>Augmented Images  
    Augmented images are saved in the output directory (<code>/kaggle/working/augmented_data</code>). These images are used for training, ensuring a diverse dataset for the model.
  </li>
  <li>Trained Model  
    The best model is saved in the file <code>/kaggle/working/best_model_2.keras</code>. This model can be used for inference on new, unseen data.
  </li>
  <li>Example Results  
    After training, you can visualize the model's performance on the validation set and see the predicted results on test images.
  </li>
</ol>

