Account login: HeziLiu, starred repos: 6

# Local LLM Radar — Team Briefing

Pointable briefing for the team's stack decision on running and serving large language models on our own hardware: the current go-to open-source inference engines, serving frameworks and local runtimes, cross-referenced against the repositories currently starred on my GitHub account. Starred data comes straight from the GitHub API (paged, newest-starred-first — 6 repositories total; the page after that was empty, so nothing was sliced off). Project statuses come from web searches plus GitHub release listings.

## Top picks — current open-source projects for running and serving LLMs on our own hardware

1. **Ollama** (github.com/ollama/ollama) — Purpose: developer-first local-LLM runtime; `ollama pull/run` one-command installs, OpenAI-compatible HTTP API, desktop app; wraps llama.cpp underneath. Latest release / maintenance: latest **v0.40.x line** — v0.40.5 published 2026-10-15, with a burst of 0.40.x builds 2026-10-11 to 2026-10-18 (Nemotron 3.5, `q2_0` GGUF and other model-format support plus cloud-side features); actively maintained, though note the Oct 2026 CVE advisory (Ollama up to 0.34.1, fixed in 0.34.2) — not starred.
2. **vLLM** (github.com/vllm-project/vllm) — Purpose: high-throughput, memory-efficient LLM inference and serving engine (PagedAttention, continuous batching, speculative decoding) — the reference platform for GPU serving. Latest release / maintenance: **v0.31.0** (released 2026-10-05; DeepSeek-V4.1-Flash performance work, etc.), actively maintained — hundreds of commits per release (~717 from 307 contributors), one of the most active open-source AI projects; not starred.
3. **llama.cpp** (github.com/ggml-org/llama.cpp) — Purpose: C/C++ inference engine for GGUF models on CPU, GPU and Apple Silicon; the minimal, hardware-agnostic base engine many local runtimes are built on. Latest release / maintenance: still extremely active in 2026 — weekly GitHub reports through August 2026 (including a 2026-08-31 report), org live under *ggml-org* (the old *ggerganov/llama.cpp* repo is a sparse mirror), no build freeze, multiple 2026 date-tagged releases; not starred.
4. **LocalAI** (github.com/mudler/LocalAI) — Purpose: open-source OpenAI-compatible inference server that runs LLMs, vision, voice, image and video models on any hardware — no GPU required — as a drop-in replacement for OpenAI APIs, with a WebUI and model gallery. Latest release / maintenance: actively maintained under the *mudler/LocalAI* org (original go-skynet/LocalAI is long unmoved) — weekly sprint reports continuing through 2026-03-29, multi-PR weekly cycles; latest patch tags **v4.12.1** (compare shows v4.12.0 → v4.12.1); **not starred**.
5. **LM Studio** (github.com/lmstudio-ai/lm-studio) — Purpose: GUI-first local desktop app for running LLMs with a blocked-open local OpenAI-compatible server API; aimed at the hardware you actually sit in front of. Latest release / maintenance: actively maintained on a 0.3x/0.4x cadence — 0.3.38 (Jan 2026), 0.4.9 (Apr 2026), 0.4.14 (May 2026), 0.4.16/0.4.18 (Jun 2026); MLX Engine + parallel-request support in the 0.4.x line; active bug-tracker traffic in 2026; **not starred**.

**Are any of these already starred?** No. None of the five picks appear on my starred list.

## Cross-reference: my starred list

My five picks are *not* currently starred. My starred list instead skews toward LLM-adjacent research tooling and coursework: agent training/eval infra (OpenBMB/AgentCPM), a Chinese NLP toolkit (fastNLP), a PaddlePaddle model family (ERNIE/ERNIEKit), Hung-yi Lee's 2017 ML course homework and the funNLP corpora catalog, plus 996.ICU. Only open-LLM-adjacent surface (agent/LLM research) — but none of these are serving engines.

## Currently starred — every repository the lookup returned, with web status

The lookup returned **6 repositories** (newest-starred first); I web-checked the five most recently starred.

- **OpenBMB/AgentCPM** — Web check (checked): actively developed — repo updated 2026-10-29; the agent line keeps expanding (AgentCPM-Explore — first full-parameter 4B open agent model on long-horizon benchmarks, Jan 2026; ongoing AgentCPM-GUI on-device agent work). No formal GitHub release numbers surfaced. Recent major shift: compact 4B–8B agents incl. on-device GUI agents.
- **PaddlePaddle/ERNIE** — Web check (checked): maintained — ERNIE 4.5 and ERNIE 4.5-VL open-sourced Sep 2025 (Apache-2.0), continued model releases, `release/v1.5` branch stays current, FastDeploy keeps submitting inference-validation PRs. Recent major shift: open-weights, Apache-2.0 model releases on PaddlePaddle/FastDeploy.
- **FudanNLP/fastNLP** — Web check (checked): dormant as a release line — repo describes itself as "currently still in incubation"; last formal release v0.6.0 (Nov 2020), PyPI quiet since 2022. Last major shift was 2020; not part of a modern serving stack.
- **maplezzz/NTU_ML2017_Hung-yi-Lee_HW** — Web check (checked): static archive — 2017 Hung-yi Lee machine-learning course homework (Jupyter Notebooks). No releases, no development; last "updates" are the original course pages. Last major shift: never shipped beyond the 2017 course.
- **fighting41love/funNLP** — Web check (checked): maintained as a curated static list — ~84k stars, 15k+ forks, Chinese/English corpora and NLP-tool catalog; no formal release process ever existed; community-built and effectively frozen. Last major shift: static catalog growth only.
- **996icu/996.ICU** — Not web-checked (sixth of six, outside the top-5-most-recently-starred scope): dormant, unrelated to serving hardware. Description: "Repo for counting stars and contributing. Press F to pay respect to glorious developers." — a 2019-era labor-protest/meme repository with no functional development.

## Bottom line for the hardware choice

- Apple Silicon / consumer CPU, zero frills → llama.cpp raw, or Ollama as the friendly wrapper.
- Team GPU serving, throughput-first → vLLM (PyTorch upgrades land on each release; verify before upgrading a production server).
- Structured output / agent workloads → LocalAI as the flexible OpenAI-compatible server.
- GUI on single-GPU workstations → LM Studio 0.4.x.
