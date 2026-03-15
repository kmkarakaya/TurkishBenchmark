# Turkish LLM Benchmark Results
_Güncellendi: 2026-03-15T21:31:06+03:00_

## Model Karşılaştırma
| Model | Accuracy % | Success/Scored | Median | Mean | P95 | Latency Score |
|---|---:|---:|---:|---:|---:|---:|
| qwen3.5:397b | 100.0 | 14/14 | 14.81s | 17.70s | 41.00s | 21.5 |
| gemma3:27b | 82.6 | 19/23 | 6.38s | 6.67s | 10.77s | 49.8 |
| gemma3:12b | 69.6 | 16/23 | 3.18s | 4.46s | 6.60s | 100.0 |
| gemma3:4b | 34.8 | 8/23 | 3.46s | 4.17s | 9.38s | 91.9 |

## Soru Bazlı Sonuç Matrisi
| Soru ID | Kategori | gemma3:12b | gemma3:27b | gemma3:4b | qwen3.5:397b |
|---|---|---|---|---|---|
| q001 | Türkçe | ✅ 2.65s | ✅ 7.19s | ✅ 3.43s | ✅ 11.71s |
| q002 | Türkçe | ✅ 2.36s | ✅ 3.98s | ✅ 3.12s | ✅ 5.09s |
| q003 | Türkçe | ✅ 2.55s | ✅ 6.47s | ✅ 3.46s | ✅ 14.52s |
| q004 | Türkçe | ✅ 2.52s | ✅ 3.57s | ✅ 3.25s | ✅ 21.58s |
| q005 | Türkçe | ✅ 2.74s | ✅ 5.11s | ✅ 4.36s | ✅ 10.97s |
| q006 | Türkçe | ✅ 2.37s | ✅ 2.87s | ❌ 1.81s | ✅ 41.48s |
| q007 | Mantık | ❌ 5.32s | ✅ 10.89s | ❌ 9.87s | - |
| q008 | Mantık | ✅ 2.30s | ✅ 3.69s | ❌ 2.75s | - |
| q009 | Mantık | ✅ 5.60s | ✅ 6.02s | ❌ 3.32s | - |
| q010 | Mantık | ❌ 1.42s | ❌ 3.45s | ❌ 3.54s | - |
| q011 | Tarih | ❌ 3.61s | ✅ 5.43s | ❌ 4.80s | - |
| q012 | Coğrafya | ✅ 5.26s | ✅ 6.38s | ❌ 3.03s | - |
| q013 | Genel Kültür | ❌ 3.90s | ❌ 7.30s | ❌ 2.84s | ✅ 19.04s |
| q014 | Genel Kültür | ❌ 5.62s | ✅ 6.87s | ❌ 3.51s | ✅ 21.44s |
| q015 | Genel Kültür | ✅ 1.78s | ✅ 7.01s | ❌ 4.51s | - |
| q016 | Genel Kültür | ✅ 3.18s | ✅ 6.80s | ✅ 3.58s | ✅ 11.60s |
| q017 | FİNANS | ✅ 6.41s | ✅ 9.06s | ❌ 5.05s | - |
| q018 | FİNANS | ❌ 6.62s | ✅ 8.38s | ❌ 4.23s | - |
| q019 | KODLAMA | ✅ 23.62s | ❌ 23.34s | ❌ 12.05s | ✅ 16.21s |
| q020 | HAFIZA | ✅ 2.83s | ✅ 3.83s | ❌ 4.73s | ✅ 6.03s |
| q021 | HAFIZA | ✅ 4.68s | ✅ 9.63s | ✅ 3.16s | ✅ 15.10s |
| q022 | HAFIZA | ✅ 3.19s | ✅ 3.56s | ✅ 2.60s | ✅ 12.27s |
| q023 | HAFIZA | ❌ 1.98s | ❌ 2.49s | ❌ 2.88s | ✅ 40.75s |
