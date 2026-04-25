# 🤗 Day 1: Introduction to Hugging Face

---

## 📌 What is Hugging Face?

Hugging Face is an open-source AI platform that provides:

* Pre-trained Machine Learning models
* Tools to build and train models
* A hub to share models and datasets

👉 It is mainly used for:

* Natural Language Processing (NLP)
* Computer Vision
* Audio Processing
* Multimodal AI

---

## 🚀 Why Hugging Face is Popular?

* 100,000+ pre-trained models available
* Easy to use (even for beginners)
* Works with PyTorch & TensorFlow
* Strong open-source community

---

## 🧠 What are Transformers?

Transformers are deep learning models used for understanding and generating text.

👉 Examples:

* BERT
* GPT
* T5

They are the core of Hugging Face.

---

## 📦 Key Components of Hugging Face

### 🔹 1. Transformers

* Main library
* Provides pre-trained models

### 🔹 2. Datasets

* Ready-to-use datasets
* Easy to load and preprocess

### 🔹 3. Tokenizers

* Convert text → numbers (tokens)
* Required before feeding data to model

### 🔹 4. Model Hub

* Collection of all models
* You can search and use models easily

---

## ⚙️ Installation

```bash
pip install transformers datasets
```

---

## ⚡ First Simple Example

```python
from transformers import pipeline

classifier = pipeline("sentiment-analysis")

result = classifier("I love learning Hugging Face!")
print(result)
```

👉 Output:

* POSITIVE or NEGATIVE sentiment

---

## 🎯 What  Learned Today

* What is Hugging Face
* Why it is important
* Basic components
* How to install
* First simple example

---


## ⭐ Your Goal

Build AI projects using Hugging Face 🚀
