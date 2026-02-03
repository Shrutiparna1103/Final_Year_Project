# Toxifilter – Real-Time Toxic Content Filtering System

## Project Context
This project was developed as my **Final Year Undergraduate Academic Project**.
The objective was to design and evaluate a **real-time system for detecting and filtering toxic and sexual text content** at the keyboard-input level, focusing on low-latency and offline execution.

I was responsible for the system design, model integration, experimentation, evaluation, and documentation as part of the academic requirements.

---

## Overview
Toxifilter is a real-time AI-based text sanitization system that detects and filters toxic and sexual content as users type.
It combines **rule-based techniques**, **fuzzy matching**, and a **fine-tuned RoBERTa model** deployed via **ONNX Runtime** to deliver efficient, low-latency content moderation without requiring internet connectivity.

---

## Key Features
- Real-time keyboard input interception  
- Hybrid detection pipeline (rules + ML)  
- Obfuscation-aware fuzzy word matching  
- Context-aware toxicity classification  
- Offline inference using ONNX Runtime  
- Escalation-based enforcement (pass → warn → enforce)  
- Modular and extensible system design  

---

## System Architecture
**Processing Flow:**
1. Keyboard input capture  
2. Text preprocessing and normalization  
3. Exact and fuzzy toxic word matching  
4. RoBERTa-based ML inference  
5. Escalation decision logic  
6. Text sanitization and enforcement  

---

## My Contributions
- Designed the end-to-end system architecture  
- Implemented rule-based and fuzzy matching pipelines  
- Integrated and optimized a RoBERTa-based NLP model  
- Converted and deployed the model using ONNX Runtime  
- Conducted experiments and evaluated performance metrics  
- Documented results, limitations, and findings for academic review  

---

## Tech Stack
- Python 3.11  
- PyTorch  
- Hugging Face Transformers (RoBERTa)  
- ONNX Runtime  
- pynput  
- NumPy, Regex  

---

## Project Structure
toxifilter/
├── src/
│ ├── main.py
│ ├── keyboard_hook.py
│ ├── text_sanitizer.py
│ ├── preprocess.py
│ ├── word_match.py
│ ├── fuzzy_match.py
│ ├── sentence_model.py
│ ├── escalation.py
│ ├── data_loader.py
│ ├── eval.py
│ └── demo_sanitize.py
│
├── models/
│ ├── exports/
│ │ ├── model.onnx
│ │ └── model_traced.pt
│ └── roberta_saved/
│
├── data/
│ ├── raw/
│ ├── merged/
│ └── processed/
│
├── config.yaml
├── requirements.txt
└── README.md


---

## Dataset
The model was trained on a merged dataset (~51,000 samples), including:
- Jigsaw Toxic Comment Dataset  
- OLID (Offensive Language Identification Dataset)  
- Custom sexual content dataset  

Class imbalance was addressed using class-weighted training techniques.

---

## Installation
```bash
pip install -r requirements.txt
Usage
python src/main.py
Note: Keyboard hooks may require administrator privileges and may be restricted in certain applications or environments.

Evaluation
python src/eval.py
The evaluation script generates:

Accuracy

Precision

Recall

F1-score

Limitations
Desktop platforms only

English language support

Elevated permissions may be required for keyboard interception

Academic Note
This project was developed strictly for academic and educational purposes.
It is based on publicly available datasets and open-source research.
Model architecture inspiration and datasets are appropriately credited, with
implementation, experimentation, and evaluation performed by me.
