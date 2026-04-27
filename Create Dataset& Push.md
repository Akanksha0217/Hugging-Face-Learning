# 🤗 Create Dataset in Google Colab & Push to Hugging Face

---

## 📌 Goal

* Create your own dataset 📊
* Upload (push) it to Hugging Face Hub 🚀

---

## ⚙️ Step 1: Install Libraries (Colab)

```python
!pip install datasets huggingface_hub
```

---

## 🔑 Step 2: Login to Hugging Face

1. Go to: https://huggingface.co/settings/tokens
2. Create a token
3. Copy token

Now login in Colab:

```python
from huggingface_hub import login
login("YOUR_TOKEN_HERE")
```

---

## 📊 Step 3: Create Dataset

### Example: Simple Student Dataset

```python
from datasets import Dataset

data = {
    "name": ["Akanksha", "Rahul", "Sneha"],
    "age": [23, 24, 22],
    "course": ["AI", "CS", "IT"]
}

dataset = Dataset.from_dict(data)
print(dataset)
```

---

## 🔍 Step 4: Check Dataset

```python
dataset[0]
```

👉 Output:

```
{'name': 'Akanksha', 'age': 23, 'course': 'AI'}
```

---

## ☁️ Step 5: Push Dataset to Hugging Face

```python
dataset.push_to_hub("your-username/student-dataset")
```

👉 Replace:

* `your-username` with your Hugging Face username

---

## 🌐 Step 6: Check Your Dataset

Go to:
👉 https://huggingface.co/datasets

You will see your dataset there 🎉

---

## 📁 Optional: Create Dataset from CSV

```python
from datasets import load_dataset

dataset = load_dataset("csv", data_files="students.csv")
```

---

## 🎯 What You Learned

* Create dataset using Python
* Login to Hugging Face
* Upload dataset to Hub

---

