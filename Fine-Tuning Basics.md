# 🤗 Fine-Tuning Basics

---

## 📌 What is Fine-Tuning?

**Fine-tuning** means training a pre-trained model on your own dataset for a specific task.

👉 Instead of training from scratch:

* Use an already trained model
* Train it a little more on your data

---

## 🧠 Example

Pretrained model:

* Knows general English language

Fine-tuned model:

* Learns movie sentiment analysis

Example:

```text id="ft1"
Pretrained BERT + Movie Reviews = Sentiment Model
```

---

## 🔹 Why Fine-Tuning?

Training from scratch is:

* Expensive 💰
* Slow ⏳
* Needs huge data 📊

Fine-tuning is:

* Faster ⚡
* Cheaper ✅
* Better for beginners

---

## 🔧 Required Libraries

```bash id="ft2"
pip install transformers datasets evaluate
```

---

## 🔹 Steps in Fine-Tuning

1. Load dataset
2. Load tokenizer
3. Tokenize dataset
4. Load model
5. Train model
6. Evaluate

---

## 1. Load Dataset

```python id="ft3"
from datasets import load_dataset

dataset = load_dataset("imdb")
```

---

## 2. Load Tokenizer

```python id="ft4"
from transformers import AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained(
    "bert-base-uncased"
)
```

---

## 3. Tokenize Dataset

```python id="ft5"
def tokenize_function(example):
    return tokenizer(
        example["text"],
        padding="max_length",
        truncation=True
    )

tokenized_data = dataset.map(tokenize_function)
```

---

## 4. Load Model

```python id="ft6"
from transformers import AutoModelForSequenceClassification

model = AutoModelForSequenceClassification.from_pretrained(
    "bert-base-uncased",
    num_labels=2
)
```

---

## 5. Training Arguments

```python id="ft7"
from transformers import TrainingArguments

training_args = TrainingArguments(
    output_dir="./results",
    evaluation_strategy="epoch",
    num_train_epochs=1
)
```

---

## 6. Trainer

```python id="ft8"
from transformers import Trainer

trainer = Trainer(
    model=model,
    args=training_args,
    train_dataset=tokenized_data["train"],
    eval_dataset=tokenized_data["test"]
)
```

---

## 7. Train Model

```python id="ft9"
trainer.train()
```

---

## 8. Evaluate Model

```python id="ft10"
trainer.evaluate()
```

---

## 🔹 Save Fine-Tuned Model

```python id="ft11"
model.save_pretrained("my_finetuned_model")
tokenizer.save_pretrained("my_finetuned_model")
```

---

## 🔹 Load Saved Model

```python id="ft12"
from transformers import pipeline

classifier = pipeline(
    "sentiment-analysis",
    model="my_finetuned_model"
)
```

---

## 📌 Real Use Cases

Fine-tuning is used for:

* Resume screening
* Chatbots
* Spam detection
* Sentiment analysis
* Medical text classification

---

## 🎯 Practice Tasks

1. Fine-tune BERT on imdb
2. Change epochs
3. Try your own dataset

---

## ⚠️ Important Notes

* Fine-tuning can take time
* GPU is helpful
* Start with small datasets

---

## 🧠 Pro Tip

Pretrained model = base knowledge
Fine-tuning = specialization

Example:

```text id="ft13"
Doctor after MBBS → Specialization
```

Same concept 😄

---

## ⭐ Summary

Fine-tuning process:

```text id="ft14"
Dataset → Tokenizer → Model → Train → Evaluate
```

---

