# BBC News Subtopic Classification and Event Summarization

## 🎯 Objective

This project utilizes the BBC news dataset to:

1. **Classify major categories** (e.g. business, entertainment, sport) into **subtopics** using unsupervised learning.
2. **Extract and summarize** events involving the keyword "April" using an extractive summarization pipeline.
3. **Identify named media personalities** and infer their professions from context using rule-based heuristics.

## 📂 Dataset

The original dataset is structured into categories (`business`, `entertainment`, `sport`, etc.) and was converted into a CSV file (`bbc_raw_dataset.csv`) for further processing.

## 🛠️ Methods Used

- **TF-IDF + K-Means**: To cluster each category into meaningful subtopics.
- **Transformers (BART)**: For sentence-level summarization of "April" mentions.
- **Regex + Heuristic Rules**: For named entity recognition and job inference.

## 📁 Output Files

- `subtopics.csv`: Contains top keywords per cluster within each category.
- `april_summaries.csv`: Contains raw and summarized sentences related to April.
- `media_entities.csv`: Extracted names with inferred professions and context.

## ⚠️ Limitations

| Feature | Expected Output | Actual Output | Reason |
|--------|------------------|---------------|--------|
| Subtopic Extraction | Meaningful cluster separation (e.g. “stock market”, “mergers”) | Some noisy keywords | TF-IDF lacks contextual understanding |
| Summarization | Concise summaries | Sometimes cuts off sentences or provides trivial phrases | Transformer model not always suited for short input, limited input size |
| Job Inference | Accurate professions for named persons | Heuristic guesses (e.g. "Unknown") | Advanced NLP models like spaCy were unavailable due to installation issues |

## ❌ Missing Features

- No use of **spaCy** NER due to installation errors (`en_core_web_sm` could not be downloaded).
- No real-time abstractive summarization models (e.g. T5) were applied due to resource constraints.

## ✅ Suggestions for Improvement

- Use a **pretrained NER model** (like spaCy or Flair) for better name and job extraction.
- Replace heuristic summarizer with **T5 or PEGASUS** models.
- Integrate **topic modeling** (LDA or BERTopic) for richer subtopic discovery.

## 📦 Requirements

```bash
transformers
scikit-learn
pandas
nltk
