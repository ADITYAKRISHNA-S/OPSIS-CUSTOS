# How to Train VID-TRUST Model (MesoNet)

> **Updated for MesoNet (Meso4) Architecture**

This project now uses **MesoNet**, a lightweight convolutional network specifically designed for deepfake detection.

## 1. Prepare Your Dataset

Ensure your FaceForensics++ folders are organized. The script expects:

```
dataset_root/
├── original/
│   └── (videos here)
├── Deepfakes/
│   └── (videos here)
├── Face2Face/
│   └── (videos here)
...
```

## 2. Update Path in `train.py`

Open `backend/train.py` and edit line 15:

```python
DATASET_ROOT = "path/to/faceforensics_plus_plus"
```

Change this to the actual absolute path to your dataset.

## 3. Run Training

In your terminal (inside `vid-trust/backend`):

```bash
python train.py
```

This will:

1. Scan your folders.
2. Train the **Meso4** model from scratch (since we don't have pre-trained weights).
3. Save the result as `mesonet_weights.pth`.

## 4. Use the Real Model

The app effectively "looks" for the file `backend/mesonet_weights.pth`.

- If found: **Real AI Mode** (MesoNet) is activated.
- If missing: **Demo Simulation Mode** is used.

## 5. Pre-Trained Weights?

Since we are implementing the architecture from scratch, we don't have the official author's weights loaded.
You must run `python train.py` on your dataset to create the weights file!
