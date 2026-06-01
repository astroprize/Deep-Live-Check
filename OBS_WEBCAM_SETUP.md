# Live Webcam Setup with OBS

Stream your face-swapped video as a virtual webcam or to the web.

## Prerequisites

- Deep Live Check running in Live mode
- OBS installed (`brew install obs`)

## Option 1: Virtual Webcam (For Video Calls)

Use a virtual camera to appear in Zoom, Teams, Discord, etc.

### Setup

1. **Start Deep Live Check Live mode**
   ```bash
   source venv/bin/activate
   python3.11 run.py --execution-provider coreml
   ```
   Click the **"Live"** button in the GUI.

2. **Open OBS**
   ```bash
   open /Applications/OBS.app
   ```

3. **Add Deep Live Check as a source**
   - Click **"+"** under Sources (bottom left)
   - Select **"Window Capture"**
   - Choose **"Deep Live Check"** from the dropdown
   - Click OK

4. **Start Virtual Camera**
   - Go to **Tools → Start Virtual Camera**
   - A red recording indicator will appear

5. **Use in your app**
   - Open Zoom, Google Meet, Teams, Discord, etc.
   - Go to **Settings → Camera/Video**
   - Select **"OBS Virtual Camera"**
   - Your face-swapped video now appears!

### Fixing Mirror/Flip Issue

If the Deep Live Check header appears backward:

1. Right-click the source in OBS
2. Select **"Transform" → "Flip Horizontally"**
3. Preview will now be correct

---

## Option 2: Web Browser Stream (OBS.Ninja)

Share your stream link so others can watch in any browser.

### Setup

1. **Capture in OBS** (same as Option 1, steps 1-3)

2. **Get a stream link**
   - Go to https://obs.ninja
   - Click "Start Streaming"
   - Follow the prompts
   - Get a shareable link

3. **Share the link**
   - Give the link to anyone
   - They can watch in their browser
   - No download needed

### Advantages
- No local setup needed for viewers
- Works on any device/browser
- Free, no server required

---

## Option 3: Stream to Twitch/YouTube Live

Broadcast to a wider audience.

### Setup

1. **Get streaming credentials**
   - Twitch: Get your Stream Key from Creator Dashboard
   - YouTube: Go to Youtube.com/live and get RTMP details

2. **In OBS:**
   - Go to **Settings → Stream**
   - Set Service to **"Twitch"** or **"Custom RTMP Server"**
   - Paste your Stream Key
   - Click OK

3. **Start streaming**
   - Click **"Start Streaming"** in OBS
   - Share your stream link with viewers

---

## Troubleshooting

### Virtual camera not showing in browser
- Restart the browser
- Restart OBS
- Make sure "Start Virtual Camera" is active (red indicator visible)

### Face looks backward/mirrored
- Use OBS Transform → Flip Horizontally (see above)
- Or check Deep Live Check settings for mirror option

### OBS not capturing the window
- Make sure Deep Live Check window is on screen
- Try closing and reopening OBS
- Select the correct window in Window Capture dropdown

### Performance issues
- Reduce resolution in OBS settings
- Lower frame rate (30 fps instead of 60)
- Close other applications

---

## Tips

- **Best lighting**: Good lighting helps face detection work better
- **Position**: Keep your face centered in the webcam
- **Bandwidth**: OBS.Ninja works best on same network; for remote streaming use Twitch/YouTube
- **Recording**: In OBS, you can also record locally while streaming
