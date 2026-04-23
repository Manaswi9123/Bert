# Bert
# 🤖 State-of-the-Art NLP: BERT with TensorFlow Hub

Traditional NLP models read text in a linear fashion (left-to-right or right-to-left). This repository implements **BERT**, a transformer-based model that reads entire sequences of words at once, allowing it to learn the full context of a word based on all of its surroundings.

---

## 🛠️ The Transformer Stack
* **Framework:** TensorFlow & Keras
* **Model Source:** TensorFlow Hub (`bert_en_uncased`)
* **Preprocessing:** `tensorflow_text` (BERT-specific tokenization)
* **Architecture:** Transformer Encoder blocks with Multi-Head Attention.

---

## 🧠 Key Concepts Implemented

### 1. BERT Preprocessing
BERT requires a specific input format consisting of three main parts, which I implemented using the `hub.KerasLayer`:
* **Input Word IDs:** Unique integers representing each token.
* **Input Mask:** To help the model ignore "padding" tokens.
* **Input Type IDs:** Used to distinguish between different sentences.

### 2. Contextual Embeddings
I extracted the two primary outputs of the BERT model to show how it "thinks":
* **Pooled Output:** A single vector ($768$ dimensions) representing the **entire sentence**. This is perfect for tasks like Sentiment Analysis.
* **Sequence Output:** Individual vectors for **every word** in the sentence. This is used for tasks like Named Entity Recognition (NER) or Question Answering.



### 3. Sentence Similarity
By comparing the vector outputs of different sentences, I demonstrated how BERT recognizes semantic meaning:
* **Experiment:** Comparing "I love grapes" with "I love oranges."
* **Observation:** BERT identifies high similarity between these sentences because it understands the shared context of "fruit" and "preference," even though the words are different.

---

## 📈 Why use BERT?
* **Bidirectionality:** It looks at the words both before and after a target word simultaneously.
* **Transfer Learning:** I utilized a pre-trained "base" model, meaning it already understands the English language perfectly; we only need to "fine-tune" it for specific tasks.
* **No More Polysemy Issues:** BERT easily handles words with multiple meanings based on the surrounding sentence structure.

---

## 🚀 How to Run

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/Manaswi9123/Python-DataScience-Fundamentals.git](https://github.com/Manaswi9123/Python-DataScience-Fundamentals.git)

2. **Install Dependencies:**
       pip install tensorflow tensorflow-hub tensorflow-text

3. **Execute:** Open BERT.ipynb in Google Colab or Jupyter to see the transformer in action.
