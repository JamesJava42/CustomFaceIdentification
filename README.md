Introduction
This project aims to create a face recognition system that can identify and label known faces in real-time using a webcam. It leverages MTCNN for face detection and a VGG16 model fine-tuned with an SVM classifier for face recognition.

Installation
To set up the project, follow these steps:

Installing the Libraries:
pip install mtcnn tensorflow keras opencv-python-headless matplotlib scikit-learn


Data-set preparation:
  Adding the images of the 5 people to train in the model

  Model Training:
    base_model = VGG16(weights='imagenet', include_top=False, input_shape=(224, 224, 3))
x = base_model.output
x = tf.keras.layers.Flatten()(x)
x = tf.keras.layers.Dense(256, activation='relu')(x)
model = Model(inputs=base_model.input, outputs=x)


Real TIme Face detection:

Detecting the images from he real cameara and making it to set unknow if not from the trained images.

