Account login: HeziLiu, starred repos: 6

# LLM Radar — Local LM Stack Briefing

Short briefing for the team picking a stack to run and serve large language models on our own hardware. Covers top open-source inference/serving projects and cross-references them against the starred-repositories list on the HeziLiu GitHub account.

## Top picks

### 1. llama.cpp (ggml-org/llama.cpp)
- Purpose: C/C++ inference engine for running GGUF-format LLMs on CPU, CUDA, ROCm, Metal, SYCL and webassembly.
- Latest release / maintenance: v0.8.0 is the latest GitHub release; nightly builds at b11326-b11330 (Oct 2026). Actively maintained.
- Already starred: No.

### 2. Ollama (ollama/ollama)
- Purpose: Simple CLI and REST API for pulling and running large language models locally.
- Latest release / maintenance: v0.40.13 (published 2026-10-28; adds LFM3 on Linux/Windows). Actively maintained.
- Already starred: No.

### 3. vLLM (vllm-project/vllm)
- Purpose: High-throughput LLM inference and serving engine (PagedAttention) for GPU servers.
- Latest release / maintenance: v0.33.0 (rc3; stable v0.32.0 published 2026-10-18 per PyPI). Actively maintained.
- Already starred: No.

### 4. LM Studio (lmstudio-ai)
- Purpose: Desktop GUI plus local OpenAI-compatible server for chatting with and serving LLMs.
- Latest release / maintenance: 0.4.27 per Uptodown (Oct 30 2026); changelog entries 0.4.14 (May 2026) and 0.4.2 (Feb 2026). GitHub releases API returned 404; the desktop app is still shipping regular updates.
- Already starred: No.

### 5. MLC-LLM (mlc-ai/mlc-llm)
- Purpose: ML-compiled universal LLM deployment engine; efficient inference of LLMs across CPUs, GPUs, phones and browsers.
- Latest release / maintenance: Latest GitHub release v0.1.dev0 (Apr 2023); SourceForge mirror last updated 2026-07-07 and CI still running (Windows CI #2723). Actively maintained, no formal releases since 2023.
- Already starred: No.

## Currently starred (6 repositories returned by the lookup)

1. OpenBMB/AgentCPM — Actively maintained; last commit 2026-10-22 ("fix AgentDock security vulnerabilities").
2. PaddlePaddle/ERNIE — Maintained; last commit 2025-12-26; official repo for ERNIE 4.5 / ERNIEKit on PaddlePaddle.
3. FudanNLP/fastNLP — Dormant since Dec 2022 (last commit 2022-12-13); README still says "Currently still in incubation".
4. maplezzz/NTU_ML2017_Hung-yi-Lee_HW — Static NTU ML2017 coursework (Hung-yi Lee's assignments); last updated 2026-10-26.
5. fighting41love/funNLP — Dormant since Aug 2023 (last commit 2023-08-24); large Chinese NLP resource collection.
6. 996icu/996.ICU — Protest/solidarity repo; last updated 2026-11-02; not actively developed.
