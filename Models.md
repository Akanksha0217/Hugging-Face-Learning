# 🤗 Day 4: Hugging Face Models

---

## 📌 What is a Model?

A **model** is a trained AI system that learns patterns from data.

👉 It takes input data and gives predictions/output.

Example:

* Input: "I love AI"
* Output: Positive sentiment

---

## 🧠 Simple Flow

```text id="8z6x7n"
Text → Tokenizer → Model → Output
```

Example:

```text id="l7s2qv"
"Hello" → [101, 7592, 102] → Model → Prediction
```

---

## 🔹 Why Models are Important?

Models are the **brain** of AI.

They perform tasks like:

* Text classification
* Text generation
* Translation
* Question answering
* Summarization

---

## 🔹 Types of Models

---

## 1. Encoder Models

Example:

* BERT
* RoBERTa
* DistilBERT

### Used for:

* Classification
* Sentiment analysis
* Named Entity Recognition

### How they work:


Example:

```text id="h1v6u4"
I love AI
```

Model understands complete sentence.

---

## 2. Decoder Models

Example:

* GPT
* GPT-2
* LLaMA

### Used for:

* Text generation
* Chatbots
* Story writing

### How they work:

* Predict next word step by step

Example:

```text id="3e2p1w"
Once upon a time...
```

Generates continuation.

---

## 3. Encoder-Decoder Models

Example:

* T5
* BART

### Used for:

* Translation
* Summarization

### How they work:

* Encoder reads input
* Decoder generates output

Example:

```text id="n4y7g8"
English → French
```

---

## 🔹 Load a Pretrained Model

```python id="model1"
from transformers import AutoModel

model = AutoModel.from_pretrained("bert-base-uncased")
print(model)
```

---

## 🔹 Load Model for Specific Task

### Sentiment Analysis

```python id="model2"
from transformers import AutoModelForSequenceClassification

model = AutoModelForSequenceClassification.from_pretrained(
    "bert-base-uncased"
)
```

---

## 🔹 Common Auto Classes

| Class                              | Use             |
| ---------------------------------- | --------------- |
| AutoModel                          | Base model      |
| AutoTokenizer                      | Tokenizer       |
| AutoModelForSequenceClassification | Classification  |
| AutoModelForCausalLM               | Text generation |
| AutoModelForQuestionAnswering      | QA              |

---

## 🔹 Example: Tokenizer + Model

```python id="model3"
from transformers import AutoTokenizer, AutoModel

tokenizer = AutoTokenizer.from_pretrained("bert-base-uncased")
model = AutoModel.from_pretrained("bert-base-uncased")

inputs = tokenizer("Hello world", return_tensors="pt")
outputs = model(**inputs)

print(outputs)
```

---

## 🔹 Model Output

Usually returns:

* Hidden states
* Logits
* Predictions

---

## 🔹 Popular Models

| Model      | Use              |
| ---------- | ---------------- |
| BERT       | Classification   |
| GPT-2      | Generation       |
| T5         | Multiple tasks   |
| BART       | Summarization    |
| DistilBERT | Lightweight BERT |

---

## 🔹 Save Model

```python id="model4"
model.save_pretrained("my_model")
```

---

## 🔹 Load Saved Model

```python id="model5"
model = AutoModel.from_pretrained("my_model")
```

---


## ⚠️ Important Notes

* Always match tokenizer + model
* Example:

  * BERT tokenizer → BERT model

---

## 🧠 Pro Tip

Pipeline = Easy way
Model + Tokenizer = More control

---

## ⭐ Summary

* Model = AI brain
* Tokenizer converts text
* Model processes tokens

Flow:

```text id="r2k8m1"
Input → Tokenizer → Model → Output
```

---

## 📅 Tomorrow Plan (Day 5)

* Datasets
* Fine-tuning basics

---

## 🚀 Goal

Understand how Hugging Face models work internally
