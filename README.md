# Bachelor Thesis - IU GitHub Repository

**Course: Bachelor Thesis — B.Sc. Applied Artificial Intelligence**

**IU International University of Applied Sciences**

---

## Overview

This repository contains all code, data, and survey materials for the bachelor thesis:

**Thesis Title: A Comparative Study of Large Language Models for Financial Sentiment Analysis and Their Predictive Potential for Short-Term Stock Price Movement**

This study compares four large language models on financial sentiment classification and tests whether the extracted sentiment signals relate to short-term stock price movement. Two computational experiments are conducted along with an online practitioner survey of market participants, finance and AI professionals.

---

## Experiments

**Experiment 1 — Sentiment Classification Benchmarking**

All four models are evaluated on the Financial PhraseBank dataset (sentences_50agree, 4,846 sentences) under identical zero-shot conditions. Performance is measured using accuracy, macro precision, recall, and F1-score.

**Experiment 2 — Directional Stock Price Prediction**

Sentiment signals extracted from 1,000 FNSPID financial news headlines across 10 companies are compared against actual next-day stock price movement. The period covered is January 2018 to June 2020. Historical closing prices are sourced from Yahoo Finance using the yfinance library.

---

## Models

| Model | Developer | Parameters | Type |
|---|---|---|---|
| FinBERT (ProsusAI/finbert) | ProsusAI | 110M | Domain-specific |
| Llama 3 8B Instruct | Meta | 8B | General-purpose |
| Mistral 7B Instruct v0.3 | Mistral AI | 7B | General-purpose |
| Gemma 3 4B Instruct | Google DeepMind | 4B | General-purpose |

All models are open-source and accessed via Hugging Face.

General-purpose LLMs are loaded with 4-bit NF4 quantization.

All experiments are run on Google Colab free tier (Tesla T4 GPU, 16GB RAM).

---

## Repository Structure

```
llm-financial-sentiment/
│
├── README.md
├── NOTEBOOK_LINKS.md
│
├── /notebooks
│   ├── exp1_dataset_preparation_financialphrasebank.ipynb
│   ├── exp1_a_finbert.ipynb
│   ├── exp1_b_llama3.ipynb
│   ├── exp1_c_mistral.ipynb
│   ├── exp1_d_gemma3.ipynb
│   ├── exp2_dataset_preparation_fnspid.ipynb
│   ├── exp2_a_finbert.ipynb
│   ├── exp2_b_llama3.ipynb
│   ├── exp2_c_mistral.ipynb
│   └── exp2_d_gemma3.ipynb
│
├── /notebook_outputs_pdf
│   ├── exp1_dataset_preparation_financialphrasebank.pdf
│   ├── exp1_a_finbert.pdf
│   ├── exp1_b_llama3.pdf
│   ├── exp1_c_mistral.pdf
│   ├── exp1_d_gemma3.pdf
│   ├── exp2_dataset_preparation_fnspid.pdf
│   ├── exp2_a_finbert.pdf
│   ├── exp2_b_llama3.pdf
│   ├── exp2_c_mistral.pdf
│   └── exp2_d_gemma3.pdf
│
├── /data
│   ├── exp1_results_finbert.csv
│   ├── exp1_results_llama3.csv
│   ├── exp1_results_mistral.csv
│   ├── exp1_results_gemma3.csv
│   ├── exp2_headlines_1000.csv
│   ├── exp2_results_finbert.csv
│   ├── exp2_results_llama3.csv
│   ├── exp2_results_mistral.csv
│   └── exp2_results_gemma3.csv
│
└── /survey
    ├── survey_responses.xlsx
    └── survey_summary.pdf
```

---

## Notebooks

