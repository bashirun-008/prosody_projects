Speech Prosody-Based Emotion Classifier (Prototype)
A prototype pipeline for classifying emotional tone in speech using prosodic audio features (pitch, pitch range, and energy).
Overview
This project demonstrates an end-to-end pipeline for audio-based emotion classification:
Extract prosodic features (mean pitch, pitch range, RMS energy) from audio using librosa
Train a Random Forest classifier to map these features to emotion categories (Happy/Excited, Neutral/Calm, Sad/Tired)
Run predictions on new audio samples
Current Status: Prototype
This is a proof-of-concept pipeline, not a production-ready emotion classifier. Important limitations:
Training data is synthetic. The classifier is trained on artificially generated feature distributions (numpy.random.normal) that approximate what "happy," "neutral," and "sad" speech might look like in pitch/energy space — not on features extracted from real, labeled emotional speech.
Sample audio isn't genuinely labeled. The demo audio clips are segments of a single instrumental trumpet recording, split into thirds and labeled for demonstration purposes only — not actual emotional speech recordings.
Reported accuracy is not meaningful. The 100% accuracy reflects the classifier separating cleanly-generated synthetic clusters, not real-world classification performance.
What This Demonstrates
Audio feature extraction (pitch tracking, energy/RMS analysis) using librosa
Building a full classification pipeline: feature extraction → model training → inference
Working with scikit-learn's Random Forest classifier
Handling user-uploaded audio for live predictions (Colab file upload integration)
Tech Stack
Python
librosa (audio feature extraction)
scikit-learn (Random Forest classifier)
NumPy
Next Steps
To turn this into a genuine emotion classifier:
Replace synthetic training data with a real labeled speech-emotion dataset (e.g., RAVDESS or CREMA-D)
Extract the same prosodic features from real labeled audio samples
Retrain and validate on a proper train/test split of real data
Evaluate with a confusion matrix and per-class metrics, not just overall accuracy
How to Run
Open prosody_project1.ipynb in Google Colab
Run all cells in order
Upload your own .wav or .mp3 file when prompted to see a live prediction
Author
Md Bashirun Sultana
