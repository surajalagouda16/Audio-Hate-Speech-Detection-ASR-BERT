# Cascaded ASR–Transformer Framework for Audio-Based Hate Speech Detection

## Overview

This repository contains the implementation, experimental results, and supporting resources for the research work:

**"Cascaded ASR–Transformer Framework for Audio-Based Hate Speech Detection"**

The proposed framework addresses the challenge of detecting hate and offensive speech from audio content by combining Automatic Speech Recognition (ASR) with a transformer-based language model. The system utilizes OpenAI's Whisper model to convert speech into text and a fine-tuned BERT classifier to identify hateful or offensive content.

---

## Motivation

With the rapid growth of social media and audio-based communication platforms, harmful speech is no longer restricted to textual content. Detecting hate speech directly from spoken audio remains challenging due to the limited availability of annotated audio datasets, speech variability, and transcription errors.

This work proposes a cascaded approach that separates speech recognition from semantic understanding, enabling robust hate speech detection using modern ASR and transformer technologies.

---

## Proposed Architecture

The complete framework consists of four major stages:

1. Audio Input
2. Whisper ASR Transcription
3. BERT Tokenization and Embedding Generation
4. Transformer-Based Classification

### Processing Pipeline

Audio → Whisper ASR → Text Transcript → BERT Tokenizer → Transformer Encoder → Classification Layer → Prediction

---

## Dataset Generation

Due to the lack of large-scale audio hate speech datasets, a custom spoken-audio dataset was created using the HateXplain corpus.

### Dataset Creation Pipeline

* Text extraction from HateXplain
* Text cleaning and normalization
* Speech synthesis using Google Text-to-Speech (gTTS)
* Audio validation and filtering
* Dataset balancing and labeling

### Dataset Statistics

| Class | Category         | Samples |
| ----- | ---------------- | ------: |
| 0     | Normal           |    2332 |
| 1     | Hate/Offensive   |    5768 |
| Total | Combined Dataset |    8100 |

Audio files were generated in MP3 format and validated to remove corrupted or silent samples.

---

## Model Configuration

### ASR Module

* Whisper Base Model

### Classification Module

* BERT Base Uncased
* 12 Transformer Encoder Layers
* 768-Dimensional Embeddings
* CLS Token Classification Head

### Training Parameters

| Parameter     | Value |
| ------------- | ----- |
| Optimizer     | AdamW |
| Learning Rate | 2e-5  |
| Epochs        | 5     |
| Batch Size    | 8     |
| Classes       | 2     |

---

## Experimental Results

### Classification Performance

| Metric            | Score  |
| ----------------- | ------ |
| Accuracy          | 83.59% |
| Weighted F1-Score | 0.84   |
| Macro F1-Score    | 0.77   |
| AUC Score         | 0.75   |

### Key Observations

* Stable convergence during fine-tuning
* Strong performance on ASR-generated transcripts
* Effective discrimination between normal and hate/offensive speech
* Competitive performance despite synthetic audio generation

---

## Repository Structure

```text
Audio-Hate-Speech-Detection-ASR-BERT/

├── README.md

├── Paper/
│   └── Published_Paper.pdf

├── Dataset/
│   ├── dataset_description.md
│   └── sample_audio_files/

├── Code/
│   ├── hate_speech_detection.ipynb
│   └── requirements.txt

├── Results/
│   ├── confusion_matrix.png
│   ├── accuracy_curve.png
│   ├── loss_curve.png
│   ├── roc_curve.png
│   └── classification_report.png

├── Architecture/
│   ├── architecture_diagram.png
│   └── dataset_pipeline.png

└── LICENSE
```

---

## Technologies Used

* Python
* PyTorch
* OpenAI Whisper
* Hugging Face Transformers
* BERT Base Uncased
* Scikit-Learn
* NumPy
* Pandas
* Matplotlib
* Seaborn
* gTTS

---

## Future Improvements

* Multilingual hate speech detection
* Integration of acoustic and textual features
* Real-world audio dataset collection
* Explainable AI techniques (SHAP/LIME)
* Real-time moderation deployment

---

## Citation

If you use this work in your research, please cite the associated publication.

```bibtex
@article{yourpaper2026,
  title={Cascaded ASR--Transformer Framework for Audio-Based Hate Speech Detection},
  author={Your Name},
  year={2026}
}
```

---

## Author

**Suraj A**

Electronics and Communication Engineering

Research Interests:

* Artificial Intelligence
* Machine Learning
* Natural Language Processing
* Speech Processing
* Analog IC Design

---
