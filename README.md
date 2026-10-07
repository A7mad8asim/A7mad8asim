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
- **82.5% of held-out questions and 87.5% of large-table questions answered correctly on a local 8B model, at about 2 seconds per question**; every unanswerable question refused, 14 of 16 Gulf-dialect questions correct (144 bilingual gold questions, with held-out and large-table splits)
- **Ablation, step by step:** reranking moved the answer row to first place (57% → 80%), showing the model only the 3 best rows fixed refusals, and query translation plus hybrid BM25 + bge-m3 retrieval recovered Gulf dialect; profiling then found a 2-second `localhost` delay per request and cut the time per question from 12.4 to 2.2 seconds
- **All 1,432 datasets indexed:** 2.8 million trade rows as server-side totals by country and month, the rest in full (29,699 chunks); a Streamlit app with linked source cards, a GPU Docker setup tested end to end, and tests in CI

`Python` `RAG` `BM25` `bge-m3` `Ollama` `Streamlit` `REST API` `Docker` `pytest` `GitHub Actions`

---

## 🛠 Tools I've Used in Public Projects

| Category | Tools |
| :--- | :--- |
| **Languages** | Python, SQL |
| **LLMs** | Ollama (Qwen3), Anthropic API, prompt design, few-shot retrieval, evaluation harnesses |
| **Retrieval / RAG** | BM25, bge-m3 embeddings, hybrid retrieval with reciprocal rank fusion, LLM reranking, query translation, Arabic text normalization, citation grounding |
| **Data** | DuckDB, Pandas, NumPy, REST API ingestion, synthetic data generation |
| **Apps & Engineering** | Streamlit, Docker, pytest, GitHub Actions |

---

## 🎯 Currently Building

- 📚 Fixing the **RAG** assistant's remaining wrong-row answers (7 of 120)
- 🧪 **Fine-tuning** a small open model to close the Gulf-dialect accuracy gap (63% → ?)
- 📈 **Forecasting** clinic demand and no-show risk with explainable ML

---

## 📫 Connect

- 📧 [a7mad8asim@gmail.com](mailto:a7mad8asim@gmail.com)
