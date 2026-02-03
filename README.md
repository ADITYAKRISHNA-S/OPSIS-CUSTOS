# VID-TRUST 🛡️

**AI-Powered Deepfake Detection & Explainability Engine**

> **Hackathon MVP Edition**  
> _Trusted Verification for the Generative AI Era._

---

## 🔴 The Problem

The rapid rise of Generative AI has flooded social media with hyper-realistic deepfakes. Misinformation, financial scams, and identity theft are scaling faster than human verification can handle. Existing tools are complex, slow, and "black boxes"—they give a score but don't explain _why_ content is fake, leading to low user trust.

## 🎯 Our Solution: VID-TRUST

VID-TRUST is a specialized, lightweight tool designed for **transparency**. It doesn't just catch deepfakes; it **visually explains** the manipulation.

### Key Features

- **Real-Time Analysis**: Processes short clips (5-15s) in seconds.
- **Visual Evidence**: Generates a **Heatmap Overlay** showing exactly where the AI manipulated the face.
- **Human-Readable Reports**: Translates complex ML confidence scores into simple bullet points (e.g., "Irregular eye blinking", "Lip-sync mismatch").
- **Reliable Demo**: Fallback mechanisms ensure the system _never_ crashes during a live pitch.

## 🛠️ Tech Stack

- **Frontend**: HTML5, CSS3 (Glassmorphism), Vanilla JavaScript
- **Backend**: Python 3.9, Flask (REST API)
- **Computer Vision**: OpenCV (Frame extraction, Face detection)
- **ML/AI**: PyTorch (Model architecture), Grad-CAM (Simulated for Demo Stability)

---

## 🚀 Setup Instructions

### Prerequisites

- Python 3.9+ installed
- pip installed

### 1. Installation

Clone the repo and install dependencies:

```bash
cd vid-trust/backend
pip install -r requirements.txt
```

### 2. Run the Backend

Start the flask server:

```bash
python app.py
```

_Server will start at http://127.0.0.1:5000_

### 3. Launch the Frontend

Simply go to the `vid-trust/frontend` folder and double-click `index.html` to open it in your browser.
_(Alternatively, you can serve it, but the app is configured to allow local file access via CORS)_.

---

## 🧪 How the Demo Works

1. **Upload**: User selects a video file (MP4).
2. **Pre-Processing**: Backend extracts the first 10 frames using OpenCV.
3. **Inference**:
   - The system scans for facial artifacts.
   - _Note: For this MVP, we use a robust simulation module to ensure 100% demo uptime without downloading 500MB+ weights._
4. **Explainability**:
   - Generates a heat-map overlay on the face.
   - Maps the confidence score to pre-defined linguistic patterns.
5. **Result**: User sees a "Suspicious" or "Safe" badge, a heatmap, and a reason list.

## ⚠️ Limitations (MVP)

- **Model Size**: Deepfake models are heavy; this MVP uses lightweight/simulated inference for speed.
- **Audio**: Currently analyzes visual frames only, not audio spectrum (voice cloning).
- **Scale**: Designed for single-user demos, not concurrent production loads.

## 🔮 Future Scope

- **Audio-Visual Fusion**: Check for Lip-Sync inconsistencies using Wav2Lip.
- **Blockchain Verification**: Hash verified videos to a public ledger (c2pa compatibility).
- **Browser Extension**: Real-time overlay for WhatsApp/Telegram Web.

---

**Built with ❤️ for a Safer Internet.**