| Notebook | Description |
|---|---|
| exp1_dataset_preparation_financialphrasebank.ipynb | Dataset loading and preparation for Experiment 1 |
| exp1_a_finbert.ipynb | Experiment 1 — FinBERT on Financial PhraseBank |
| exp1_b_llama3.ipynb | Experiment 1 — Llama 3 8B on Financial PhraseBank |
| exp1_c_mistral.ipynb | Experiment 1 — Mistral 7B on Financial PhraseBank |
| exp1_d_gemma3.ipynb | Experiment 1 — Gemma 3 4B on Financial PhraseBank |
| exp2_dataset_preparation_fnspid.ipynb | Dataset sampling and preparation for Experiment 2 |
| exp2_a_finbert.ipynb | Experiment 2 — FinBERT directional prediction |
| exp2_b_llama3.ipynb | Experiment 2 — Llama 3 8B directional prediction |
| exp2_c_mistral.ipynb | Experiment 2 — Mistral 7B directional prediction |
| exp2_d_gemma3.ipynb | Experiment 2 — Gemma 3 4B directional prediction |

### Note on Notebook Rendering

Google Colab notebooks saved with widget state metadata cannot be rendered directly on GitHub. When such notebooks are uploaded without modification, GitHub displays an "Invalid Notebook" error caused by a missing `state` key in the widget metadata.

Due to this issue, the notebooks in the `/notebooks` folder have had their outputs cleared before upload. This removes the problematic metadata while keeping all code cells intact. Anyone who wants to run the notebooks can open them directly in Google Colab, enable a GPU runtime, and run all cells to reproduce the results.

**For those who want to view the full experiment runs without re-running the code, two alternatives are provided:**

- The `/notebook_outputs_pdf` folder contains PDF exports of all ten notebooks as they were executed for this thesis, including all code, outputs, charts, and evaluation metrics.
- The direct Google Colab links in the table below and in [NOTEBOOK_LINKS.md](./NOTEBOOK_LINKS.md) open the original shared notebooks with all outputs visible.

### Google Colab Links — Full Output Notebooks

