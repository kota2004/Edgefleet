# Edgefleet

# Cricket Ball Detection and Trajectory Tracking

This project detects the centroid of a cricket ball in each frame of a video captured from a static camera.
It generates a processed video with the ball trajectory and a CSV file containing per-frame annotations.

---

## Features

* Detects cricket ball using color-based segmentation.
* Tracks the ball using temporal consistency.
* Generates trajectory overlay on output video.
* Produces per-frame centroid annotations.

---

## Requirements

Install the required libraries:

```bash
pip install opencv-python numpy pandas
```

---

## Input

* Cricket video from a static camera.
* Supported format: **.mp4**

If your video is in `.mov` format, convert it:

```bash
ffmpeg -i input.mov input.mp4
```

---

## How to Run

1. Place your video file in the same directory as the script.

2. Open the Python script and set:

```python
video_path = "your_video.mp4"
```

3. Run the script:

```bash
python cricket_ball_detection.py
```

---

## Output

For each video, the following files are generated:

* `output_with_trajectory.mp4`
  → Processed video with ball trajectory

* `ball_annotations.csv`
  → Per-frame ball centroid data

CSV format:

```
frame_index, x_centroid, y_centroid, visibility_flag
```

If the ball is not visible:

```
x = -1, y = -1, visibility_flag = 0
```

---

## Multi-Video Processing

To process multiple videos, place them in a folder and modify the main script to loop through all files.

---

## Author

Dhana Lakshmi
AI22BTECH11012
