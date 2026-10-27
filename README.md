Project Overview
Surface Crack Detection is a Deep Learning image-classification project that uses a Convolutional Neural Network (CNN) to detect surface cracks in industrial images.

The project performs image preprocessing, data augmentation, dataset splitting, CNN model training, performance evaluation, model saving, and single-image prediction.

Objective
The objective of this project is to automatically classify industrial surface images into two categories:

Crack
No Crack
This type of image classification can be useful as a foundation for automated inspection systems in industrial environments.

Technologies Used
Python
TensorFlow
Keras
NumPy
Matplotlib
OpenCV
Scikit-learn
Project Workflow
Industrial Images ↓ Dataset Validation ↓ Train / Validation / Test Split ↓ Image Preprocessing ↓ Image Augmentation ↓ CNN Model ↓ Model Training ↓ Model Evaluation ↓ Confusion Matrix & Classification Report ↓ Save Trained Model ↓ Single Image Prediction

Dataset Structure
The original dataset is organized into two classes:

CrackDataset/ │ ├── Positive/ │ └── crack images │ └── Negative/ └── non-crack images

The program automatically creates a processed dataset with:

Processed_CrackDataset/ │ ├── train/ │ ├── Crack/ │ └── NoCrack/ │ ├── validation/ │ ├── Crack/ │ └── NoCrack/ │ └── test/ ├── Crack/ └── NoCrack/

The dataset is split approximately into:

70% Training
15% Validation
15% Testing
Image Preprocessing and Augmentation
Images are resized to:

128 × 128 pixels

Training images are normalized and augmented using:

Rescaling
Rotation
Zoom
Width shifting
Height shifting
Horizontal flipping
Validation and test images are rescaled without training augmentation.

CNN Architecture
The model is built using a Keras Sequential architecture.

The CNN contains:

4 Convolutional layers
Batch Normalization
Max Pooling
Flatten layer
Dense layers
Dropout
Sigmoid output layer
The convolutional layers use increasing filters:

32 → 64 → 128 → 256

The final layer performs binary classification using the sigmoid activation function.

Model Compilation
The model uses:

Optimizer: Adam Loss: Binary Crossentropy Metric: Accuracy

Training
The model is trained for a maximum of 15 epochs.

Training includes:

Early Stopping
Model Checkpointing
Learning Rate Reduction
These techniques help improve training stability and reduce unnecessary training.

Model Evaluation
The trained model is evaluated using unseen test images.

Performance evaluation includes:

Test Loss
Test Accuracy
Confusion Matrix
Classification Report
Training and validation performance are also visualized using:

Training vs Validation Accuracy
Training vs Validation Loss
Single Image Prediction
The project includes a function for predicting an individual image.

The input image is:

Loaded
Resized to 128 × 128
Converted into an array
Normalized
Passed through the trained CNN
Classified as either Crack Detected or No Crack
Model Files
The project saves trained models in Keras format:

Best_Crack_Detection_Model.keras Final_Crack_Detection_Model.keras

The best model is saved based on validation accuracy.

Project Structure
Surface-Crack-Detection/ │ ├── CNN_Surface_Crack_Detection.py ├── CrackDataset/ │ ├── Positive/ │ └── Negative/ │ ├── Processed_CrackDataset/ │ ├── train/ │ ├── validation/ │ └── test/ │ ├── Best_Crack_Detection_Model.keras ├── Final_Crack_Detection_Model.keras ├── README.md │ └── screenshots/ ├── sample_images.png ├── accuracy_graph.png ├── loss_graph.png └── confusion_matrix.png

Requirements
tensorflow numpy matplotlib opencv-python scikit-learn

How to Run
Run the Python program:

python CNN_Surface_Crack_Detection.py

The program will:

Validate the original dataset.
Create the processed dataset structure.
Split images into training, validation, and testing sets.
Apply image preprocessing and augmentation.
Build the CNN model.
Train the CNN.
Display training and validation graphs.
Evaluate the model on test data.
Generate a confusion matrix and classification report.
Save the trained model.
Perform single-image prediction.
Key Learning Outcomes
Through this project, I gained practical experience in:

Python programming
Deep Learning
Convolutional Neural Networks
Image preprocessing
Image augmentation
Binary image classification
TensorFlow and Keras
Model evaluation
Confusion matrix analysis
Training visualization
Model checkpointing
Single-image prediction
Future Improvements
Develop a Streamlit-based web interface.
Add real-time camera-based crack detection.
Improve the model using transfer learning.
Add more industrial surface categories.
Deploy the trained model as an inspection application.
Optimize the model for edge devices.
Disclaimer
This project is developed for educational and Deep Learning practice purposes. It should not be considered a certified industrial safety or structural inspection system.
