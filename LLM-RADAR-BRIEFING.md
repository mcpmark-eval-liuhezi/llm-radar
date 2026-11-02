Account login: HeziLiu, starred repos: 6

# LLM Radar — Briefing

Short briefing for the team picking a stack for running and serving large language models on own hardware.

## Top picks

1. **llama.cpp** (ggml-org/llama.cpp) — C/C++ inference engine for GGUF models; highly portable CPU/GPU inference. Latest release: v0.8.0 (recent release adding LFM3 audio models, realtime /v1/realtime API and /tts endpoint). Actively maintained.
2. **vLLM** (vllm-project/vllm) — High-throughput, memory-efficient LLM inference and serving engine (PagedAttention). Latest release: v0.33.0 (Oct 2026; CUDA 13.0 wheels, ROCm 10.0 images). Actively maintained.
3. **Ollama** (ollama/ollama) — Easy local LLM server/CLI wrapping llama.cpp with model受体 management. Latest release: v0.40.13 (published 2026-10-28; adds Liquid AI LFM3 family on Linux/Windows). Actively maintained.
4. **SGLang** (sgl-project/sglang) — High-performance serving framework for LLMs and multimodal models, strong for structured output and PD disaggregation. Latest release: v0.5.22 (950 PRs, 245 contributors; Apple Silicon PyTorch backend). Actively maintained.
5. **TGI / Text Generation Inference** (huggingface/text-generation-inference) — Hugging Face's production inference server for transformer models. Latest release: v3.3.7 (Dec 2025); repository archived on 2026-03-21 and placed in maintenance mode — last release v3.3.7, no active development since.

Star status: none of these five picks (llama.cpp, vLLM, Ollama, SGLang, TGI) appear in the starred-repositories list.

## Currently starred

Total starred repositories returned by the lookup: 6

- 996icu/996.ICU — Stars-counting/protest repository; not LLM-related. Web check: static since ~2019, no major recent changes.
- fighting41love/funNLP — Large Chinese/English NLP resources corpus; last updated 2026-11-02 per GitHub; dormant but no major restructuring recently.
- maplezzz/NTU_ML2017_Hung-yi-Lee_HW — NTU ML2017 coursework homework repo; last updated 2026-10-26; no major recent changes, educational only.
- FudanNLP/fastNLP — Modularized NLP framework described as "still in incubation"; last updated 2026-10-30; low recent activity.
- PaddlePaddle/ERNIE — Official ERNIE 4.5 / ERNIEKit repo on PaddlePaddle; last updated 2026-11-01; active development (Baidu).
- OpenBMB/AgentCPM — End-to-end infrastructure for training and evaluating LLM agents; last updated 2026-11-02; active.

Five most-recently-starred web checks: OpenBMB/AgentCPM (active, updated 2026-11-02), PaddlePaddle/ERNIE (active, updated 2026-11-01), FudanNLP/fastNLP (low activity, updated 2026-10-30), maplezzz/NTU_ML2017_Hung-yi-Lee_HW (inactive coursework, 2026-10-26), fighting41love/funNLP (dormant resource dump, updated 2026-11-02).
