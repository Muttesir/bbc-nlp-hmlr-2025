# HMLR 2025 Data Scientist Challenge

This project addresses the 2025 Data Scientist Challenge provided by HM Land Registry (HMLR). It leverages Natural Language Processing (NLP) to analyze and summarize a set of BBC News articles.

## ✅ Objectives Covered

### 1. Sub-category Classification
We applied KMeans clustering to group texts into subtopics within main categories:
- **Business**: e.g., stock market, mergers, company news
- **Entertainment**: e.g., music, cinema, theatre
- **Sport**: e.g., football, cricket, marathon

Results saved to: `subtopics.csv`

---

### 2. Named Entity Extraction with Role Classification
We extracted named entities (person names) and inferred their professions using rule-based keyword matching.

Examples:
- 🎤 "Beyoncé" ➝ *Musician*
- 🎬 "Keanu Reeves" ➝ *Actor*
- ⚽ "Thierry Henry" ➝ *Athlete*
- 🏛️ "Tony Blair" ➝ *Politician*

Results saved to: `media_entities.csv`

---

### 3. Extractive Summarization of April-related Events
We filtered sentences that mention **April**, and used a summarization model (`facebook/bart-large-cnn`) to generate concise summaries.

Use cases:
- Track scheduled or occurred events in April (past or future)
- Help in timeline-based NLP analytics

Results saved to: `april_summaries.csv`

---

## 📦 Technologies Used

- `Python`
- `scikit-learn` (TF-IDF, KMeans)
- `transformers` (HuggingFace BART summarizer)
- `pandas`, `re` (text processing)
- `regex`-based NER and rule-based job inference

---

## 🏁 How to Run

```bash
# Install required packages
pip install -r requirements.txt

# Run the end-to-end pipeline
python main.py
