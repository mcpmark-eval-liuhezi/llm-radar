# LLM Radar — Local LLM Stack Briefing

Account login: HeziLiu, starred repos: 6

## Top picks

1. **llama.cpp** (ggml-org/llama.cpp) — C/C++ LLM inference engine with GGUF support, minimal setup and wide hardware coverage. Latest release v0.8.0 (adds LFM3 family, realtime audio /v1/realtime and TTS endpoints, ggml bump to v0.28.0). Actively maintained with frequent releases.
2. **vLLM** (vllm-project/vllm) — High-throughput LLM inference and serving engine with PagedAttention and an OpenAI-compatible API. Latest release v0.33.0 (PyTorch 2.14, CUDA 13.0 wheels; target commit releases/v0.33.0). Actively maintained; recent CVE-2025-48956 DoS fix included.
3. **Ollama** (ollama/ollama) — Easy-to-run local LLM server with an OpenAI-compatible API and simple model management. Latest release v0.40.13 (published 2026-10-28; LFM3 models on Linux/Windows). Actively maintained.
4. **LM Studio** (lmstudio-ai/lmstudio) — Desktop UI for running local models with built-in model download and an optional OpenAI-compatible server. Latest stable 0.3.26 (Sep 2025 per official blog); GitHub repo does not expose releases/tags (404), so version is taken from lmstudio.ai. Actively maintained desktop app.
5. **SGLang** (sgl-project/sglang) — High-performance serving framework for LLMs and multimodal models with RadixAttention prefix caching and structured output. Latest release v0.5.22 (950 PRs from 245 contributors; Apple Silicon support, InstantTensor loader, PD disaggregation). Actively maintained.

Which picks I already star: None of llama.cpp, vLLM, Ollama, LM Studio, or SGLang appear in the starred list, so none of the top picks are already starred.

## Currently starred

- 996icu/996.ICU — Star-counting/protest repo (~277k stars); no code maintenance, not archived, API metadata updated 2026-11-02.
- fighting41love/funNLP — 84k-star Chinese/English NLP resource collection; snapshot-style repo, effectively unmaintained but not archived.
- maplezzz/NTU_ML2017_Hung-yi-Lee_HW — NTU 2017 ML course homework; last commit ~5 years ago, dormant.
- FudanNLP/fastNLP — Modular NLP framework (3.1k stars); description says "still in incubation", modest recent activity.
- PaddlePaddle/ERNIE — ERNIE 4.5 / ERNIEKit on PaddlePaddle; active model releases on Hugging Face (2025) and PaddleNLP issues, actively maintained.
- OpenBMB/AgentCPM — End-to-end LLM agent training/eval infrastructure (834 stars, 8 open issues); updated 2026-11-02, actively maintained.
