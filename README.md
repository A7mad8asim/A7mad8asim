# 👋 Hi, I'm Ahmed

**Data Scientist & Analyst** building LLM-powered analytics tools that are measured, private and safe, with a focus on **Arabic / English** and **healthcare & operations** data.

---

## ⭐ Featured Projects

### [Ask-the-Data · اسأل البيانات](https://github.com/A7mad8asim/ask-the-data)

A bilingual (Arabic / English, including Gulf dialect) **text-to-SQL assistant for clinic analytics**. Managers ask a question in their own words and get a correct number back, with a chart and the SQL that produced it.

- **79% execution accuracy** on a 100-question bilingual gold set, using a **local 8B model** (Qwen3 via Ollama), so no health data leaves the machine
- **20 / 20** privacy and safety attacks blocked: a SQL sandbox on the parsed query tree, a read-only database and small-group suppression (`<10`)
- The LLM never calculates a number: every figure in an answer is checked against the result table
- Ablation study (schema → glossary → few-shot retrieval → repair loop), a self-checking evaluation harness in CI, and Docker

`Python` `DuckDB` `sqlglot` `Ollama` `Claude API` `Streamlit` `pytest` `GitHub Actions` `Docker`

### [Arabic RAG Assistant · مساعد الإحصاءات](https://github.com/A7mad8asim/arabic-rag-assistant) <sub>work in progress</sub>

Bilingual **retrieval-augmented generation over Qatar's official open statistics**: 1,432 National Planning Council datasets from the Qatar Open Data portal. Ask in Arabic or English; every figure in the answer links to the dataset it came from.

- **Grounding check:** the model may only repeat numbers found in the sources it cites; any other number and the answer is withheld
- **Bilingual chunks:** Arabic and English values are paired from the portal's twin columns (`Doha / الدوحة`), so one index serves both languages
- **First baseline on a 40-question seed set:** 75% of answers correct (Arabic 80%), 87% hit@6 retrieval, 90% of unanswerable questions refused, all Gulf-dialect questions correct
- Data pipeline from the portal's API (23,465 chunks), BM25 with optional bge-m3 hybrid retrieval, a Streamlit app with linked source cards, and tests in CI

`Python` `BM25` `RAG` `Ollama` `Streamlit` `REST API` `pytest` `GitHub Actions`

---

## 🛠 Tools I've Used in Public Projects

| Category | Tools |
| :--- | :--- |
| **Languages** | Python, SQL |
| **LLMs** | Ollama (Qwen3), Anthropic API, prompt design, few-shot retrieval, evaluation harnesses |
| **Retrieval / RAG** | BM25, hybrid retrieval with reciprocal rank fusion, Arabic text normalization, citation grounding |
| **Data** | DuckDB, Pandas, NumPy, REST API ingestion, synthetic data generation |
| **Apps & Engineering** | Streamlit, Docker, pytest, GitHub Actions |

---

## 🎯 Currently Building

- 📚 Growing the **RAG** benchmark to ~120 bilingual questions and adding a reranker to catch wrong-row answers
- 🧪 **Fine-tuning** a small open model to close the Gulf-dialect accuracy gap (63% → ?)
- 📈 **Forecasting** clinic demand and no-show risk with explainable ML

---

## 📫 Connect

- 📧 [a7mad8asim@gmail.com](mailto:a7mad8asim@gmail.com)
