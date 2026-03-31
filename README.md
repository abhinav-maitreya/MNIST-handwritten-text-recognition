# MNIST-handwritten-text-recognition
this project has handwritten text recognition implementation.

1. Project Description:
The objective of this project is to develop a Digit Recognition System using the MNIST dataset. The MNIST (Modified National Institute of Standards and Technology) database is a "hello world" dataset in computer vision, consisting of 70,000 grayscale images of handwritten digits (0–9), each sized at $28 \times 28$ pixels.

Technical Stack:
Deep Learning Framework: Keras (running on TensorFlow).
Data Manipulation: NumPy.
Visualization: Matplotlib.
Image Processing: OpenCV (cv2) and PIL (for custom image testing).

2. Technical Analysis:
A. Data Preprocessing:
The notebook follows standard best practices for preparing image data:
Loading: It separates the data into 60,000 training images and 10,000 test images.
Normalization: Pixel values are scaled from the range [0, 255] to [0, 1]. This helps the neural network converge faster during gradient descent.
One-Hot Encoding: The labels (integers 0–9) are converted into categorical vectors (e.g., 5 becomes [0,0,0,0,0,1,0,0,0,0]) using to_categorical.
Reshaping: Since the model uses Dense (fully connected) layers rather than Convolutional layers, the 28 times 28 2D images are "flattened" into a 1D vector of 784 pixels.

B. Model Architecture:
The project defines a Multilayer Perceptron (MLP). The architecture is as follows:
Input Layer: 784 neurons (one for each pixel).
Hidden Layer 1: 10 neurons with ReLU activation.
Hidden Layer 2: 30 neurons with ReLU activation.
Hidden Layer 3: 10 neurons with ReLU activation.
Output Layer: 10 neurons with Softmax activation (outputting probabilities for each of the 10 digits).
Optimization: The model uses the Adam optimizer with a learning rate of 0.01 and Categorical Crossentropy as the loss function.

C. Training PerformanceEpochs: 10Batch Size: 200
Validation Split: 10% of the training data is held back to monitor for overfitting.
Results: The model achieved a Test Accuracy of ~93.18%.
Overfitting Check: The notebook includes code to plot Loss and Accuracy. The logs show that validation accuracy remains high (94.18\%), suggesting the model generalizes well for a basic ANN.

D. External Testing:
A unique part of this notebook is the "In-the-wild" test. The code:
Downloads a random image of a digit from a URL.Uses OpenCV to resize it to 28 times 28, convert it to grayscale, and invert the colors (to match the MNIST format of white-on-black).
Predicts the digit. 
In the provided output, the model correctly predicted the digit '2'.3. 

Observations and Recommendations Scalability:
The notebook correctly notes in the comments that "Linear NN is NOT scalable when dealing with more complex data.While 93% is good for a simple ANN, a Convolutional Neural Network (CNN) using Conv2D layers would likely push the accuracy above 99%.

Bottleneck Architecture: The first hidden layer has only 10 neurons. This is quite small and acts as a "bottleneck," potentially discarding useful spatial information early on. Increasing the width of the first layer (e.g., to 128 or 512) would improve performance. 

Deprecation Warning: The code uses model.predict_classes(), which is deprecated in newer versions of TensorFlow. It is recommended to use np.argmax(model.predict(img), axis=-1) instead.
