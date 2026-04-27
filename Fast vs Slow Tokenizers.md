# ⚡ Fast vs Slow Tokenizers in Hugging Face

---

## 📌 What are Fast and Slow Tokenizers?

Hugging Face provides **two types of tokenizers**:

* 🐢 **Slow Tokenizers** → Written in Python
* ⚡ **Fast Tokenizers** → Written in Rust (very fast)

---

## 🔹 Slow Tokenizers

### ✅ Features:

* Easy to understand
* Pure Python implementation
* More flexible for debugging

### ❌ Limitations:

* Slower performance
* Not optimized for large data

---

## 🔹 Fast Tokenizers

### ✅ Features:

* Very fast (Rust-based)
* Optimized for performance
* Can handle large datasets efficiently

### 🔥 Extra Feature:

* Return **offset mapping** (position of words in original text)

---

## 🧠 Example

```python id="fastslow1"
from transformers import AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained("bert-base-uncased")

print(type(tokenizer))
```

👉 Output:

* `<class 'transformers.models.bert.tokenization_bert_fast.BertTokenizerFast'>`

---

## 🔹 Force Slow Tokenizer

```python id="fastslow2"
tokenizer = AutoTokenizer.from_pretrained(
    "bert-base-uncased",
    use_fast=False
)
```

---

## 🔹 Check if Tokenizer is Fast

```python id="fastslow3"
print(tokenizer.is_fast)
```

---

## ⚡ Speed Comparison

| Feature        | Slow 🐢   | Fast ⚡ |
| -------------- | --------- | ------ |
| Speed          | Low       | High   |
| Language       | Python    | Rust   |
| Offset Mapping | ❌         | ✅      |
| Large Data     | Not ideal | Best   |

---

## 🎯 When to Use What?

### ✅ Use Fast Tokenizer:

* Large datasets
* Production apps
* Real-time systems

### ✅ Use Slow Tokenizer:

* Debugging
* Learning internals

---
