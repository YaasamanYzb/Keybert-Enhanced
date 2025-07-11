# Keyphrase Extraction with Enhanced KeyBERT 🔍✨

This project investigates and enhances [KeyBERT](https://github.com/MaartenGr/KeyBERT) for unsupervised keyphrase extraction. We explore how lightweight yet effective improvements—such as diversity control via MaxSum and embedding upgrades using MPNet—impact the quality of extracted keyphrases across short (SemEval-2010 Task 8) and long (Inspec) text domains.

---

## 🚀 Key Features

- Use of **MaxSum-based diversity** to minimize redundancy and improve semantic variety.
- Evaluation based on **partial string matching** to reflect real-world phrase similarity.
- Embedding model upgrade to **all-mpnet-base-v2** for richer semantic representations.
- Comparative analysis across two diverse datasets: short relation-focused and long academic abstracts.
- Full performance evaluation with **precision, recall, and F1-score** metrics.

---

## 📊 Datasets

### SemEval-2010 Task 8
- Contains 8,000 training samples and 2,717 test samples.
- Sentences are annotated with two target entities per instance.
- Short, syntactically clean text ideal for evaluating precision on entity-focused extraction.
- Can be loaded from Hugging Face via:
  `from datasets import load_dataset`

### Inspec Dataset
- Consists of scientific abstracts annotated with gold-standard keyphrases.
- Texts are longer and more domain-specific than SemEval.
- Designed to evaluate the generalizability of keyphrase extraction systems in technical contexts.

---

## 🧠 Project Structure

```
keybert-enhanced/
├── notebooks/
│   ├── baseline_keybert.ipynb
│   ├── extension_maxsum.ipynb
│   └── extension_maxsum_mpnet.ipynb
├── report/
│   └── keybert_project_report.pdf
├── requirements.txt
├── README.md
```

---

## 📓 Notebooks

| Notebook                     | Description                                                  |
|-----------------------------|--------------------------------------------------------------|
| `baseline_keybert.ipynb`    | Keyphrase extraction using default KeyBERT with strict evaluation. |
| `extension_maxsum.ipynb`    | Applies MaxSum to promote diversity in selected phrases.     |
| `extension_maxsum_mpnet.ipynb` | Combines MaxSum with an MPNet embedding upgrade.           |

---

## 📈 Results Summary

| Dataset         | Configuration         | Precision | Recall | F1 Score |
|----------------|------------------------|-----------|--------|----------|
| SemEval (Test) | Baseline               | 0.216     | 0.321  | 0.238    |
| SemEval (Test) | + MaxSum               | 0.544     | 0.544  | 0.544    |
| SemEval (Test) | + MaxSum + MPNet       | 0.529     | 0.529  | 0.529    |
| Inspec (Test)  | Baseline               | 0.216     | 0.321  | 0.238    |
| Inspec (Test)  | + MaxSum               | 0.286     | 0.411  | 0.311    |
| Inspec (Test)  | + MaxSum + MPNet       | 0.295     | 0.425  | 0.321    |

---

## 🛠️ Setup & Installation

Clone the repository:

```bash
git clone https://github.com/your-username/keybert-enhanced.git
cd keybert-enhanced
```

(Optional) Create a virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## 📄 Report

You can find the detailed project write-up here:

📎 `report/keybert_project_report.pdf`

It includes methodology, experimental setup, evaluation examples, and final conclusions.

---

## 🔬 Future Work

- Incorporate MMR (Maximum Marginal Relevance) and compare it with MaxSum.
- Test on additional datasets like KPTimes or DUC2001.
- Experiment with transformer models such as RoBERTa or DistilBERT.
- Apply domain-adaptive finetuning for embeddings.
- Explore supervised refinement of the unsupervised extraction results.

---

## 🤝 Contributions

Contributions and suggestions are welcome! Please open an issue or fork the repository and submit a pull request.

---

## 📜 License

This project is licensed under the MIT License.
