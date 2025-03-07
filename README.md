# **Japanese Politeness Classification with LINE DistilBERT**

### **Overview**

This project implements a Japanese politeness classification model using LINE DistilBERT, a distilled version of BERT optimized for Japanese text. The model classifies sentences into polite, neutral, or impolite categories, leveraging a pre-trained transformer for efficient and accurate classification.
___
### **Dataset**

* Polite & Impolite Sentences (4000 total): Extracted from the KeiCo corpus, where all sentences are pre-labeled based on politeness levels.
(https://aclanthology.org/2022.dclrl-1.3/)

* Neutral Sentences (2000 total): Collected from Japanese Wikipedia, manually filtered to remove non-sentence lines like noun phrases and mathematical formulas.

* The dataset was split into 80% training, 10% validation, and 10% test sets.
___
### **Model**

The project employs LINE DistilBERT (line-corporation/line-distilbert-base-japanese) for sequence classification. This model was selected for two key reasons:

* Efficiency - Since this is a solo project, computational resources are limited, and a distilled model offers a balance between performance and memory usage.

* Coverage - Unlike other Japanese distilled BERT models, LINE DistilBERT is pretrained on a diverse Japanese corpus, making it well-suited for handling different politeness registers.
___
### **Training & Results**

* Tokenizer & Preprocessing: The AutoTokenizer from transformers was used to tokenize sentences, truncating at the 95th percentile of sentence length to optimize for memory and efficiency.
  
* Fine-Tuning: The model was fine-tuned for politeness classification with a cross-entropy loss function.

**Performance Metrics:**

  Test Accuracy: 0.9783
  
  Validation Accuracy: 0.9833
  
  Training Loss (Epoch 3): 0.073

___
### **Dependencies**

The following Python libraries were used:

```bash
pip install transformers unidic_lite sentencepiece fugashi
```

___
### **Future Improvements**

* Further refinement of neutral sentence selection for improved balance.

* Exploration of contextual influences on politeness classification.

* Testing with alternative Japanese BERT-based models for comparison.
