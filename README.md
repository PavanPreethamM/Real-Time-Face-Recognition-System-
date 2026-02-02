# Real-Time-Face-Recognition-System-
This project implements a robust system for detecting and identifying individuals in a live video stream using a hybrid approach of classical computer vision and deep learning. By combining the speed of Haar Cascade classifiers with the feature extraction power of the AlexNet architecture.
Core Technologies & Toolboxes
The system is developed in MATLAB R2021a and requires the following components:


Computer Vision Toolbox: Used to interface with OpenCV for efficient face detection.


Deep Learning Toolbox: Provides the pre-trained AlexNet model and training environment.


MATLAB Support Package for USB Webcams: Enables real-time acquisition of video frames.

The workflow is divided into four distinct modules to ensure modularity and scalability:

1. Face Detection Module
The system captures live video frames and uses a Haar Cascade Classifier (Viola-Jones framework) to scan for facial regions. This method is chosen for its low computational overhead, allowing it to process multiple faces in a single frame without lagging.

2. Preprocessing & Normalization
Once a face is detected, the region is cropped and resized to 227x227 pixels to match the standard input dimensions required by AlexNet. The system also normalizes pixel values and performs data augmentation—such as rotation and brightness adjustments—to improve model robustness.

3. Deep Learning Classification (AlexNet)
The "brain" of the system is a fine-tuned AlexNet CNN.


Transfer Learning: The earlier layers of the pre-trained network are "frozen" to preserve general feature extraction knowledge.


Custom Layers: The final fully connected layers are replaced and retrained on a custom dataset tailored to the specific individuals being recognized.


Training: The model is trained for 20 epochs using GPU acceleration to minimize training time while maximizing accuracy.

4. Real-Time Annotation & UI
The final output overlays a bounding box and a predicted label (e.g., "Person 1" or "Ramana") directly onto the live video feed. To enhance usability, the interface provides feedback if no face is detected, ensuring a smooth user experience
Key Performance Features

Parallel Execution: The architecture is optimized to perform detection and classification concurrently using hardware-enabled GPUs.


Accuracy: By using a library of approximately 150 labeled images per individual, the model learns to generalize effectively across different expressions and lighting conditions.


Scalability: The modular design allows the system to be deployed on edge devices for local processing or integrated into cloud-based surveillance environments.
