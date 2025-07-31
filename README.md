Introduction
This project is a practical guide for setting up real-time object detection and tracking on a Raspberry Pi using a camera and open-source computer vision tools. It’s ideal for DIY and maker projects, enabling detection and tracking of objects by color, shape, features, faces, and even with deep learning. The code runs on Python and OpenCV, making it portable across Linux systems such as PC, Nvidia Jetson, Banana Pi, and more.

Dependencies
Required Packages
Python (version 3.5 or later)

OpenCV-Python

OpenCV-Contrib-Python

NumPy

SciPy

Matplotlib

Ultralytics (for YOLO tasks)

Hardware Support
Raspberry Pi 1/2/Zero/3/4/5 (higher models recommended for better performance)

Nvidia Jetson Nano/Orin

Any USB camera compatible with Raspberry Pi

Official RPi camera module (supported via Picamera2)

Most scripts can also run on other Linux single-board computers.

Features & Implementations
Camera Test: Verify that your camera setup and environment are working.

Motion Detection: Detects movement in video frames.

Color-based Object Tracking: Tracks objects by color in HSV space, with interactive color selection.

Shape-based Object Tracking: Detects and tracks round (and soon square) objects.

Feature-based Object Tracking: Uses ORB algorithm for fast detection and tracking of distinctive objects.

Face Detection: Fast face detection and tracking using Haar cascades.

YOLO Object Detection: (RPi 3/4/5) Real-time deep learning object detection (You Only Look Once algorithm).

TensorFlow Lite Object Detection: Deep learning detection using efficient models (work in progress).

How to Run
1. Install Dependencies
bash
sudo apt-get install -y libopencv-dev libatlas-base-dev
pip3 install virtualenv Pillow numpy scipy matplotlib opencv-python opencv-contrib-python
Or use the automated script:

bash
chmod +x install.sh
./install.sh
2. (Optional) Install TensorFlow Lite
For neural network-based detection:

bash
wget https://github.com/PINTO0309/Tensorflow-bin/raw/master/tensorflow-2.1.0-cp37-cp37m-linux_armv7l.whl
pip3 install --upgrade setuptools
pip3 install tensorflow-2.1.0-cp37-cp37m-linux_armv7l.whl
pip3 install -e .
3. Run Scripts
All main scripts are under the /src folder.
Run with:

bash
python3 src/<feature-folder>/<script-name>.py
(e.g., python3 src/motion-detection/motion_detection.py)

Stop any running script by pressing the ESC key.

4. Change Camera Resolution
Edit IMAGE_WIDTH and IMAGE_HEIGHT at the start of each script to change resolution; common options are:

160x120, 320x240 (default), 640x480, 1280x720, 1920x1080

FAQ
Support for Nvidia Jetson: Yes, tested.

Support for RPi camera module: Yes.

RPi 5 compatibility: Not officially tested but expected to work.

Ubuntu Server 22.04: Majority of features work; some may require minor tweaks.

Trouble with ‘libcamera’ in a virtual environment? Create your venv with --system-site-packages.
