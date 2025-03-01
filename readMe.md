# Drowsiness Detection System

## Overview
This project implements a drowsiness detection system using OpenCV, dlib, and playsound. The system detects a user's face and monitors their eye aspect ratio (EAR) to determine if they are drowsy. If the EAR falls below a predefined threshold for a certain number of frames, an alert message is displayed, and an alarm sound is played to wake up the user.

## Features
- Real-time face and eye detection
- Eye Aspect Ratio (EAR) calculation to detect drowsiness
- Visual alert message displayed on the screen
- Audio alarm when drowsiness is detected

## Dependencies
Ensure you have the following dependencies installed before running the script:

```sh
pip install opencv-python imutils dlib playsound
```

Additionally, you need to download the pre-trained dlib facial landmark model:

- [shape_predictor_68_face_landmarks.dat](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2)

Extract and place the file in the `models/` directory of your project.

## Installation
1. Clone the repository:
```sh
git clone https://github.com/yourusername/drowsiness-detection.git
```
2. Navigate to the project directory:
```sh
cd drowsiness-detection
```
3. Install required dependencies:
```sh
pip install -r requirements.txt
```

## Usage
Run the script to start the drowsiness detection system:
```sh
python drowsiness_detection.py
```

### Key Components:
- `eye_aspect_ratio(eye)`: Computes the EAR to determine if eyes are closed.
- `detect`: Uses dlib's frontal face detector.
- `predict`: Uses dlib's landmark predictor to identify facial landmarks.
- `playsound()`: Triggers an alarm sound if drowsiness is detected.

### Controls:
- Press `q` to exit the program.

## Configuration
You can modify the following parameters to fine-tune detection:
- `thresh = 0.25` (Eye Aspect Ratio threshold for drowsiness detection)
- `frame_check = 20` (Number of consecutive frames required to trigger an alert)

## Troubleshooting
- Ensure your webcam is properly connected.
- If the alarm sound does not play, check the path to the `.mp3` file and verify that `playsound` is installed.
- If `dlib` installation fails, ensure you have CMake installed and use:
  ```sh
  pip install dlib --verbose
  ```

## License
This project is open-source and available under the [MIT License](LICENSE).

## Acknowledgments
- OpenCV and dlib for facial landmark detection
- Imutils for image processing helpers

