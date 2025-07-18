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


# How to Run

## Prerequisites

Before running the Persian License Plate Recognition system, ensure you have the following installed:

- **Python 3.8+** - Download from [python.org](https://www.python.org/downloads/)
- **Git** - Download from [git-scm.com](https://git-scm.com/)
- **CUDA-compatible GPU** (optional but recommended for better performance)

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/mahdimtd/persian-plate-recognition.git
cd persian-plate-recognition
```

### 2. Create Virtual Environment

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Linux/MacOS:
source venv/bin/activate

# On Windows:
venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Download Pre-trained Models

Download the pre-trained model weights from the repository releases/assets and place them in the `weights/` directory:

```
weights/
├── vehicle_detection.pth
├── plate_detection.pth
└── persian_ocr.pth
```

## Running the System

### Basic Usage

```bash
python detect.py --source test_images/
```

### Custom Input

```bash
# Process a single image
python detect.py --source path/to/your/image.jpg

# Process a video
python detect.py --source path/to/your/video.mp4

# Process a directory of images
python detect.py --source path/to/your/directory/
```

### Advanced Options

```bash
python detect.py \
    --source input.jpg \
    --weights weights/model.pth \
    --conf-threshold 0.7 \
    --output results/
```

## Command Line Arguments

| Argument | Description | Default | Example |
|----------|-------------|---------|---------|
| `--source` | Input path (image/video/directory) | `test_images/` | `--source video.mp4` |
| `--weights` | Model weights path | `weights/` | `--weights custom_weights/` |
| `--conf-threshold` | Confidence threshold (0-1) | `0.5` | `--conf-threshold 0.7` |
| `--output` | Output directory | `results/` | `--output my_results/` |

## Input Formats Supported

- **Images**: `.jpg`, `.jpeg`, `.png`, `.bmp`
- **Videos**: `.mp4`, `.avi`, `.mov`, `.mkv`
- **Directory**: Process all supported files in a directory

## Output

The system will generate the following outputs in the specified output directory:

- **Annotated Images/Videos**: Original input with bounding boxes and recognized Persian text
- **Text Files**: Detection results with coordinates and recognized plate numbers
- **Console Output**: Real-time processing information

### Example Output Structure

```
results/
├── input_processed.jpg          # Annotated image
├── input.txt                    # Detection results
└── processing_log.txt           # Processing details
```

## Performance Tips

1. **GPU Acceleration**: For faster processing, ensure you have CUDA installed and a compatible GPU
2. **Batch Processing**: Process multiple images by pointing to a directory
3. **Confidence Threshold**: Adjust `--conf-threshold` based on your accuracy requirements
4. **Model Weights**: Ensure you're using the latest pre-trained weights for best performance

## Troubleshooting

### Common Issues

1. **Missing Dependencies**: Make sure all requirements are installed
   ```bash
   pip install -r requirements.txt
   ```

2. **Model Weights Not Found**: Download weights from repository releases
   ```bash
   # Check if weights directory exists
   ls weights/
   ```

3. **CUDA Issues**: Install appropriate PyTorch version for your CUDA version
   ```bash
   # Check CUDA version
   nvidia-smi
   ```

4. **Permission Errors**: Ensure you have write permissions to the output directory

### Getting Help

If you encounter issues:

1. Check the console output for error messages
2. Verify all prerequisites are installed
3. Ensure input files exist and are in supported formats
4. Check that model weights are properly downloaded

## System Requirements

- **RAM**: Minimum 8GB (16GB recommended)
- **Storage**: At least 5GB free space for models and processing
- **GPU**: CUDA-compatible GPU with 4GB+ VRAM (optional but recommended)

## Docker Support (Optional)

If Docker is available, you can also run the system in a containerized environment:

```bash
# Build Docker image
docker build -t persian-plate-recognition .

# Run container
docker run -v /path/to/input:/app/input -v /path/to/output:/app/output persian-plate-recognition
```

*Note: Docker configuration may require additional setup depending on your system.*
✅​ Video Processing: Processes input videos and generates annotated output

✅​ Persian Text Rendering: Proper bidirectional text support for Persian characters



