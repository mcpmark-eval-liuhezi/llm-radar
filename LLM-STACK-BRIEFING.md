Account login: HeziLiu, starred repos: 6

# LLM Radar — Running &amp; Serving LLMs on Our Own Hardware (Stack Briefing)

A short, pointable briefing on the current go-to open-source projects for running and serving large language models locally, cross-referenced against the repositories I currently star on GitHub. Starred data was pulled fresh from the GitHub API on 2026-10-21; project statuses come from web searches plus GitHub release lookups.

**Hosting note:** this briefing lives in the `mcpmark-eval-liuhezi/llm-radar` repository (the organization account reachable with the current API credentials). Creating the repository directly on the personal `HeziLiu` account was rejected by the API token (403 — "Resource not accessible by personal access token"), so the org-owned repo is the fallback location.

## Top picks

Five recommended projects for running and serving LLMs locally, each with a web-checked release / maintenance status:

### 1. llama.cpp — ggml-org/llama.cpp
- **Purpose:** C/C++ inference engine for LLMs and VLMs (the GGUF ecosystem) with minimal setup and state-of-the-art performance across a wide range of hardware — locally and in production; it is the engine many other runtimes build on.
- **Latest release / maintenance:** **v0.7.0** — very actively maintained. The release adds LiliCorr speculative decoding, a host-memory MoE-expert GPU cache (`--moe-cache-mib`, up to ~2.2x decode speedup), and a large batch of new model architectures. The project ships continuously and gets day-0 support for new model releases.
- **Already starred?** **No.**

### 2. Ollama — ollama/ollama
- **Purpose:** The easiest local LLM runtime — one-command model pulls, an OpenAI-compatible API and desktop app; it bundles llama.cpp under the hood.
- **Latest release / maintenance:** **v0.40.7** (published 2026-10-18) — actively maintained; web coverage shows a steady 0.40.x cadence (e.g. 0.40.4 on 2026-10-14 adding decision models in the CLI). Watch item: a Windows update-mechanism RCE was disclosed in April 2026, so keep the client current.
- **Already starred?** **No.**

### 3. vLLM — vllm-project/vllm
- **Purpose:** High-throughput, memory-efficient LLM inference and serving engine (PagedAttention, continuous batching) — the default choice for production GPU serving.
- **Latest release / maintenance:** **v0.32.0** — extremely active: 814 commits from 363 contributors in the release alone. PyPI history shows 0.30.0 (2026-09-22) and 0.31.0 (2026-10-05) preceding it, and NVIDIA ships its own vLLM container builds (release 26.08). Breaking changes land regularly — review the changelog before upgrading production inference servers.
- **Already starred?** **No.**

### 4. SGLang — sgl-project/sglang
- **Purpose:** High-performance serving framework for LLMs and multimodal models, known for RadixAttention prefix caching, structured output, and strong agent-workload throughput.
- **Latest release / maintenance:** **v0.5.22** — actively maintained: 950 PRs from 245 contributors in the release; web results show the repo updated within the last day. Now requires Python 3.11+ and ships NVIDIA, AMD MI30x/MI35x and Intel GPU/CPU images.
- **Already starred?** **No.**

### 5. LocalAI — mudler/LocalAI
- **Purpose:** Self-hosted, drop-in OpenAI API replacement that runs LLMs, image generation and audio models locally on consumer hardware, with many interchangeable backends.
- **Latest release / maintenance:** **v4.11.0** — very actively maintained: 243 merged PRs in a 15-day development window ending 2026-10-02, a weekly project report cadence (reports.localai.io), and a model gallery that just passed 1,900 entries.
- **Already starred?** **No.**

### Considered but excluded: Hugging Face TGI (huggingface/text-generation-inference)
Web results show the repository **was archived by its owner on 2026-03-21** and is now read-only; the final release note itself was "Maintenance mode" (v3.3.7, 2025-12-19). It is therefore not recommended for a new self-hosted serving stack, and was dropped from the picks in favor of LocalAI.

## Currently starred

The starred-repository lookup returned **6 repositories**, listed below. The five most recently starred were web-checked for maintenance status; the sixth falls outside the five most recent, so it is listed without a check.

1. **OpenBMB/AgentCPM** — End-to-end infrastructure for training and evaluating various LLM agents. **Web status (checked): actively developed** — repo updated 2026-10-21, though it has no formal GitHub Releases. The family keeps expanding: AgentCPM-Report (8B, built on the MiniCPM4.1 base, announced Jan 2026) for autonomous long-form report generation, and AgentCPM-Explore (Sep 2026), the first full-parameter 4B agent model to rank on 8 long-horizon agent benchmarks. Major recent shift: focus on compact 4B–8B agent models, including on-device GUI agents.
2. **PaddlePaddle/ERNIE** — Official repository for the ERNIE 4.5 model family and ERNIEKit, its industrial-grade development toolkit based on PaddlePaddle. **Web status (checked): maintained** — default branch is `release/v1.5`, updated 2026-10-20; the latest formal release tag is `ernie-4.5` (2025-06-30). Web results show continued ERNIE-4.5-VL model releases through late 2025, built on PaddlePaddle for high-performance inference across hardware.
3. **FudanNLP/fastNLP** — A modularized and extensible NLP framework (still "in incubation"). **Web status (checked): effectively dormant as a release line** — last formal release v0.6.0 (2020-11-06) and PyPI last updated 2022-10-31; the 1.0 line has been in incubation for years. The repo still receives occasional pushes (updated 2026-10-14), but this is a pre-LLM-era research/teaching framework, not part of a modern serving stack.
4. **maplezzz/NTU_ML2017_Hung-yi-Lee_HW** — NTU ML2017 Spring/Fall course homework for Hung-yi Lee's machine learning course. **Web status (checked): static archive** — 2017-era homework solutions in Jupyter notebooks, no releases and no sign of development; web results only surface the original course pages. Fine as study material, not maintained software.
5. **fighting41love/funNLP** — A huge curated collection of Chinese/English NLP resources (corpora, lexicons, toolkits, pre-trained models). **Web status (checked): maintained as a curated list** — repo updated 2026-10-21 with ~84k stars; no formal releases (it is an awesome-list), and web coverage (Sep 2025) still describes it as a community-maintained toolkit with data integrated into the `cocoNLP` Python package.
6. **996icu/996.ICU** — "Repo for counting stars and contributing. Press F to pay respect to glorious developers." **(Not web-checked — outside the five most recently starred.)** A 2019-era protest/meme repository with ~277k stars; still enormous, but with no functional development.

## Cross-reference summary

**None of the five top picks are in my starred list.** The starred list skews toward Chinese NLP resources, course materials, agent-infra research (AgentCPM, ERNIE) and one cultural meme repo, while the modern local-serving stack (llama.cpp, Ollama, vLLM, SGLang, LocalAI) is entirely un-followed. If we adopt this stack, starring those five projects would be a reasonable hygiene step.

## Method

- **Starred list:** GitHub API `list_starred_repositories` for account `HeziLiu`, sorted by star date descending — 6 repositories returned; pagination was verified to be exhausted (no further pages).
- **Picks &amp; statuses:** Google web searches via serp-search, plus GitHub latest-release lookups per project (llama.cpp under `ggml-org`, Ollama, vLLM, SGLang, LocalAI, and TGI for the exclusion note).
- **Starred-repo checks:** Google web searches for the five most recently starred repositories, corroborated with GitHub release/metadata lookups.
