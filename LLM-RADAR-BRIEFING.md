Account login: HeziLiu, starred repos: 6

# Local LLM Stack Radar — Briefing

Artifact for the team briefing on running and serving large language models on your own hardware.

It folds together two lookups: a starred-repository list from the account (with a freshness/maintenance note on the five most recently starred repos) and the current open-source landscape of inference engines, serving frameworks and local runtimes (one entry per project with latest release / maintenance status, and whether you already star it).

Generated from the starred-lookup and follow-up web searches.

## Top picks

1. **vLLM** (vllm-project/vllm) — High-throughput GPU inference and serving engine for LLMs; the production-serving reference for large models on a GPU.
   Latest release / maintenance: v0.27.0 released 2026-08-10 (DeepSeek V4, Kimi K3 and Qwen3.5 support, PyTorch 2.13 upgrade, Model Runner V2 now covering non-generative tasks); multiple releases and daily CI, so actively maintained.
   Already starred? **No.**

2. **Ollama** (ollama/ollama) — One-command local-LLM runtime with an OpenAI-compatible API; the mainstream developer-first local stack.
   Latest release / maintenance: install artifacts dated 2026-10-21 along a rolling v0.3.x series; actively released, but mostly beta-style QA versions rather than canonical pairs.
   Already starred? **No.**

3. **llama.cpp** (ggml-org/llama.cpp) — C/C++ LLM inference engine for CPU and Apple Silicon; the foundation behind many local runtimes and the raw base of several GPU serving projects.
   Latest release / maintenance: releases continue at the front line (~1,000 releases since mid-2023, 5,000+ commits); note the osllmai/llama.cpp fork was frozen (read-only) on 2026-02-04, while the canonical ggml-org repo keeps shipping.
   Already starred? **No.**

4. **SGLang** (sgl-project/sglang) — High-performance serving framework with day-0 support for the latest open models, including structured-output / JSON generation.
   Latest release / maintenance: the v0.5.x line remains current (external release trackers show releases through at least v0.5.17), with an active community design discussion around the serving HTTP layer; actively maintained.
   Already starred? **No.**

5. **Text Generation WebUI** (oobabooga/textgen) — Classic open-source web front-end for loading and running locally loaded open models (ingest, management, run prompts).
   Latest release / maintenance: last real release cycle was around 2023; forks, notably vanilla-UI and BigPhenom, still carry the UI; known long-outstanding Windows-installer issues date to Oct 2023.
   Already starred? **No.**

## Cross-reference with my starred list

None of the five top picks appear in the starred list — every one reads "already starred? No". The closest security to "already following" is zero. For a team serving stack, Ollama + llama.cpp cover the CPU side while vLLM or SGLang serve the GPU side.

## Currently starred — every repository the lookup returned (6 total, newest starred first)

- **OpenBMB/AgentCPM** — repo metadata still current at lookup time (2026-10-29 scan); CI and README workflow still live, and the parent-ecosystem activity is still rolling → not stale.
- **PaddlePaddle/ERNIE** — actively developed: ERNIE 4.5 variants still ship (e.g. ERNIE-4.5-21B-A3B-Paddle, published 2025-12-23), with FastDeploy submitting PRs validating inference across platforms → actively maintained.
- **FudanNLP/fastNLP** — lowest signal found in web lookups; the repo itself flags it as "Currently still in incubation", so treat as dormant-ish research tooling rather than a runtime → not maintained.
- **maplezzz/NTU_ML2017_Hung-yi-Lee_HW** — 2017 Hung-yi Lee machine-learning course homework archive; nothing meaningful changed recently (no recent activity surfaced, only forks) → not maintained.
- **fighting41love/funNLP** — edited description still advertises the giant Chinese/English NLP resource kit, but the list is stale to the point of disconnection → not actively maintained.
- **996icu/996.ICU** — dormant: last commit 2019-04-04; no code for years; purely awareness-preserving (open repo, still faced with massive positive star counts) → no maintained project.
