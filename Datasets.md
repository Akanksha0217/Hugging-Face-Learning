# 🤗 Hugging Face Datasets
---

## 📌 What is a Dataset?

A **dataset** is a collection of data used to:

* Train models
* Test models
* Evaluate performance

Examples:

* Text
* Images
* Audio

---

## 🧠 Example

Dataset for sentiment analysis:

| Text      | Label    |
| --------- | -------- |
| I love AI | Positive |
| Bad movie | Negative |

👉 Model learns from this data.

---

## 🔹 Why Datasets are Important?

Datasets help models learn patterns.

Without data:

* No training ❌
* No predictions ❌

---

## 🔧 Install Datasets Library

```bash id="d1"
pip install datasets
```

---

## 🔹 Load Dataset

```python id="d2"
from datasets import load_dataset

dataset = load_dataset("imdb")
print(dataset)
```

---

## 📌 Output

```python id="d3"
DatasetDict({
    train: Dataset(...)
    test: Dataset(...)
})
```

---

## 🔹 Access Data

```python id="d4"
print(dataset["train"][0])
```

Example output:

```python id="d5"
{
    'text': 'Amazing movie',
    'label': 1
}
```

---

## 🔹 Dataset Splits

Usually datasets have:

* train → model learns
* test → model evaluation
* validation → tuning

Example:

```text id="d6"
train = practice
test = exam
validation = mock test
```

---

## 🔹 Dataset Features

```python id="d7"
print(dataset["train"].features)
```

Shows:

* columns
* labels
* data types

---

## 🔹 Select Few Rows

```python id="d8"
small_data = dataset["train"].select(range(5))
print(small_data)
```

---

## 🔹 Shuffle Dataset

```python id="d9"
dataset = dataset.shuffle(seed=42)
```

---

## 🔹 Filter Dataset

```python id="d10"
filtered = dataset["train"].filter(
    lambda x: x["label"] == 1
)
```

---

## 🔹 Map Function

Apply transformation to dataset.

```python id="d11"
def lowercase(example):
    example["text"] = example["text"].lower()
    return example

dataset = dataset.map(lowercase)
```

---

## 🔹 Train-Test Split

```python id="d12"
split = dataset["train"].train_test_split(test_size=0.2)
```

---

## 🔹 Load Custom CSV

```python id="d13"
dataset = load_dataset("csv", data_files="data.csv")
```

---

## 🔹 Save Dataset

```python id="d14"
dataset.save_to_disk("saved_dataset")
```

---

## 🔹 Load Saved Dataset

```python id="d15"
from datasets import load_from_disk

dataset = load_from_disk("saved_dataset")
```

---

## 📚 Popular Datasets

| Dataset | Use                 |
| ------- | ------------------- |
| imdb    | Sentiment analysis  |
| squad   | Question answering  |
| ag_news | News classification |
| mnist   | Image recognition   |

---

## 🎯 Practice Tasks

1. Load imdb dataset
2. Print first 5 rows
3. Shuffle data
4. Filter positive reviews

---

## ⚠️ Important Notes

Large datasets may take time to download.

---

## 🧠 Pro Tip

Good model + bad dataset = bad results ❌

Good dataset = better performance ✅

---

## ⭐ Summary

Dataset = Training data for models

Common steps:

```text id="d16"
Load → Explore → Clean → Train
```

---

