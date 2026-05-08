# Drowsiness Detection System

An AI-powered real-time drowsiness detection system using computer vision, facial landmark analysis, voice interaction, and gesture activation.

## Features

- Real-time eye closure detection using EAR (Eye Aspect Ratio)
- Yawn detection using MAR (Mouth Aspect Ratio)
- Head pose estimation for head-down detection
- PERCLOS fatigue monitoring
- Voice-controlled startup system
- Hand gesture activation (open palm detection)
- Audio alert system with multiple alert levels
- Personalized calibration mode
- Real-time visual monitoring dashboard

---

## Technologies Used

- Python
- OpenCV
- MediaPipe
- NumPy
- SciPy
- SpeechRecognition
- Pygame Mixer
- Threading

---

## Detection Methods

### 1. Eye Closure Detection
The system calculates the Eye Aspect Ratio (EAR) from facial landmarks to determine whether the user's eyes are closed for a prolonged duration.

### 2. Yawn Detection
Mouth Aspect Ratio (MAR) is used to identify yawning behavior as an early sign of drowsiness.

### 3. Head Pose Estimation
Using MediaPipe Face Mesh and solvePnP, the system estimates head pitch rotation to detect head-down conditions.

### 4. PERCLOS Monitoring
PERCLOS (Percentage of Eye Closure) is calculated over a rolling window to measure fatigue level.

---

## Alert Levels

| Level | Condition | Alert |
|---|---|---|
| Tier 1 | Yawning | Yawn audio warning |
| Tier 2 | Eyes closed | Continuous alert sound |
| Tier 3 | Head down + eyes closed | Critical emergency alert |

---

# How to Run

## 1. Clone the Repository

```bash
git clone https://github.com/fadyanm/drowsiness-derection.git
cd drowsiness-derection
```

---

## 2. Create Virtual Environment (Recommended)

### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

---

## 3. Install Required Libraries

```bash
pip install -r requirements.txt
```

If `requirements.txt` is unavailable:

```bash
pip install opencv-python mediapipe numpy scipy pygame SpeechRecognition pyaudio
```

---

## 4. Prepare Audio Files

Make sure all required audio files are placed inside the `audio/` folder:

```bash
audio/
├── drowsiness_assistant.mp3
├── not_understand.mp3
├── alert.wav
├── critical_alert.wav
├── yawn_alert.mp3
├── normal_monitoring.mp3
├── alright.mp3
└── shutting_down.mp3
```

---

## 5. Run the Application

```bash
python main.py
```

---

## 6. Start Monitoring

You can activate the system by:

- Saying:
  - `"yes"`
  - `"start"`

OR

- Showing an open palm gesture to the webcam

---

## 7. Keyboard Controls

| Key | Action |
|---|---|
| `c` | Start calibration |
| `f` | Stop monitoring |
| `q` | Quit application |

---

## Notes

- Ensure your webcam and microphone are enabled.
- Use good lighting conditions for better face detection accuracy.
- Calibration is recommended before first use.
- If `PyAudio` installation fails on Windows:

```bash
pip install pipwin
pipwin install pyaudio
```