# 🖐️ Sign Language Recognition and Text-to-Speech System

A real-time American Sign Language (ASL) recognition system that converts hand gestures into text and speech using computer vision and deep learning. Built with Python, OpenCV, TensorFlow, and a custom-trained CNN model, this application empowers accessibility by enabling hands-free communication through sign language.

## 🚀 Features

### ✅ Core Functionalities
- **Hand Gesture Recognition**: Real-time detection of hand gestures using 21-point landmarks extracted via cvzone's HandDetector.
- **Deep Learning-based Alphabet Prediction**: A Convolutional Neural Network (CNN) trained on 26 classes (A-Z) using skeletonized hand images, achieving >95% validation accuracy.
- **Text-to-Speech Integration**: Converts the constructed sentence from hand signs to audible speech using pyttsx3.
- **Word and Sentence Suggestions**:
  - Next Word Prediction using an NLTK-trained Trigram Language Model on the Brown Corpus.
  - Auto Spell Correction with SymSpell based on dictionary frequency and edit distance.
- **Gesture Controls for Text Manipulation**:
  - ✋ Open Hand → Insert Space
  - 👍 Thumb Out → Backspace
- **Hands-Free Operation**: Completely keyboard-free communication using gestures.

### 🧠 Model Architecture
- **Input**: 55x55 grayscale images of skeletonized hand gestures
- **Layers**:
  - 3 Conv2D layers + BatchNormalization + MaxPooling + Dropout
  - Fully Connected Layers: 512, 256 neurons + Dropout
  - Output: Softmax layer with 26 nodes (A-Z)
- **Training Techniques**:
  - Data Augmentation: Rotation, Zoom, Shear, Flip
  - Early Stopping and ReduceLROnPlateau
  - ModelCheckpoint for best validation accuracy

### 📸 GUI Overview
Built using Tkinter with the following features:
- Live camera feed panel
- Skeleton drawing panel
- Current prediction with confidence level
- Sentence builder with:
  - Word suggestions
  - Next word suggestions
- Control buttons: Speak, Auto-Correct, Backspace, Clear

### 📁 File Structure
├── alphabetPred.py # Basic skeleton-to-letter prediction with OpenCV
├── final1pred.py # Full GUI-based ASL-to-speech system
├── handAcquisition.py # Data collection tool to save hand skeletons per letter
├── trainmodel.py # CNN training script with data augmentation
├── AtoZ_3.1/ # Dataset folder (26 folders for each alphabet)
├── model-bw.weights.h5 # Trained Keras model
├── best_model.h5
├── model-bw.json # Model architecture in JSON format


*###Demo Video*
https://drive.google.com/file/d/16yT3klPjl3PsZSrgbyzHKy-9Tp2QJMB_/view?usp=sharing




### 🆕 Unique Aspects
- **Skeleton-Based Image Generation**: Uses structured 2D skeleton lines instead of raw RGB images, improving generalization and reducing noise.
- **Hands-Free Control**: Users can insert space or backspace via gestures, making it usable by people with limited keyboard access.
- **Integrated Language Understanding**: Context-aware suggestions using NLP techniques.

### 🧪 Future Enhancements
- Support for dynamic gestures (motion-based signs)
- Expansion to numbers and ASL-specific phrases
- Web or mobile deployment (Flask/Kivy)
- Multi-hand tracking and recognition

### 🛠️ Technologies Used
- **Languages & Libraries**: Python, OpenCV, TensorFlow, Keras, NLTK, SymSpellPy, Tkinter, PIL, cvzone
- **Model Type**: Custom CNN for image classification
- **NLP Tools**: NLTK (Trigram language model), SymSpell (spell correction)


