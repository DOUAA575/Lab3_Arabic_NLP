# Lab3_Arabic_NLP
# Arabic NLP Project: Text Classification and Text Generation

## Project Overview

This project explores Natural Language Processing (NLP) techniques for Arabic text using deep learning and Transformer architectures.

It is divided into two main parts:

- **Part 1:** Arabic Text Classification using recurrent neural networks.
- **Part 2:** Arabic Text Generation using a pre-trained GPT-2 model.

The experiments were implemented using Python, PyTorch and Hugging Face Transformers in Kaggle notebooks.

---

## Part 1: Arabic Text Classification

### Objective

The objective is to classify Arabic texts into three categories:

| Label | Category |
|---|---|
| 0 | General topics |
| 1 | Digital technology |
| 2 | Artificial intelligence |

### Dataset

The dataset contains 34 examples:

- 4 real Arabic news articles.
- 30 synthetic educational examples.

The dataset is relatively small and is intended for educational experimentation.

### Preprocessing

The following preprocessing operations were performed:

- Arabic text normalization.
- Removal of diacritics and Tatweel.
- Arabic tokenization.
- Stopword removal.
- Stemming using ISRIStemmer.
- Vocabulary construction.
- Text encoding and padding.

### Models

Four recurrent neural network architectures were implemented and compared:

- RNN
- Bidirectional RNN (BiRNN)
- GRU
- LSTM

### Evaluation Results

| Model | Accuracy | Macro F1-score |
|---|---:|---:|
| RNN | 45.45% | 0.4444 |
| BiRNN | 36.36% | 0.3556 |
| GRU | 63.64% | 0.6202 |
| LSTM | 81.82% | 0.8130 |

LSTM achieved the best results on the test set.

**Limitation:** The test set contains only 11 examples. Therefore, these results are preliminary and do not demonstrate reliable generalization to unseen real-world articles.

---

## Part 2: Arabic Text Generation with GPT-2

### Objective

The objective is to fine-tune a pre-trained Arabic GPT-2 model on the dataset from Part 1 and generate new Arabic paragraphs from a given input sentence.

### Pre-trained Model

- Model: `aubmindlab/aragpt2-base`
- Architecture: GPT-2 (Transformer, autoregressive language model)
- Framework: Hugging Face Transformers and PyTorch.

### Dataset Preparation

The same dataset from Part 1 is reused.

The original Arabic titles and texts are combined into training examples. The normalized and stemmed classification data are not used for generation, in order to preserve natural Arabic language.

### Fine-tuning

The model is fine-tuned on the custom Arabic corpus using:

- Tokenization.
- Padding and truncation.
- PyTorch Dataset.
- Causal language modeling.
- Hugging Face Trainer.

### Text Generation

After fine-tuning, the model generates a paragraph based on a given Arabic prompt.

Example prompt:

`الذكاء الاصطناعي أصبح من أهم التقنيات الحديثة`

The generated continuation is evaluated qualitatively in terms of coherence, fluency, relevance and repetition.

**Limitation:** The dataset is small and contains synthetic examples. Generated texts may be repetitive or inaccurate.

---

## Technologies Used

- Python
- PyTorch
- TensorFlow-free deep learning workflow
- Hugging Face Transformers
- NLTK
- CAMeL Tools
- Pandas
- NumPy
- Scikit-learn
- Kaggle Notebooks
- Git and GitHub

---



## How to Run

1. Open the notebooks using Kaggle or Jupyter Notebook.
2. Install the required dependencies.
3. Load the dataset.
4. Execute the cells in order.
5. For Part 2, use a GPU if available for GPT-2 fine-tuning.

---


## Conclusion

This project demonstrates two important NLP tasks for Arabic language processing: text classification and text generation. The first part compares recurrent neural network architectures, while the second part explores Transformer fine-tuning using AraGPT2.
