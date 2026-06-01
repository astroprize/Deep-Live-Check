# Mac Setup Guide (Apple Silicon)

## Step 1 — Python 3.11

Python 3.11 is required. Newer versions (3.12+) have compatibility issues with some dependencies.

```bash
python3.11 --version
```

If not installed:
```bash
brew install python@3.11
brew install python-tk@3.11
```

## Step 2 — Create virtual environment and install dependencies

```bash
cd /Users/dparmar/Documents/Dev/Deep-Live-Check
python3.11 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

## Step 3 — Download models (~600MB total)

Place both files in the `models/` folder:

1. **inswapper_128_fp16.onnx** (face swap model)
   ```
   https://huggingface.co/hacksider/deep-live-cam/resolve/main/inswapper_128_fp16.onnx?download=true
   ```

2. **GFPGANv1.4.pth** (face enhancement model)
   ```
   https://github.com/TencentARC/GFPGAN/releases/download/v1.3.4/GFPGANv1.4.pth
   ```

## Step 4 — Run the app

```bash
source venv/bin/activate
python3.11 run.py --execution-provider coreml
```

This opens the Tkinter GUI. For headless/CLI mode, add `-s source.jpg -t target.mp4 -o output.mp4`.

## Notes

- CoreML provider routes inference to Apple Neural Engine — significantly faster than CPU
- The app auto-downloads the InsightFace `buffalo_l` detection model on first run (~200MB)
- For webcam mode: click "Live" in the GUI, then use OBS to capture the preview window
