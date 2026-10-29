Account login: HeziLiu, starred repos: 6

# Local LLM Radar — Team Briefing

This is the pointable briefing for the team's stack decision on running and serving large language models on our own hardware: the current Go-To open-source options for local inference engines, serving frameworks and on-device runtimes, cross-referenced against the repositories currently starred on my GitHub account. The starred data comes straight from the GitHub API and the project statuses come from web searches plus GitHub release listings.

## Top picks — current open-source projects for running and serving LLMs on our own hardware

1. **llama.cpp** (github.com/ggml-org/llama.cpp) — C/C++ inference engine for GGUF models running on CPU, GPU and Apple Silicon — the minimal, hardware-agnostic base engine that many other local runtimes are built on.
   Latest release / maintenance: latest tagged release is **v0.8.0** (Oct 2026) on the canonical *ggml-org* org (note it moved there — the earlier *ggerganov* repo is now just a sparse mirror); thousands of incremental tagged releases since 2023 (~15k commits), extremely active. Not starred. For heavy CPU/SteamDeck-style hardware or as the base engine of a custom runtime.

2. **Ollama** (github.com/ollama/ollama) — the simplest developer-first local-LLM runtime: one-command `ollama pull/run`, an OpenAI-compatible HTTP API, and a desktop app; it bundles llama.cpp underneath.
   Latest release / maintenance: **v0.33.3** released 2 Sept 2026, on a steady late-0.3x cadence (v0.31.2 → v0.33.x; dependency-side releases through Oct 2026). Actively maintained, ~52M monthly downloads (Q1 2026) — though releases are verbose. Not starred. Consumer-hardware friendly wrapper around llama.cpp.

3. **vLLM** (github.com/vllm-project/vllm) — high-throughput, memory-efficient LLM inference and serving engine (PagedAttention, continuous batching, spec decoding) — the reference platform for GPU serving.
   Latest release / maintenance: **v0.32.0** (published 18 Oct 2026); hundreds of commits per release with the V4 tracking roadmap listed as the active development driver; actively maintained and one of the most active open-source AI projects. Not starred. Where to run this team: the GPU-serving backbone; pair with SGLang for agent / structured-output workloads.

4. **LM Studio** (github.com/lmstudio-ai/lm-studio) — GUI-first local desktop app that also exposes a local OpenAI-compatible server API; aimed at hardware you actually sit in front of.
   Latest release / maintenance: **0.4.26** released 13 Oct 2026 per the official changelog, on a 0.3x/0.4x cadence with quarterly model-support jumps (0.4.0 Jan 2026). Actively maintained; good as the desktop surface on single-GPU workstations. Not starred.

5. **SGLang** (github.com/sgl-project/sglang) — high-performance serving framework for LLMs and multimodal models, built on RadixAttention prefix caching with strong throughput for agent-style and structured-output workloads.
   Latest release / maintenance: latest v0.5.x (**v0.5.21**, Oct 2026 per release trackers; pipeline already at v0.5.21 with v0.5.10 shipped 6 Apr 2026) with design work ongoing (PD disaggregation, DSpark speculative decoding, Python 3.11+ from v0.5.20, Apple Silicon support). Actively maintained on NVIDIA CUDA 13.11 alongside AMD/intel build targets. Not starred.

**Are any of these already starred?** None. I have *not* starred any of the five hand-picked picks; my starred list skews toward agent *training/eval* research (OpenBMB/AgentCPM), a Chinese NLP toolkit (fastNLP), a PaddlePaddle model family (ERNIE/ERNIEKit), coursework materials (NTU ML2017 homework, funNLP) and the 996.ICU protest repo. Two are LLM-related but neither is a serving engine.

## Currently starred — every repository the lookup returned

The starred-repository lookup returned **6 repositories** (newest starred first). Five of them were web-checked; the sixth is listed for completeness.

- **OpenBMB/AgentCPM** — web status (checked): actively developed. The repo itself was updated 2026-10-29; the broader agent line keeps expanding (AgentCPM-Explore — the first full-parameter 4B open agent model to rank on long-horizon agent benchmarks — Jan 2026; on-device GUI agent work, AgentCPM-GUI). No formal GitHub *Releases* numbers surfaced, but no signs of stagnation. Recent major shift: compact 4B–8B agent models including on-device GUI agents.
- **PaddlePaddle/ERNIE** — web status (checked): maintained. The ERNIE 4.5 series was open-sourced in Sep 2025, including ERNIE 4.5-VL multimodal models, under Apache-2.0, with continued model releases built on PaddlePaddle for fast inference; FastDeploy keeps submitting inference-validation PRs and the release branch (`release/v1.5`) stays current. Recent major shift: open-weights, Apache-2.0 licensed model releases on top of PaddlePaddle inference.
- **FudanNLP/fastNLP** — web status (checked): dormant as a release line. The repo describes itself as "currently still in incubation"; last formal release v0.6.0 (Nov 2020) and PyPI untouched since 2022. Pre-LLM research/teaching tooling, not part of a modern serving stack.
- **maplezzz/NTU_ML2017_Hung-yi-Lee_HW** — web status (checked): static archive. 2017 Hung-yi Lee machine-learning course homework (Jupyter Notebook); no releases, no development — last page-lookups just surface the original course pages. Fine as study material, not maintained software.
- **fighting41love/funNLP** — web status (checked): maintained as a curated static list. Huge Chinese/English NLP corpora-and-toolkits catalog (~84k stars, 15k+ forks) with no formal releases and no developer releases; community-maintained and effectively frozen. Study/data material only, not a software project.
- **996icu/996.ICU** — web status (not web-checked, outside the five most recently starred): dormant and unrelated to serving hardware. Its own description reads "Repo for counting stars and contributing. Press F to pay respect to glorious developers." — a 2019-era protest/meme repository with no functional development.

## Bottom line for the hardware choice

- **Apple Silicon / consumer CPU, zero frills:** llama.cpp (ggml-org) raw, or Ollama as the friendly wrapper.
- **Team GPU serving, throughput-first:** vLLM v0.32 (+ PyTorch 3.13 upgraded GPU support; check breaks before upgrading a production server).
- **Structured output / agent workloads improving swiftly:** SGLang v0.5.x.
- **Hardware you sit in front of, GUI wanted:** LM Studio 0.4.26.
