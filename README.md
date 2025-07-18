# persian-plate-recognition
## Persian License Plate Recognition System
This project implements a complete pipeline for detecting vehicles, recognizing license plates, and reading Persian license plate numbers from video footage. It combines three custom-trained deep learning models for vehicle detection, license plate detection, and Persian character recognition.

https://github.com/user-attachments/assets/dfa19290-e050-4639-97cf-ade2773abc01




## Key Features :

✅​ Vehicle Detection: YOLOv8 model fine-tuned for vehicle detection

✅​ License Plate Detection: Custom YOLOv8 model for license plate localization

✅​ Persian OCR: CRNN model specialized for Persian license plate recognition

✅​ Object Tracking: ByteTrack for consistent vehicle tracking across frames

✅​ Data Interpolation: Smooths bounding boxes for better visualization

✅​ Video Processing: Processes input videos and generates annotated output

✅​ Persian Text Rendering: Proper bidirectional text support for Persian characters



## 🚀 How to Run the Project
Prerequisites
Python 3.8+
Install from python.org

### Git
Install from git-scm.com

## Step-by-Step Instructions
bash
# 1. Clone the repository
git clone https://github.com/mahdimtd/persian-plate-recognition.git
cd persian-plate-recognition

# 2. Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # Linux/MacOS
venv\Scripts\activate    # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Download pre-trained weights
# ⚠️ Place your model weights in the specified directory (e.g., `weights/`)
#    Refer to repository structure for correct paths

# 5. Run inference on test images
python detect.py --source test_images/  # Replace with your image/directory path
Key Arguments for detect.py
Argument	Description	Default
--source	Input path (image/video/directory)	test_images/
--weights	Model weights path	weights/
--conf-threshold	Confidence threshold (0-1)	0.5
--output	Output directory	results/
Example:

bash
python detect.py --source input.jpg --weights weights/model.pth --output results/
Notes
🔋 Pre-trained Models: Download weights from repository releases/assets and place them in weights/

📂 Test Images: Add your own images to test_images/ or specify a custom path

🐋 Docker Support: If available, include Docker instructions here

🖥️ GPU Acceleration: Requires CUDA-compatible GPU and torch GPU version

Expected Output
Results will be saved in the --output directory with:

Annotated images (input_processed.jpg)

Text files containing plate detections (input.txt)





