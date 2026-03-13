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

## Current Results (Snapshot)

Latest full report is in `results.md`. Current model comparison snapshot:

| Model | Accuracy % | Success/Scored | Median (s) | Mean (s) | P95 (s) | Latency Score |
|---|---:|---:|---:|---:|---:|---:|
| qwen3.5:397b | 100.0 | 4/4 | 17.07 | 16.80 | 21.08 | 15.2 |
| gemma3:12b | 87.5 | 7/8 | 2.60 | 3.62 | 7.77 | 100.0 |
| gemma3:4b | 77.8 | 7/9 | 3.43 | 3.56 | 4.96 | 75.9 |
| gemma3:27b | 66.7 | 2/3 | 6.80 | 7.60 | 10.48 | 38.2 |

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
