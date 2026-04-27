# Tokenizers in Hugging Face

---

## 📌 What is a Tokenizer?

A **tokenizer** converts text into numbers so that a model can understand it.

👉 Because:

* Machines don’t understand text ❌
* Machines understand numbers ✅

---

## 🧠 Example

Text:

```
Hello world
```

After tokenization:

```
["Hello", "world"] → [101, 7592, 2088, 102]
```

---

## 🔹 Why Tokenizers are Important?

* Convert text → tokens → IDs
* Required before giving input to model
* Ensures model understands input correctly

---

## 🔹 Types of Tokenization

### 1. Word Tokenization

```
"I love AI" → ["I", "love", "AI"]
```

---

### 2. Subword Tokenization (Most Used 🔥)

```
"playing" → ["play", "##ing"]
```

👉 Used in models like BERT

---

### 3. Character Tokenization

```
"AI" → ["A", "I"]
```

---

## 🔧 Using Tokenizer in Hugging Face

### ✅ Example

```python id="tok1"
from transformers import AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained("bert-base-uncased")

result = tokenizer("Hello world")
print(result)
```

---

## 📌 Output Explanation

```python
{
 'input_ids': [101, 7592, 2088, 102],
 'token_type_ids': [0, 0, 0, 0],
 'attention_mask': [1, 1, 1, 1]
}
```

### 🔹 input_ids

* Numeric representation of words

### 🔹 token_type_ids

* Used in sentence pairs

### 🔹 attention_mask

* Tells model which tokens to focus on

---

## 🔹 Convert Back (Decode)

```python id="tok2"
text = tokenizer.decode([101, 7592, 2088, 102])
print(text)
```

---

## 🔹 Special Tokens

| Token | Meaning           |
| ----- | ----------------- |
| [CLS] | Start of sentence |
| [SEP] | Separator         |
| [PAD] | Padding           |
| [UNK] | Unknown word      |

---

## 🔹 Padding & Truncation

```python id="tok3"
tokenizer(
    "Hello world",
    padding=True,
    truncation=True,
    max_length=10
)
```




Understand how text is converted before going into AI model 🚀
