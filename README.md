# Turkish LLM Benchmark (MVP)

Real-time Streamlit app for quickly evaluating open-source LLMs on Ollama Cloud with a simple Turkish Q/A benchmark.

## Overview

- This app uses a simple Turkish question-answer set to provide a fast baseline evaluation for Ollama Cloud models.
- The questions were prepared by Murat Karakaya for instructional purposes.
- The app provides a lightweight UI and backend to run evaluations, compare models, and record results automatically.

## Contributing Questions

To update existing questions or add new ones, please open a Pull Request on GitHub by editing `data/benchmark.json`. Follow the existing JSON structure, fill all fields correctly, and assign a new unique `id` in `qNNN` format (use the next available number, do not renumber existing IDs).

## Quick Start

```bash
pip install -r requirements.txt
streamlit run app.py
```

## Environment Variables

- `OLLAMA_API_KEY` (required)
- `OLLAMA_HOST` (optional, default: `https://ollama.com`)

## Dataset

Source-of-truth dataset is:
- `data/benchmark.json`

Each record must include:
- `id` (immutable, format `qNNN`, e.g. `q001`)
- `question`
- `expected_answer`

Optional fields used in UI:
- `topic`
- `hardness_level`
- `why_prepared`

Dataset loading, validation, and writes are handled by:
- `data/benchmark.py`

## Runtime Outputs

- `data/results.json`: canonical run results
- `results.md`: auto-generated comparison report (accuracy + latency + matrix)

## Question Distribution by Topic

| Topic | Question Count | Share |
|---|---:|---:|
| Türkçe | 6 | 26.1% |
| HAFIZA | 4 | 17.4% |
| Genel Kültür | 4 | 17.4% |
| Mantık | 4 | 17.4% |
| FİNANS | 2 | 8.7% |
| Coğrafya | 1 | 4.3% |
| KODLAMA | 1 | 4.3% |
| Tarih | 1 | 4.3% |
| **Toplam** | **23** | **100%** |

## Current Behavior

- App reads questions only from `data/benchmark.json` (no PDF/DOCX extraction path).
- Expected answer edits in UI are written back to `data/benchmark.json` by question `id`.
- Model responses stream in real time in the UI.
- Results are auto-saved after each run/decision.
- Default system prompt enforces Turkish answers.
