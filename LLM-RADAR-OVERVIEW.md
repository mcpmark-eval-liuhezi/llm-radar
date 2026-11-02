Account login: HeziLiu, starred repos: 6

# LLM Radar — Local LLM Stack Briefing

Briefing for the team picking a stack for running and serving large language models on own hardware, cross-referenced against the GitHub starred-repositories lookup.

## Top picks

1. **vLLM** (vllm-project/vllm) — High-throughput, memory-efficient inference and serving engine for LLMs (PagedAttention, continuous batching, OpenAI-compatible API). Latest release: v0.33.0 (milestone v0.20.2 also referenced); actively maintained with ~2-week release cadence; web sources call it the top open-source project on GitHub for 2025. Already starred: No.

2. **llama.cpp** (ggml-org/llama.cpp) — C/C++ inference runtime for GGUF models supporting CPU, CUDA, Vulkan and Apple Metal; simple, dependency-light local serving. Latest release: v0.8.0 (Release #5218, Oct 2026; ggml-org container images updated Oct 2026). Already starred: No.

3. **Ollama** (ollama/ollama) — Easy-to-run local LLM server with model pull/management and REST API. Latest release: v0.40.13 (published 2026-10-28; Homebrew core/ollama at 0.40.7). Already starred: No.

4. **SGLang** (sgl-project/sglang) — High-performance serving framework for LLMs and multimodal models with structured output, PD disaggregation and Kubernetes-friendly deployment. Latest release: v0.5.22 (950 PRs from 245 contributors). Already starred: No.

5. **TensorRT-LLM** (NVIDIA/TensorRT-LLM) — NVIDIA's optimized LLM inference SDK for NVIDIA GPUs (FP8/INT8, KV cache, multi-node serving). Latest release: v1.2.1 (published 2026-04-20); 0.18.0/0.18.1 also announced; docs last updated Oct 2026. Already starred: No.

## Currently starred

- **996icu/996.ICU** — Stars-counting/protest repo; last updated 2026-11-02; not an ML project, no active development.
- **fighting41love/funNLP** — Large Chinese/English NLP resources collection; last commit 2023-08-24; inactive.
- **maplezzz/NTU_ML2017_Hung-yi-Lee_HW** — NTU 2017 ML course homework repo; last commit 2019-03-15; long dormant.
- **FudanNLP/fastNLP** — Modularized NLP framework; last commit 2022-12-13 ("add elasticbert"); described as "currently in incubation"; largely dormant.
- **PaddlePaddle/ERNIE** — ERNIE 4.5 / ERNIEKit on PaddlePaddle; last commit 2025-12-26 on release/v1.5 with CI still running in 2026; actively maintained.
- **OpenBMB/AgentCPM** — End-to-end infrastructure for training/evaluating LLM agents; last commit 2026-10-22 ("fix AgentDock security vulnerabilities"); actively maintained.

None of the five top picks (vLLM, llama.cpp, Ollama, SGLang, TensorRT-LLM) appear in the starred list.