| Notebook | Description | Colab Link |
|---|---|---|
| exp1_dataset_preparation_financialphrasebank | Dataset preparation for Experiment 1 | [Open in Colab](https://colab.research.google.com/drive/1M_nApnksBpY_zvnXMlbz8_nsM3TAijxs?usp=sharing) |
| exp1_a_finbert | Experiment 1 — FinBERT | [Open in Colab](https://colab.research.google.com/drive/1dfgHAXbiGf1CqGDu8VMNJU3rpbpnPjUu?usp=sharing) |
| exp1_b_llama3 | Experiment 1 — Llama 3 8B | [Open in Colab](https://colab.research.google.com/drive/18Mg2Mc7aFWhxoDeYa6vswRr5iuysLcx6?usp=sharing) |
| exp1_c_mistral | Experiment 1 — Mistral 7B | [Open in Colab](https://colab.research.google.com/drive/1wT6N9Ba0gw8xpp_Mz1KWmxegqpJR1PGp?usp=sharing) |
| exp1_d_gemma3 | Experiment 1 — Gemma 3 4B | [Open in Colab](https://colab.research.google.com/drive/1f03gP6V7zIEmWJWBo9G-VWAiyopG_XFd?usp=sharing) |
| exp2_dataset_preparation_fnspid | Dataset preparation for Experiment 2 | [Open in Colab](https://colab.research.google.com/drive/1D_Wtk4B5_YGh4miqXm4gDu_Q6ipeEuD2?usp=sharing) |
| exp2_a_finbert | Experiment 2 — FinBERT | [Open in Colab](https://colab.research.google.com/drive/1Tm4_wqesIR4b13owTNqNSvH5IV5eeWoT?usp=sharing) |
| exp2_b_llama3 | Experiment 2 — Llama 3 8B | [Open in Colab](https://colab.research.google.com/drive/1N22SZIAInjV0tArJ02Zk1MX8X6JrU5l2?usp=sharing) |
| exp2_c_mistral | Experiment 2 — Mistral 7B | [Open in Colab](https://colab.research.google.com/drive/146zrXmPtK1M1obpN9i8_I28fPNYVOrQr?usp=sharing) |
| exp2_d_gemma3 | Experiment 2 — Gemma 3 4B | [Open in Colab](https://colab.research.google.com/drive/13P_KW6r76qZcLiSqFrei9DJvJgHmM7J9?usp=sharing) |

The same links are also available in [NOTEBOOK_LINKS.md](./NOTEBOOK_LINKS.md).

---

## Data

> **Note:** Some CSV files in this folder are large and may not render directly in the GitHub file viewer. To view all files, download the full repository as a ZIP file by clicking the green **Code** button on the repository homepage and select **Download ZIP**.

| File | Description |
|---|---|
| exp1_results_finbert.csv | FinBERT predictions for Experiment 1 |
| exp1_results_llama3.csv | Llama 3 8B predictions for Experiment 1 |
| exp1_results_mistral.csv | Mistral 7B predictions for Experiment 1 |
| exp1_results_gemma3.csv | Gemma 3 4B predictions for Experiment 1 |
| exp2_headlines_1000.csv | 1,000 sampled FNSPID headlines with binary movement labels |
| exp2_results_finbert.csv | FinBERT sentiment & directional predictions for Experiment 2 |
| exp2_results_llama3.csv | Llama 3 8B sentiment & directional predictions for Experiment 2 |
| exp2_results_mistral.csv | Mistral 7B sentiment & directional predictions for Experiment 2 |
| exp2_results_gemma3.csv | Gemma 3 4B sentiment & directional predictions for Experiment 2 |

---

## Datasets Used

**Financial PhraseBank (sentences_50agree)**

4,846 labelled sentences from financial news articles — used in Experiment 1

https://huggingface.co/datasets/takala/financial_phrasebank

**FNSPID Financial News Dataset**

15.7 million+ financial news records linked to S&P 500 companies

https://huggingface.co/datasets/Zihan1004/FNSPID/blob/main/Stock_news/All_external.csv

**Yahoo Finance (via yfinance)**

Historical daily closing prices for 10 selected companies

https://github.com/ranaroussi/yfinance

---

## Key Results

### Experiment 1 — Sentiment Classification (Financial PhraseBank)

| Model | Accuracy | Precision | Recall | Macro F1 |
|---|---|---|---|---|
| FinBERT | 88.96% | 0.8584 | 0.9163 | 0.8825 |
| Gemma 3 4B | 81.39% | 0.7898 | 0.8315 | 0.8081 |
| Mistral 7B | 79.61% | 0.8039 | 0.7845 | 0.7934 |
| Llama 3 8B | 78.25% | 0.7867 | 0.7375 | 0.7585 |

### Experiment 2 — Directional Price Prediction (FNSPID, 1,000 headlines)

| Model | Directional Accuracy | Macro F1 |
|---|---|---|
| Llama 3 8B | 50.00% | 0.4961 |
| Gemma 3 4B | 49.00% | 0.4894 |
| FinBERT | 48.80% | 0.4878 |
| Mistral 7B | 48.70% | 0.4750 |

All four models perform at random chance level, consistent with the Efficient Market Hypothesis (Fama, 1970).

---

## Survey

The practitioner survey titled *The Use of Large Language Models in Financial Sentiment Analysis: A Practitioner Survey* collected 33 responses from retail investors, finance professionals, and AI and data science professionals.

Raw response data and the Microsoft Forms summary report are available in the /survey folder.

---

## How to Reproduce

### Experiment 1

1. Open any exp1 notebook in Google Colab
2. Add a Hugging Face API Key
3. Enable GPU runtime — go to Runtime → Change runtime type → T4 GPU
4. Run all cells from top to bottom
5. The Financial PhraseBank dataset & LLM Models loads via Hugging Face

### Experiment 2

1. Upload `exp2_headlines_1000.csv` to your Google Drive
2. Update the file path variable in the notebook to match your Drive location
3. Open the relevant exp2 notebook in Google Colab
4. Add a Hugging Face API Key
5. Enable GPU runtime and run all cells

---

## Requirements

All notebooks run on Google Colab with no local installation required.

Key libraries used:

`transformers` `bitsandbytes` `datasets` `pandas` `scikit-learn` `yfinance` `torch`

---

## Author

Siddharthsinh Rathod

Thesis Title: A Comparative Study of Large Language Models for Financial Sentiment Analysis and Their Predictive Potential for Short-Term Stock Price Movement

Bachelor Thesis — B.Sc. Applied Artificial Intelligence

Thesis Supervisor: Prof. Dr. Sameer Joshi

IU International University of Applied Sciences

March-May 2026
