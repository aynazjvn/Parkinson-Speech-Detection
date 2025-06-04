**Detecting Parkinson's Disease from Speech with Deep Learning Architectures (X-vector, ECAPA-TDNN, Whisper, Wav2Vec2) 🧠**

## 🧾 Overview

This notebook demonstrates the detection of Parkinson’s disease from speech recordings using a variety of deep learning models. The goal is to differentiate between healthy individuals and those with PD using vocal biomarkers. Experiments were conducted on both original and augmented data to evaluate model robustness.

---

## 🚀 Models Used

| Model         | Feature Type | Notes |
|---------------|--------------|-------|
| **X-vector**  | MFCC         | Lightweight speaker embedding model |
| **ECAPA-TDNN**| Fbanks       | Robust SOTA speaker embedding model |
| **Wav2Vec2**  | Raw waveform | Self-supervised audio model (Facebook AI) |
| **Whisper**   | Raw waveform | ASR model adapted for PD classification |

---

## 🔬 Experimental Setup

- **Sample Rate:** 16 kHz
- **Task:** Binary classification (Parkinson’s / Healthy)
- **Data Augmentation:** Applied in augmented sets to test robustness
- **Evaluation Metrics:** Accuracy, Classification Error, Loss

---

## 📊 Results Summary

| Model                       | Dataset             | Valid Error (%) | Test Accuracy (%) | Test Error (%) | Test Loss |
|----------------------------|---------------------|------------------|-------------------|----------------|-----------|
| Xvector (MFCC)             | Original            | 1.22             | 100.00            | 0.00           | 0.0086    |
| Xvector (MFCC)             | Augmented           | 18.30            | 90.60             | 9.41           | 0.315     |
| ECAPA-TDNN (Fbank)         | Original            | 0.00             | 100.00            | 0.00           | 0.131     |
| ECAPA-TDNN (Fbank)         | Augmented           | 19.50            | 85.90             | 14.10          | 0.362     |
| Whisper                    | Original            | 3.70             | 95.30             | 4.70           | -         |
| Whisper                    | Augmented           | 29.40            | 70.60             | 29.40          | -         |

---

## 📈 Training Highlights

### Whisper (Original Data)

- 📉 Training loss decreased from 27.7 → 3.05
- ✅ Validation Accuracy improved from 67.1% → 97.6%
- 🎯 Final Test Accuracy: **95.3%**

### ECAPA-TDNN (Original Data)

- 🧠 Final Test Accuracy: **100%**
- 🔁 Model maintained strong generalization with no overfitting

---

## 🧪 How to Run

1. **Clone the repo**
   ```bash
   git clone https://github.com/ayanazjvn/parkinsons-detection-speech.git
   cd parkinsons-detection-speech
