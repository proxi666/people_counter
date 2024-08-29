# People Counting Project

This project implements a people counting system using the YOLOv8 model for object detection and the SORT algorithm for tracking. The system counts people moving across two designated lines in a video feed, distinguishing between those moving up and down.

## Features
- **Object Detection:** Utilizes YOLOv8 for detecting various classes of objects, specifically focusing on people in this project.
- **Object Tracking:** Implements the SORT (Simple Online and Realtime Tracking) algorithm for tracking people across frames.
- **Custom Masking:** Applies a mask to focus the detection on a specific region of interest in the video feed.
- **Counting Logic:** Counts people crossing two defined lines (upward and downward) within the frame, using their center coordinates.

## How It Works
1. **Object Detection:**
   - The script uses a pre-trained YOLOv8 model (`yolov8n.pt`) to detect objects in each frame of the video.
   - Only people (`person` class) with confidence scores above 0.3 are considered for counting.

2. **Tracking:**
   - The SORT tracker is used to maintain the identity of people across frames, allowing for accurate counting.
   - Each person is assigned an ID that persists until they leave the frame.

3. **Counting:**
   - Two red lines are drawn at specific positions in the frame, acting as counting thresholds (one for upward movement and one for downward movement).
   - People crossing these lines are counted, and the counts are displayed on the frame.
   - The lines change color to green when a person is successfully counted.

## Prerequisites
- Python 3.x
- OpenCV
- YOLOv8 (from `ultralytics` package)
- `cvzone` library for drawing bounding boxes and text.
- `sort` library for tracking.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/proxi666/people-counting.git
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   
## Usage

1. Run the people_counter.py script:
 ```bash
  python people_counter.py
