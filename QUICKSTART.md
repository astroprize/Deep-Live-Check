# Quick Start Guide

## Clone and Setup (macOS Apple Silicon)

```bash
# 1. Clone the repo
git clone https://github.com/astroprize/Deep-Live-Check
cd Deep-Live-Check

# 2. Download pre-trained models (~600MB)
gh release download v1.0-models -D models/

# 3. Create virtual environment with Python 3.11
python3.11 -m venv venv
source venv/bin/activate

# 4. Install dependencies
pip install -r requirements.txt
```

## Run the App

```bash
# Activate virtual environment
source venv/bin/activate

# Start GUI
python3.11 run.py --execution-provider coreml

# Or run headless with specific files
python3.11 run.py -s source.jpg -t target.mp4 -o output.mp4 --execution-provider coreml
```

## If Python 3.11 is not installed

```bash
brew install python@3.11
brew install python-tk@3.11
```

## Notes

- **CoreML provider** routes inference to Apple Neural Engine (significantly faster than CPU)
- **First run**: App auto-downloads InsightFace `buffalo_l` detection model (~200MB)
- **Webcam mode**: Click "Live" in GUI, then use OBS to capture the preview window
