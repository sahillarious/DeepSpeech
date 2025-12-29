# DeepSpeech Therapy: Real-Time Speech Assessment & Feedback 🗣️🤖

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/Framework-PyTorch-EE4C2C.svg)](https://pytorch.org/)
[![Gradio](https://img.shields.io/badge/UI-Gradio-orange.svg)](https://gradio.app/)

Deep Learning based speech-language therapy system jo users ki pronunciation aur fluency ko real-time mein evaluate karta hai. Ye system autoencoders aur transformers ka use karke speech defects detect karta hai aur GPT-4 ke zariye personalized corrective feedback deta hai.

---

## 📌 Project Objectives
* **Speech Clarity Check:** Ek convolutional autoencoder model jo "clear" aur "faulty" speech ke beech farak kar sake.
* **Stutter Detection:** Speech impairments jaise stuttering ko identify karna aur unhe multiclass (Block, Prolongation, Repetition, etc.) mein categorize karna.
* **Interactive Feedback:** LLM ka use karke user ko natural language mein samjhana ki wo apni articulation kaise sudharein.
* **Gamified Learning:** Ek aisa platform banana jahan users interactive exercises ke zariye apni bolne ki shamta behtar kar sakein.

---

## 🛠️ Technical Architecture

### 1. Speech Clarity Detection
* **Model:** 1D Convolutional Autoencoder.
* **Dataset:** LibriSpeech (train-clean-100).
* **Logic:** Model MFCC features ko reconstruct karta hai. Agar reconstruction error dynamic threshold (0.0279) se zyada hota hai, toh speech ko "faulty" flag kiya jata hai.
* **Accuracy:** Validation accuracy **96.89%** achieve ki gayi.

### 2. Multi-class Stuttering Diagnosis
* **Dataset:** SEP-28k (32,000 audio clips).
* **Models Explored:** * **CNN + Attention:** Long-range temporal dependencies ko capture karne ke liye.
    * **Conv1D Autoencoder + Transformer:** Latent embeddings aur sequence modeling ke liye.
    * **ResNet18:** Transfer learning ke zariye feature extraction ke liye.
* **Best Result:** Transformer-based model ne stuttered speech identify karne mein **0.702 F1-score** dikhaya.

### 3. LLM-based Virtual Coach
* **Integration:** GPT-4 API ka use karke context-aware suggestions generate kiye jate hain.
* **Deployment:** **Gradio** interface ke zariye user-friendly dashboard banaya gaya hai jahan log apni voice record karke turant assessment paa sakte hain.

---

## 📊 Model Performance

| Component | Metric | Result |
| :--- | :--- | :--- |
| **Clarity Detection** | Accuracy | **96.89%** |
| **Stuttering Diagnosis** | F1-Score | **0.67 - 0.70** |
| **Acoustic Recognition** | Accuracy | **96.0%** |

---

## 🚀 Future Roadmap
* **Scale Up:** Pipeline ko clinical disorders jaise **Dysarthria, Apraxia, aur Dementia** tak expand karna.
* **Fine-Tuning:** Wav2Vec2 jaise pretrained models ka domain-specific training badhana.
* **Gamification:** Correct pronunciation par points dene wala reward system implement karna.

---

## 👥 Contributors
* **Sahil Shivaji Sawant** - Model building (Autoencoders, Transformers), Training & Evaluation.
* **Fagun Nirag Patel** - Dataset collection, LLM integration, ResNet/CRNN models.

*University at Buffalo - Deep Learning Project.*
