# CodeClause_Ai_Intern_Gesture_Recognition

Title: Development of a Gesture Recognition System
Summary:

Setup Paths and Label Map

Setting Up Paths:
Define paths for various components like workspace, scripts, models, annotations, images, and configuration.

Create Label Map:
Define the labels ('Sign language') with their respective IDs.
Write this information to a label map file (label_map.pbtxt).
Create TFRecords

Generate TFRecords:
Run a script to convert labeled images into TFRecord format, which is required by the TensorFlow Object Detection API.
The script is run twice, once for training images and once for testing images.
Download Pretrained Models

Clone TensorFlow Models:
Clone the TensorFlow models repository, which contains the implementation of various model architectures.
Download and extract a pretrained SSD MobileNet model from the TensorFlow Model Zoo.
Configure the Model for Transfer Learning

Copy Model Config to Training Folder:
Create a directory for the custom model and copy the configuration file of the pretrained model into this directory.

Update Config for Transfer Learning:
Load the model configuration and update it for transfer learning. Specifically, set the number of classes, batch size, and paths to the fine-tuning checkpoint and TFRecord files.
Train the Model

Train the Model:
Use the model_main_tf2.py script to start the training process. The training will use the specified model directory and pipeline configuration, and it will run for a defined number of steps.
Load Trained Model from Checkpoint

Load the Trained Model:
Load the trained model from a checkpoint.
Define a function (detect_fn) to process input images and run detection using the loaded model.
Detect in Real-Time

Real-Time Detection:
Use OpenCV to capture video from a webcam.
For each frame, preprocess the image and run the detection function.
Visualize the detected boxes and labels on the frame.
Display the frame with detections in a window. The loop breaks when the 'q' key is pressed.
