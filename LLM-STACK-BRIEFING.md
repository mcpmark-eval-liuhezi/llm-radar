Account login: HeziLiu, starred repos: 6

# LLM Radar — Running & Serving LLMs Locally (Stack Briefing)

A short, pointable briefing for the team on the current go-to open-source projects for running and serving large language models on our own hardware, cross-referenced against the repositories currently starred on the GitHub account. Starred data was pulled fresh from the GitHub API; project statuses come from web searches plus GitHub latest-release lookups.

**Hosting note:** the briefing lives in the `mcpmark-eval-liuhezi/llm-radar` repository. Creating a fresh `llm-radar` directly on the personal `HeziLiu` account was rejected by the API token (403 — "Resource not accessible by personal access token"), and the org already had an `llm-radar` repo. The file below was committed as the briefing at the repo root, superseding the earlier version.

## Top picks

Five recommended projects for running and serving LLMs locally, each with a web-checked release / maintenance status:

### 1. llama.cpp — ggml-org/llama.cpp
- **Purpose:** C/C++ inference engine for LLMs and VLMs on the GGUF format — minimal setup, hardware-agnostic, and the engine many other runtimes build on.
- **Latest release / maintenance:** **v0.7.0** (latest release on GitHub, published 2026-10-23). Very actively maintained: ships continuously with LiliCorr speculative decoding, a host-memory MoE-expert GPU cache (`--moe-cache-mib`, up to ~2.2x decode speed), and a broad batch of new model architectures (K2 Horizon, EmbeddingGemma-2, LiquidAI d1, vLLM decision models, MiniCPM-V 4.7, Nemotron Super 3.5). Day-0 support for new model releases.
- **Already starred?** **No.**

### 2. Ollama — ollama/ollama
- **Purpose:** The easiest local LLM runtime — one-command model pulls, an OpenAI-compatible HTTP API, and a desktop app; it bundles llama.cpp under the hood.
- **Latest release / maintenance:** **v0.40.10**, published 2026-10-23. Actively maintained with a steady 0.40.x cadence (0.40.9 2026-10-22 → 0.40.10 2026-10-23). The latest model bundle adds Nemotron 3.5 Bolt E4B — a Gemma 4-based vision-language model with a 128K context and a DFlash draft for speculative decoding. Watch item: an April 2026 Windows update-mechanism RCE was disclosed in llama.cpp, so keep clients current.
- **Already starred?** **No.**

### 3. vLLM — vllm-project/vllm
- **Purpose:** High-throughput, memory-efficient LLM inference and serving engine (PagedAttention, continuous batching) — the default choice for production GPU serving.
- **Latest release / maintenance:** **v0.32.0**, the latest release. Extremely active — 814 commits from 363 contributors in the release alone (v0.30.0 2026-09-22, v0.31.0 2026-10-05). Ships CUDA 12.9/13.0, ROCm, XPU and CPU wheels plus official NVIDIA container builds. Breaking changes land regularly (e.g. Python 3.10 dropped) — review the changelog before upgrading a production inference server.
- **Already starred?** **No.**

### 4. SGLang — sgl-project/sglang
- **Purpose:** High-performance serving framework for LLMs and multimodal models, known for RadixAttention prefix caching, structured output, and strong agent-workload throughput.
- **Latest release / maintenance:** **v0.5.22**, the latest release (950 PRs from 245 contributors). Now requires Python 3.11+. Ships NVIDIA CUDA 13 images plus AMD MI35x/MI30x and Intel XPU/CPU images; adds PD disaggregation, DSpark/EAGLE3 speculative decoding, Apple Silicon support, and an InstantTensor loader for ~10x faster model loads.
- **Already starred?** **No.**

