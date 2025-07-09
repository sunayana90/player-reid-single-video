# Player Re-Identification in a Single Video

This project implements a player re-identification pipeline using YOLOv11 for detection and a simple IoU-based tracker to assign consistent player IDs, even when players leave and re-enter the frame.

## 📁 Files

- `main.ipynb`: Google Colab notebook containing the full pipeline.
- `tracked_output.mp4`: Example output video with bounding boxes and IDs.

## 🚀 How to Run

1. Open [Google Colab](https://colab.research.google.com/).
2. Upload your video (`15sec_input_720p.mp4`) and YOLOv11 model weights.
3. Install dependencies:

   ```python
   !pip install ultralytics opencv-python-headless numpy
   !apt-get install ffmpeg
   ```

4. Load the YOLO model:

   ```python
   from ultralytics import YOLO
   model = YOLO("best.pt")  
   ```

5. Run the main processing cell (tracking code provided in the notebook).

6. Download the output video:

   ```python
   from google.colab import files
   files.download('tracked_output.mp4')
   ```

## ✨ Output Example

Each detected player has:
- A bounding box
- A consistent ID (e.g., ID 0, ID 1) maintained across frames

## ⚙️ Dependencies

- Python 3.8+
- Ultralytics YOLOv11
- OpenCV
- NumPy

## 🔧 Improvements

To improve tracking accuracy:
- Integrate **DeepSORT** for appearance-based tracking.
- Apply temporal smoothing and re-ID embeddings.

## 🧠 Author

Sunayana Yadav
