# Lane Detection using Binary Thresholding, UDP, etc....

## Overview
This project implements a lane detection system using computer vision to guide an ESP32-based robot. The system processes video streams from an ESP32-CAM, detects lanes using **binary thresholding**, and sends steering commands to the robot via **UDP** communication. Developed during an internship, this project showcases efficient real-time image processing and network communication, with output videos demonstrating its performance in action.

## Key Features
- **Lane Detection with Binary Thresholding**: Utilizes OpenCV's binary thresholding to convert video frames into binary images, isolating lane markings for robust detection. This technique ensures reliable lane identification under varying lighting conditions by enhancing contrast between lanes and the background.
- **UDP Communication**: Employs UDP for low-latency, real-time command transmission between the computer vision system and the ESP32 robot, enabling rapid steering adjustments based on lane detection results.
- **Adaptive Contour Tracking**: Dynamically adjusts the minimum contour area threshold based on historical data, improving lane detection accuracy.
- **Real-Time Video Streaming**: Processes a live video feed from an ESP32-CAM, rotated 180° to correct orientation, and displays processed frames with lane overlays and steering information.
- **FPS Monitoring**: Calculates and displays frames per second to monitor system performance.

## Demo Videos
The following videos showcase the project's lane detection and robot control in action:
- **[](./Output/outputScreen_1.mp4)**
- **[](./Output/outputScreen_2.mp4)**

## Project Components
- **Python Script (Computer Vision)**:
  - Captures and processes video streams from the ESP32-CAM.
  - Applies binary thresholding to detect lanes within a defined region of interest (ROI).
  - Calculates steering angles based on the center of detected lanes.
  - Sends commands (`f`orward, `l`eft, `r`ight, `s`top) with speed values to the robot via UDP.
  - Displays binary and highlighted frames with lane overlays, steering direction, and performance metrics.
- **ESP32 Firmware**:
  - Configures the ESP32 as a local network with a static IP (192.168.82.10).
  - Listens for UDP packets on port 8888 and interprets commands to control motor movements.
  - Supports variable motor speeds (0-255) for precise control.
  - Drives four motors using PWM for forward, backward, left, and right movements.
  - ESP32-CAM hosts the video stream in the local network.

## Why This Project Stands Out
- **Efficient Use of Binary Thresholding**: The binary thresholding technique simplifies lane detection by converting grayscale images into binary, making it computationally efficient and robust for real-time applications.
- **Low-Latency UDP Communication**: UDP's lightweight protocol ensures minimal delay in sending steering commands, critical for responsive robot control in dynamic environments.
- **Integration of Hardware and Software**: Seamlessly combines computer vision with embedded systems, as demonstrated in the output videos, showcasing practical autonomous navigation.

## Acknowledgments
This project was developed during an internship, leveraging computer vision and embedded systems to create a practical autonomous navigation system. The output videos highlight the system's real-world performance. Special thanks to the internship team for their guidance and support.
