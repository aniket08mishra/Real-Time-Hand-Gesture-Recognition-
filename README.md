Gesture Recognition with Hand Tracking
This project utilizes OpenCV, MediaPipe, and PyAutoGUI to enable real-time gesture recognition and control for a computer screen. Using a webcam feed, the program detects hand gestures to simulate mouse movements and keyboard actions, such as swipe gestures and a "rock gesture" to control the spacebar.

Table of Contents
Overview
Demo
Features
Requirements
Installation
Usage
Code Explanation
Future Improvements
Acknowledgements
Overview
This project is a hand-gesture-controlled interface designed to interact with computer screens using specific hand movements. With MediaPipe's hand tracking, gestures are recognized and translated into on-screen actions, allowing you to:

Control the mouse pointer with your left hand.
Simulate keyboard swipes with your right hand.
Perform specific gestures to trigger actions, like a "rock gesture" for pausing (spacebar).
Demo

Features
Mouse Control: Move the mouse pointer by positioning your left hand on the screen.
Swipe Gestures: Swipe up, down, left, or right to trigger arrow key actions on your keyboard.
Rock Gesture: Make a rock gesture with your right hand to press the spacebar.
Requirements
Python 3.x
OpenCV for image processing
MediaPipe for hand tracking
PyAutoGUI for simulating mouse and keyboard events
Install the dependencies using:

bash
Copy code
pip install opencv-python mediapipe pyautogui
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/your_username/gesture-recognition.git
cd gesture-recognition
Install dependencies:

bash
Copy code
pip install -r requirements.txt
Usage
Run the script using:

bash
Copy code
python main.py
Controls:

Left Hand: Controls the mouse pointer.
Right Hand Swipe: Simulates keyboard arrow keys.
Swipe right → Right arrow key
Swipe left → Left arrow key
Swipe up → Up arrow key
Swipe down → Down arrow key
Rock Gesture (Right Hand): Presses the spacebar.
Press 'q' to exit the program.

Code Explanation
Hand Tracking Initialization:
The MediaPipe library initializes hand detection (mp_hands.Hands()) and tracks hand landmarks.

Screen Resolution and Webcam Feed:
PyAutoGUI detects the screen resolution, and OpenCV captures the webcam feed. The frame is horizontally flipped for a mirror effect.

Gesture Recognition:

Mouse Control with Left Hand:
The left hand’s middle finger's MCP (middle knuckle) is used to track and move the mouse cursor.
Swipe Gestures with Right Hand:
The position of the index finger tip (INDEX_FINGER_TIP) is used to calculate swipe movements, triggering arrow key events.
Rock Gesture for Spacebar:
The distance between the thumb tip and the pinky MCP landmark is used to detect a rock gesture, simulating a spacebar press.
Real-Time Drawing on Frame:
MediaPipe’s drawing utilities mark hand connections on the frame for a better visual representation of gestures.

Future Improvements
Add additional gestures for more keyboard controls.
Improve gesture accuracy and tracking speed.
Customize gesture mappings to allow user preferences.
Acknowledgements
MediaPipe by Google for efficient hand-tracking.
OpenCV for image processing and handling video feed.
PyAutoGUI for handling mouse and keyboard automation.
License
This project is licensed under the MIT License.

