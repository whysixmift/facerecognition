
---

# Face Detection Using OpenCV

This Python project uses OpenCV to detect faces in real-time using your webcam. The program captures video feed from the camera and highlights detected faces with rectangles, displaying them in a GUI window.

## Features

- **Real-time face detection** using your webcam.
- **Haar Cascade classifier** to detect faces in video frames.
- **Live video feed** with detected faces highlighted in green.
- **Simple and easy-to-use** with just a webcam and OpenCV.
- **Exit the application** by pressing the "q" key.

## Requirements

- **Python 3.x** or higher.
- **OpenCV** library.

### To install OpenCV:

```bash
pip install opencv-python
```

## Installation

1. Clone or download this repository to your local machine.
2. Navigate to the project directory:

   ```bash
   cd path/to/project
   ```

3. Install OpenCV:

   ```bash
   pip install opencv-python
   ```

## How to Run the Program

1. Open a terminal or command prompt and navigate to the directory containing the Python script.
2. Run the program:

   ```bash
   python face_detection.py
   ```

3. The program will open a window showing your webcam feed. Any detected faces will be outlined with green rectangles.

4. Press the "q" key to exit the application.

## Code Explanation

### Face Detection with Haar Cascade

This program uses OpenCV’s **Haar Cascade** classifier for face detection. It applies this classifier to the frames of the video to detect faces in real-time.

### Video Capture

The program uses `cv2.VideoCapture(0)` to access the default webcam and captures each frame.

### Face Detection

The function `detectMultiScale()` detects faces in each frame. The faces are then marked with rectangles using the `cv2.rectangle()` function.

### Exit Mechanism

To exit the video window, simply press the "q" key on your keyboard.

```python
if cv2.waitKey(1) & 0xFF == ord('q'):
    break
```

## Customization

### Change Detection Classifier

The program uses OpenCV's pre-trained **Haar Cascade** classifier for detecting faces. You can experiment with other classifiers or train your own using OpenCV's tools.

To use another classifier:

```python
face_cascade = cv2.CascadeClassifier('path_to_new_classifier.xml')
```

### Use with Images Instead of Webcam

If you prefer to use a static image for face detection, you can modify the script to read an image file instead of capturing video frames.

```python
frame = cv2.imread('image_path.jpg')
```

### Adjust Detection Parameters

You can adjust the parameters of `detectMultiScale()` to improve accuracy or performance:

```python
faces = face_cascade.detectMultiScale(gray, scaleFactor=1.1, minNeighbors=5, minSize=(30, 30))
```

- `scaleFactor`: Compensates for the size difference between faces in the image.
- `minNeighbors`: Specifies how many neighbors each candidate rectangle should have to be retained.
- `minSize`: Minimum size of the detected face.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
