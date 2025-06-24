# 🧠 TextSentimentClassifierV1

A multi-task learning model that classifies **sentiment**, and predicts **stress** and **anxiety levels** from **long-form diary entries**, fine-tuned on emotion-rich datasets. This project blends NLP and mental health insights to analyze unstructured text using Transformers.

---

## 📌 Features

- 💬 **Accepts full diary entries or journal-style reflections**
- 🧠 **Performs multi-task classification**:
  - Sentiment: Positive / Neutral / Negative
  - Stress Level: Continuous score [0.0–1.0]
  - Anxiety Level: Continuous score [0.0–1.0]
- 🛠️ Fine-tuned using:
  - [GoEmotions](https://huggingface.co/datasets/go_emotions) (from Google)
  - [Journal Entries with Labelled Emotions](https://www.kaggle.com/datasets/madhavmalhotra/journal-entries-with-labelled-emotions)
- 📈 Ready to evaluate or integrate into mental health apps or journaling tools

---

## 🗂️ Dataset Sources

### 1. GoEmotions (Google Research)
- 58k Reddit comments labeled with 27 emotions
- Used for base training and stress/anxiety heuristics

### 2. Journal Entries with Labeled Emotions (Kaggle)
- 1,500 personal diary-style texts with fine-grained emotion tags
- Used for fine-tuning sentiment prediction on long-form mental health writing

---

## 🧪 Model Architecture

This project uses a **DistilBERT** backbone fine-tuned using a **multi-head architecture**:

```text
[Input Text] ─▶ [DistilBERT Encoder]
                    ├──▶ Sentiment Classification Head (3 classes)
                    ├──▶ Stress Regressor Head (1 value)
                    └──▶ Anxiety Regressor Head (1 value)
