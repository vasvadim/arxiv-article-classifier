<h1 align="center">📚 arXiv Article Classifier</h1>

<p align="center">
  A Streamlit app that predicts the arXiv subject area of a paper from its title (and, optionally, abstract) with a fine-tuned DistilBERT.<br/>
  Project for the <b>Yandex School of Data Analysis</b> machine-learning course, 2026.
</p>

<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white">
  <img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white">
  <img alt="Transformers" src="https://img.shields.io/badge/%F0%9F%A4%97%20Transformers-DistilBERT-FFD21E">
  <img alt="Streamlit" src="https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white">
</p>

## What it does

- **Input:** the paper title, plus the abstract if you have it (title and abstract are concatenated).
- **Model:** DistilBERT fine-tuned for sequence classification into five arXiv areas: *Computer Science, Mathematics, Physics, Quantitative Biology, Statistics*.
- **Output:** the smallest set of areas whose cumulative probability reaches **95 %**, each with its probability bar, so an interdisciplinary paper is shown with two or three areas instead of one forced label.

## Run locally

```bash
git clone https://github.com/vasvadim/ysda_article_classifier.git
cd ysda_article_classifier
pip install -r requirements.txt
streamlit run app.py
```

The fine-tuned checkpoint (`model.safetensors`, tokenizer and config) ships in `model/`, so no training or download step is needed.

## Repository

| Path | Contents |
|---|---|
| `app.py` | Streamlit UI and inference (tokenisation, softmax, 95 % cumulative-probability cut-off) |
| `model/` | fine-tuned DistilBERT: `config.json`, `model.safetensors`, `tokenizer.json`, `tokenizer_config.json` |
| `requirements.txt` | `streamlit`, `torch`, `transformers` |

---

<p align="center"><a href="https://github.com/vasvadim">Vadim Vasilenko</a></p>
