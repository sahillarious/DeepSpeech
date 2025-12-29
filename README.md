# DeepSpeech Therapy: Real-Time Speech Assessment & Feedback 🗣️🤖

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/Framework-PyTorch-EE4C2C.svg)](https://pytorch.org/)
[![Gradio](https://img.shields.io/badge/UI-Gradio-orange.svg)](https://gradio.app/)

A hierarchical deep learning framework designed for real-time speech therapy. This system evaluates spoken input to detect speech defects using autoencoders and transformers, providing personalized corrective feedback via a GPT-4 integration.

---

## 📌 Project Objectives
* **Speech Clarity Check:** A 1D convolutional autoencoder model built to distinguish between "clear" and "faulty" speech patterns.
* **Stutter Detection:** Identifying speech impairments like stuttering and categorizing them into multiclass events (Block, Prolongation, Repetition, etc.).
* **Interactive Feedback:** Utilizing LLMs to provide natural language suggestions on how to improve articulation and fluency.
* **Gamified Practice:** A simple, interactive setup that allows users to practice speaking anytime with real-time assessment.

---

## 🛠️ Technical Architecture

### 1. Speech Clarity Detection
* **Model:** 1D Convolutional Autoencoder.
* **Dataset:** LibriSpeech (train-clean-100 subset).
* **Logic:** The model learns to reconstruct MFCC features. Speech is flagged as "faulty" if the reconstruction error exceeds a dynamic threshold (0.0279) set at the 95th percentile of training errors.
* **Accuracy:** Achieved a validation accuracy of **96.89%**.

### 2. Multi-class Stuttering Diagnosis
* **Dataset:** SEP-28k (approximately 32,000 audio clips).
* **Models Explored:**
    * **CNN + Attention:** Designed to capture long-range temporal dependencies in spectrograms.
    * **Conv1D Autoencoder + Transformer:** Combines latent embeddings with sequence modeling to detect subtle disfluency patterns.
    * **ResNet18:** Leveraged for robust feature extraction via transfer learning.
* **Results:** The Transformer-based architecture demonstrated superior performance in identifying disfluent segments with high recall.

### 3. LLM-based Virtual Coach
* **Integration:** GPT-4 is used to interpret the context of speech errors and generate context-aware, constructive suggestions.
* **Deployment:** Hosted on **Gradio**, providing a user-friendly dashboard for recording, diagnosis, and feedback.

---

## 📊 Performance Summary

| Component | Metric | Result |
| :--- | :--- | :--- |
| **Speech Clarity Detection** | Accuracy | **96.89%** |
| **Faulty Articulation Diagnosis** | Accuracy | **96.0%** |
| **Stuttering Diagnosis** | F1-Score | **0.67 - 0.70** |

---

## 🚀 Future Roadmap
* **Scale Up:** Expanding the pipeline to cover clinical disorders such as **Dysarthria, Apraxia, and Dementia**.
* **Fine-Tuning:** Implementing domain-specific fine-tuning for state-of-the-art models like Wav2Vec2.
* **Gamification:** Introducing a reward system where users earn points for achieving target clarity and fluency levels.

---

## 👥 Contributors
* **Sahil Shivaji Sawant** - Model building (Autoencoders, Transformers), Training, and Evaluation.
* **Fagun Nirag Patel** - Dataset collection, LLM integration, and Gradio deployment.

*Developed at the University at Buffalo.*