### 5. LocalAI — mudler/LocalAI
- **Purpose:** Self-hosted, drop-in OpenAI API replacement that runs LLMs, image, audio and video models on consumer hardware, with many interchangeable backends.
- **Latest release / maintenance:** **v4.12.1**, published 2026-10-23 — a security-only patch hardening the external-URL policy for user-supplied URLs (redirects validated on every hop, 100.64.0.0/10 and 0.0.0.0/8 treated as non-public). Active release cadence through October 2026, weekly project reports at reports.localai.io, and a model gallery that just passed 1,900 entries.
- **Already starred?** **No.**

## Currently starred

The starred-repository lookup returned **6 repositories** (sorted by starred date, newest first). The five most recently starred were web-checked for maintenance status; the sixth falls outside the five most recent, so it is listed without a check.

1. **OpenBMB/AgentCPM** — End-to-end infrastructure for training and evaluating various LLM agents (Python, 834 stars). **Web status (checked): actively developed** — repo updated 2026-10-23/24 with no formal GitHub Releases, but the family keeps expanding: AgentCPM-GUI (2025, on-device GUI agents for Android), AgentCPM-Report, and AgentCPM-Explore (Jan 2026, the first full-parameter 4B open-source agent model to rank on 8 long-horizon agent benchmarks). Major recent shift: compact 4B–8B agent models, including on-device GUI agents.
2. **PaddlePaddle/ERNIE** — Official repository for ERNIE 4.5 and ERNIEKit, its industrial-grade development toolkit based on PaddlePaddle (Python, 7,741 stars). **Web status (checked): maintained** — default branch `release/v1.5` updated 2026-10-24; ERNIE 4.5 / ERNIE 4.5-VL model releases continued through late 2025, built on PaddlePaddle for high-performance inference across hardware.
3. **FudanNLP/fastNLP** — A modularized and extensible NLP framework, "currently still in incubation" (Python, 3,139 stars). **Web status (checked): effectively dormant as a release line** — last formal release v0.6.0 (2020-11-06) and PyPI last updated 2022-10-31; the 1.0 line has been in incubation for years. Occasional commits remain, but this is a pre-LLM-era research/teaching framework, not part of a modern serving stack.
4. **maplezzz/NTU_ML2017_Hung-yi-Lee_HW** — NTU ML2017 Spring/Fall homework for Hung-yi Lee's machine learning course (Jupyter Notebook, 874 stars). **Web status (checked): static archive** — 2017-era course homework solutions with no releases and no development; web results only surface the original course pages. Fine as study material, not maintained software.
5. **fighting41love/funNLP** — A huge curated collection of Chinese/English NLP corpora, lexicons, toolkits and pre-trained models (Python, ~84k stars, 15k+ forks). **Web status (checked): maintained as a curated list** — repo updated 2026-10-24; it is an awesome-list with no formal releases, and web coverage still describes it as a community-maintained toolkit with data integrated into the cocoNLP Python package.
6. **996icu/996.ICU** — "Repo for counting stars and contributing. Press F to pay respect to glorious developers." (~277k stars). **(Not web-checked — outside the five most recently starred.)** 2019-era protest/meme repository; enormous, but with no functional development.

## Cross-reference summary

**None of the five top picks are in the starred list.** The starred list skews toward Chinese NLP resources, course materials, agent-infra research (AgentCPM, ERNIE) and one cultural meme repo, while the modern local-serving stack (llama.cpp, Ollama, vLLM, SGLang, LocalAI) is entirely un-followed. If we adopt this stack, starring those five projects would be a reasonable hygiene step.

## Method

- **Starred list:** GitHub API `list_starred_repositories` for account `HeziLiu`, sorted by star date descending — 6 repositories returned; pagination was verified to be exhausted (no further pages).
- **Picks & statuses:** Google web searches via serp-search, plus GitHub latest-release lookups per project (llama.cpp, Ollama, vLLM, SGLang, LocalAI).
- **Web checks:** Google web searches for each of the five most recently starred repositories, cross-referenced with GitHub API metadata (last push dates, open issues, stars) for the "still maintained?" signal.