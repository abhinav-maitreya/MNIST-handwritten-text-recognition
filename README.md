# MNIST-handwritten-text-recognition
this project has handwritten text recognition implementation.

MNIST Handwritten Digit Recognition
This project implements an Artificial Neural Network (ANN) to classify handwritten digits (0-9) using the classic MNIST dataset. The model is built using Keras and TensorFlow, achieving a test accuracy of approximately 93.18%. 

Project Overview
The goal of this project is to demonstrate a complete machine learning workflow, from data preprocessing and visualization to model training and real-world image prediction. While basic dense layers are used here, the project highlights the fundamental challenges of image classification, such as data normalization and the "generalization gap" between training and validation performance. 

Key Features
Data Pipeline: Automated loading and splitting of the MNIST dataset (60,000 training / 10,000 testing images).
Normalization: Scales pixel values to a [0, 1] range for faster convergence. 
ANN Architecture: A multi-layer perceptron with three hidden layers and ReLU activation.
Evaluation: Visualizes training history (loss and accuracy curves) to monitor for overfitting.
In-the-Wild Testing: A custom script using OpenCV and PIL to process and predict digits from external URLs. 

Results:
After training for 10 epochs with a batch size of 200, the model achieved:
Training Accuracy: ~93.42%
Validation Accuracy: ~94.18%
Test Accuracy: 93.18%

Training Visualization:
The project generates plots for Loss and Accuracy to help identify if the model starts to overfit during the generalization phase. 

Installation & UsageClone the repository: Bashgit clone https://github.com/your-username/mnist-digit-recognition.git

Install dependencies: Bashpip install numpy matplotlib tensorflow opencv-python pillow requests.

Run the Notebook:Open MNIST_Image_Recognition.ipynb in Jupyter Notebook or Google Colab and run all cells. External Image PredictionThe project includes a utility to test the model on images outside the dataset. It uses cv2 to:Resize images to 28 times 28 pixels. Convert to grayscale. Invert colors to match the MNIST format.
