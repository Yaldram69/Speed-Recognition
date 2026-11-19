# Speed Recognition

Vehicle speed estimation on highway video using Ultralytics YOLO11 and the built-in `solutions.SpeedEstimator`. Vehicles are detected and tracked through a user-defined region, and their speed is estimated from the motion across that region. The project is a set of Jupyter/Colab notebooks.

## Features

- YOLO11 detection and tracking through the Ultralytics `solutions.SpeedEstimator` API
- User-defined speed region (a polygon of four points, set in the notebook)
- Optional frame resizing before detection to trade speed for accuracy
- Annotated output written to AVI files

## Project structure

- `Speed Recognition/` - project folder
  - `Speed_Recognition.ipynb` - main notebook, speed estimation on a highway video
  - `Speed_Recognition (1).ipynb` - second version of the notebook with a resize option
  - `highway444444.avi`, `highway5666.avi`, `speed_estimation1111111111.avi`, `speed_test.avi` - sample highway videos and outputs (large files)

## Requirements

Packages used by the notebooks:

- ultralytics (`solutions`, `YOLO`)
- opencv-python (`cv2`)
- numpy

Install:

```bash
pip install ultralytics opencv-python numpy
```

The first notebook cell runs `!pip install ultralytics`, which is written for Colab.

## Installation

```bash
pip install ultralytics opencv-python numpy
```

## Usage

Open a notebook in Jupyter or Google Colab and run the cells in order:

```bash
jupyter notebook "Speed Recognition/Speed_Recognition.ipynb"
```

- Input: a highway video. The notebooks read `/content/highway_mini.mp4`, a Colab path. That file is not included, so replace the path with one of the included `.avi` files or your own video.
- Model: `yolo11n.pt` (named in the notebook; not included in the folder, Ultralytics downloads it when available)
- Output: an AVI file written by OpenCV (names such as `highway3333.avi` are set in the notebook), and a display window if `show=True` is set

## Notes

- Paths in the notebooks are Colab paths (`/content/...`) and must be changed for local use.
- The speed region is fixed as pixel coordinates `[(20, 400), (1800, 400), (1800, 360), (20, 360)]` and must be adjusted for other videos.
- Speed values are estimates based on the pixel scale of the video and are not calibrated to real-world units in this code.
- The `.avi` files are large and are committed in the folder. Consider Git LFS if they are published.
