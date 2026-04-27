#  Hugging Face Pipelines

---

## 📌 What is a Pipeline?

A **pipeline** is the easiest way to use AI models in Hugging Face.

👉 It handles everything:

* Model loading
* Tokenization
* Prediction

✅ You just give input → get output

---

## ⚡ Why Pipelines are Important?

* Beginner friendly
* No need to understand deep ML concepts
* Works in just a few lines of code

---

## 🔧 Installation

```bash
pip install transformers
```

---

## 🧠 Basic Syntax

```python
from transformers import pipeline

pipe = pipeline("task-name")
result = pipe("your input")
print(result)
```

---

## 🚀 Common Pipeline Tasks

---

### 🔹 1. Sentiment Analysis

```python
from transformers import pipeline

classifier = pipeline("sentiment-analysis")
result = classifier("I love learning AI")
print(result)
```

👉 Output:

* POSITIVE / NEGATIVE

---

### 🔹 2. Text Generation

```python
generator = pipeline("text-generation")

result = generator("Once upon a time", max_length=30)
print(result)
```

---

### 🔹 3. Translation

```python
translator = pipeline("translation_en_to_fr")

result = translator("Hello, how are you?")
print(result)
```

---

### 🔹 4. Summarization

```python
summarizer = pipeline("summarization")

text = "Long paragraph here..."
result = summarizer(text)
print(result)
```

---

### 🔹 5. Question Answering

```python
qa = pipeline("question-answering")

result = qa({
    "question": "What is AI?",
    "context": "AI is artificial intelligence."
})

print(result)
```

---
