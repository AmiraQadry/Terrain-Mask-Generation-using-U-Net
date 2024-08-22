# Terrain Mask Generation using U-Net

## Overview
This project involves building and training a U-Net model for terrain mask generation using [satellite images](https://www.kaggle.com/datasets/tpapp157/earth-terrain-height-and-segmentation-map-images). The U-Net architecture is used for image segmentation tasks, where the goal is to accurately segment terrain features from satellite imagery.

## Project Structure
The project consists of the following key components:

### 1. Data Loading
A data loader function is used to load the satellite images and corresponding terrain masks from a specified directory. The images and masks are resized to a consistent shape for model training.

### 2. U-Net Architecture
The U-Net model is implemented with the following characteristics:
- **Encoder Path**: The model captures features at multiple levels using a series of convolutional and max-pooling layers.
- **Decoder Path**: The model reconstructs the image to its original resolution, applying transposed convolutions, concatenations, and dropout layers.
- **Final Output**: A `Conv2D` layer with a sigmoid activation function is used to generate the final mask predictions.

### 3. Model Training
The model is compiled using the Adam optimizer, binary crossentropy loss, and accuracy as the evaluation metric. The training process is carried out for 50 epochs, with the training loss and accuracy plotted to visualize model performance.

### 4. Predictions and Visualization
A function is defined to make predictions on a batch of images and compare the predicted masks with the ground truth masks. The results are displayed using Matplotlib, showcasing the original image, the predicted mask, and the actual mask.

### 5. Image Sharpening
An image sharpening step is included to enhance the predicted masks, making the features more distinct.

### 6. Model Saving
The trained model is saved as an HDF5 file (`TerrainMaskGenerator.h5`) for future use.

## How to Run
1. **Data Preparation**: Ensure your satellite images and corresponding masks are organized in a directory structure suitable for loading.
2. **Model Training**: Execute the script to load the data, define the U-Net model, and train it on the provided dataset.
3. **Prediction and Evaluation**: Use the trained model to make predictions on test images and visualize the results.
4. **Model Saving**: Save the trained model for future inference.

## Dependencies
- Python 
- NumPy
- Pandas
- Matplotlib
- OpenCV
- TensorFlow

## Results
The trained U-Net model is capable of accurately segmenting terrain features from satellite images, as demonstrated by the prediction plots.

## Conclusion
This project successfully demonstrates the use of U-Net for image segmentation tasks, specifically for terrain mask generation. The model's architecture and training process can be adapted for various other image segmentation tasks as well.
