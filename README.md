#  Biomedical Named Entity Recognition (BINER-based)

##  Overview
This project implements a **Biomedical Named Entity Recognition (NER)** system using deep learning techniques. The model is inspired by the **BINER architecture**, which focuses on achieving high performance with **low computational cost**.

The system extracts meaningful biomedical entities such as:
-  Diseases
-  Drugs
-  Genes / Proteins
-  Clinical terms

from unstructured medical text.

---

##  Problem Statement
Biomedical NLP faces two major challenges:
1. **High computational requirements** of models like BERT/BioBERT
2. **Domain-specific complexity** (medical jargon, abbreviations, noisy data)

This project addresses these by building an efficient **BiLSTM + CRF-based NER model**.

---

##  Dataset
- Source: MACCROBAT2018 Dataset
- Format: Converted into **BIO tagging scheme**
- Split:
  - Train: 70%
  - Validation: 10%
  - Test: 20%

Example:diabetes B-Disease
        insulin B-Drug


---

## Methodology

### 🔹 Workflow
1. Data Preprocessing
2. Tokenization & Vocabulary Building
3. Feature Engineering
4. Model Training
5. Evaluation
6. Prediction System

---

### 🔹 Model Architecture

Embedding Layer
↓
Bidirectional LSTM (BiLSTM)
↓
Conditional Random Field (CRF)


#### Key Components:
- **Word Embeddings** (Word2Vec / GloVe)
- **Character-level embeddings** (for medical terms)
- **BiLSTM** → captures context (forward + backward)
- **CRF Layer** → ensures valid tag sequences

---

##  Advanced Architectures Explored
- Base BINER
-  Parallel BINER (best performing)
-  Sequential BINER

---

##  Evaluation Metrics
We use standard NER metrics:

- **Precision**
- **Recall**
- **F1-Score (Primary metric)**

F1 = 2 × (Precision × Recall) / (Precision + Recall)


---

## Training Details

| Parameter        | Value Range       |
|----------------|------------------|
| Epochs         | 50 – 100         |
| Learning Rate  | 0.0001 – 0.001   |
| Batch Size     | 8 – 64           |
| Hidden Size    | 100 – 500        |
| Dropout        | 0.2 – 0.5        |

---

##  Results
- Improved entity detection accuracy using **BiLSTM + CRF**
- Character embeddings enhanced performance on complex medical terms
- Parallel architecture showed better generalization

---

## How to Run

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 3️⃣ Train the Model
```bash
python train.py
```

### 4️⃣ Evaluate
```bash
python evaluate.py
```

### 5️⃣ Predict
```bash
python predict.py
```


### Project Structure

├── data/
├── preprocessing/
├── models/
├── training/
├── evaluation/
├── app/
├── requirements.txt
└── README.md

### Applications
- Clinical text analysis
- Electronic Health Records (EHR) processing
- Drug and disease extraction
- Medical research automation

### Future Work
- Integrate BioBERT / ClinicalBERT
- Improve performance using Transformer-based models
- Deploy as a web application (Streamlit/Flask)
- Extend to relation extraction

### Contributers
- Ananthan S
- Aleena Antony
- Drisya Krishna K V
- Athulya Mannambath

### References
- BINER: Biomedical Named Entity Recognition (2022)
- BiLSTM-CRF for Sequence Labeling
- BioBERT (Biomedical Language Representation Model)

### Acknowledgment

This project is developed as part of an NLP Capstone Project focusing on biomedical text mining.
