Account login: HeziLiu, starred repos: 6

# LLM Radar — Local LLM Serving Briefing

Briefing for the team deciding on a stack to run and serve large language models on our own hardware. Current go-to open-source options for inference engines, serving frameworks and local runtimes, cross-referenced against the repositories currently starred on the GitHub account.

**Repository location note:** a fresh repo could not be created directly on the personal `HeziLiu` account — the token was rejected with 403 "Resource not accessible by personal access token" — so the briefing was committed to the `llm-radar` repository in the `mcpmark-eval-liuhezi` organization, at the repository root.

**Data provenance:** starred repositories from the GitHub API `list_starred_repositories` for account `HeziLiu` (pagination verified — no further pages returned; 6 repositories total); project statuses from web searches plus GitHub release/tag listings.

## Top picks

Five projected open-source projects for running and serving LLMss on our own hardware, each with the latest release or maintenance status from the web:

### 1. llama.cpp —— github.com/ggml-org/llama.cpp
- **Purpose:** C/C++ inference engine for GGUF models — minimal setup, hardware-agnostic, runs on CPU, CUDA/ROCm GPU and Apple Silicon, and the base engine many other local runtimes are built on.
- **Latest release / maintenance:** **v0.8.0** is the latest tag, with v0.7.0 and v0.6.0 already below it. Extremely active — tens of thousands of commits since 2023 on a continuous release cadence, with day-0 support for new model families. Not starred.

### 2. Ollama —— github.com/ollama/ollama
- **Purpose:** The simplest developer-first local-LLM runtime: one-command model pulls, an OpenAI-compatible HTTP API, and a desktop app; it bundles llama.cpp underneath.
- **Latest release / maintenance:** **v0.40.13** is the latest tag (v0.40.12e, v0.40.11 just before it); web coverage documents a Sept 2026 v0.35.0/v0.35.1 with new decision models and provenance handling (GLM-5.2). Actively maintained on a regular 0.40.x cadence. Not starred.

### 3. vLLM —— github.com/vllm-project/vllm
- **Purpose:** High-throughput, memory-efficient LLM inference and serving engine (PagedAttention, continuous batching, spec decoding) — the reference platform for production GPU serving.
- **Latest release / maintenance:** stable **v0.32.0** is the latest release tag, with bleeding-edge **v0.33.0rc0/rc1** already out; releases land roughly every two weeks and vLLM 0.27.0 (Aug 2026) added Kimi K3, Qwen3.5 and DeepSeek-V4 optimizations plus a PyTorch 2.13 upgrade. Extremely active, one of the most active open-source AI projects. Not starred.

### 4. SGLang —— github.com/sgl-project/sglang
- **Purpose:** High-performance serving framework for LLMs and multimodal models, built on RadixAttention prefix caching, with strong throughput for agent-style and structured-output workloads.
- **Latest release / maintenance:** **v0.5.22** is the latest tag (v0.5.21, v0.5.20 below it), with pass-through Docker images at v0.5.12-cu130 (CUDA 13.0, PyTorch 2.11 shared across sglang/sgl-kernel/container images) and model gallery just past 1,900 entries. Active rhythm; design work ongoing (PD disaggregation, DSpark speculative decoding, Apple Silicon support). Not starred.

### 5. LM Studio —— github.com/lmstudio-ai/lm-studio
- **Purpose:** GUI-first local desktop app that also exposes a local OpenAI-compatible server API; aimed at hardware you actually sit in front of (intro-priced desktop for Home/Steam Machine class hardware).
- **Latest release / maintenance:** the official changelog's most recent release is **0.4.6** (Feb 27, 2026, "Introducing LM Link Connect to remote instances of LM Studio"), having released 0.3.26 in Sept 2025; the issue tracker shows active GitHub activity through Oct 2026 (github-120 joined August 2026). Actively maintained on a ~quarterly cadence. Not starred.

## Cross-reference: top picks vs starred list

**None of the five picks are starred.** The starred list skews toward LLM agent-training/evaluation research (OpenBMB/AgentCPM), a PaddlePaddle model family (ERNIE/ERNIEKit), a Chinese NLP toolkit (fastNLP), course materials (funNLP, NTU ML2017 homework) and one cultural repo (996.ICU). Two LLM-adjacent stars (AgentCPM, ERNIE) are agent research on Chinese models, not serving infrastructure.

## Currently starred

Every repository the lookup returned, newest first. The five most recently starred were web-checked for maintenance status; the sixth falls outside the five most recent, so it is listed without a check.

- **OpenBMB/AgentCPM** — actively developed: repo updated 2026-10-29, no formal GitHub Releases directed, but the OpenBMB agent line keeps expanding (AgentCPM-GUI for on-device Android GUI agents, AgentCPM-Explore — first full-parameter 4B open agent model to rank on long-horizon agent benchmarks, Jan 2026). LLM-agent *research*, not a serving engine; recent major shift: compact 4B–8B agent models including on-device GUI agents.
- **PaddlePaddle/ERNIE** — maintained: the ERNIE 4.5 series (including ERNIE 4.5-VL) was open-sourced Sep 2025 under Apache-2.0 with continued model releases on PaddlePaddle for fast inference; the release branch `release/v1.5` stays current. Recent major shift: open-weights Apache-2.0 model releases with FastDeploy inference validation.
- **FudanNLP/fastNLP** — dormant as a release line: repo describes itself as "currently still in incubation"; last formal release v0.6.0 (Nov 2020) and PyPI untouched since 2022 — a pre-LLM-era research/teaching framework, not part of a modern serving stack.
- **maplezzz/NTU_ML2017_Hung-yi-Lee_HW** — static archive: 2017 Hung-yi Lee machine-learning course homework (Jupyter Notebook); no releases, no development — last page lookups only surface the original course pages. Fine as study material, not maintained software.
- **fighting41love/funNLP** — maintained as a curated static list: huge Chinese/English NLP corpora, lexicon and toolkit catalog with no formal releases; community-maintained, heavily forked, with data mirrored into the cocoNLP Python package — a curated resource list rather than a maintained codebase.
- **996icu/996.ICU** — not web-checked (outside the five most recently starred): a 2019-era protest/meme repository ("Repo for counting stars and contributing…") with no functional development; enormous but unrelated to LLM serving.

## Bottom line for the hardware choice

- **Apple Silicon / consumer CPU, no frills:** llama.cpp, or Ollama as the friendly one-command wrapper.
- **Team GPU serving, throughput-first:** vLLM — ship CUDA 12.9/13.0 wheels, review the changelog (breaking changes land regularly, e.g. Python 3.10 dropped) before upgrading a production server.
- **Structured output / agent workloads:** SGLang, greatest win on agent-form workflows.
- **GUI for single-GPU workstations:** LM Studio 0.4x previews, surfaced many times in comparison lists as a GUI vLLM/SGLang successor.
