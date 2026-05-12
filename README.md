# BERT-FineTuned-IMDB-Sentiment-Classifier

BERT Sentiment Analysis - IMDB 🎬

Fine-tuned BERT-base-uncased on IMDB movie reviews. 
Accuracy: 92.26% ✅ (binary positive/negative).

📁 Contents:
- E_BERT_Sentiment_Analysis_Project.ipynb : Full notebook
- requirements.txt : dependencies

🚀 Quick Start:
1. Clone repo
   git clone https://github.com/ZaryabAhmad01/BERT-FineTuned-IMDB-Sentiment-Classifier.git


2. Install
   pip install -r requirements.txt
3. Run notebook
   jupyter notebook E_BERT_Sentiment_Analysis_Project.ipynb

🔮 Inference Example (Python):
----------------------------------------
from transformers import AutoTokenizer, AutoModelForSequenceClassification
import torch

tokenizer = AutoTokenizer.from_pretrained("./bert-sentiment-model")
model = AutoModelForSequenceClassification.from_pretrained("./bert-sentiment-model")

text = "This movie was fantastic!"
inputs = tokenizer(text, return_tensors="pt", truncation=True, padding=True)
pred = torch.argmax(model(**inputs).logits, dim=-1).item()
print("Positive" if pred == 1 else "Negative")
----------------------------------------

📊 Training Results:
Epoch 1: Train Loss 0.266, Val Loss 0.256, Accuracy 91.35%
Epoch 2: Train Loss 0.164, Val Loss 0.327, Accuracy 92.26%

☁️ Optional: Upload to Hugging Face Hub
----------------------------------------
model.push_to_hub("your-username/bert-imdb-sentiment")
tokenizer.push_to_hub("your-username/bert-imdb-sentiment")
----------------------------------------

📜 License: Apache 2.0 (BERT) + educational use.
