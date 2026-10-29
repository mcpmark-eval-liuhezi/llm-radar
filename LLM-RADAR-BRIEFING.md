Account login: HeziLiu, starred repos: 6

# Local LLM Serving Radar — Team Briefing

Pointable briefing for the team on running and serving large language models on our own hardware: the current go-to open-source inference engines, serving frameworks and local runtimes — cross-referenced against the repositories currently starred on the GitHub account. Starred data was pulled straight from the GitHub API (6 repositories, pagination verified exhausted); project statuses come from follow-up web searches and GitHub release listings.

Hosting note: where this briefing lives — creating a `llm-radar` repo directly on the `HeziLiu` account was rejected by the API token (403 "Resource not accessible by personal access token"); the org `mcpmark-eval-liuhezi` already contained a repo with exactly that name (`mcpmark-eval-liuhezi/llm-radar`), so this file was committed at the root of that repository.

## Top picks — current go-to open-source projects for running and serving LLMs locally

Five recommended projects, in rough terms of what each is best for:

1. **vLLM** (github.com/vllm-project/vllm) — high-throughput, memory-efficient LLM inference and serving engine with PagedAttention and continuous batching; the default production-serving engine on a GPU.
   Latest release / maintenance: latest stable **v0.32.0**, published ~2026-10-18 (docs.vllm.ai and release trackers agree), on the ~2-week release cadence (v0.30.0 2026-09-22, v0.31.0 2026-10-05) with hundreds of commits per release; actively maintained. Pair with SGLang for agent / structured-output workloads.
   Already starred? **No.**

2. **Ollama** (github.com/ollama/ollama) — the developer-first local-LLM runtime: one-command model pulls, an OpenAI-compatible HTTP API, and a desktop app; bundles llama.cpp underneath.
   Latest release / maintenance: releases kept running through 2026 in the late-0.3x line (v0.31.2 released 2026-07-06; v0.30.8 2026-06-12; dependency bumps to v0.32.5 surfaced late Oct 2026); actively maintained, though releases are verbose / QA-style.
   Already starred? **No.** (The comfort layer on top of llama.cpp.)

3. **llama.cpp** (github.com/ggml-org/llama.cpp) — C/C++ inference engine for GGUF models on CPU, GPU and Apple Silicon; the base engine behind most local runtimes and GPU-serving projects.
   Latest release / maintenance: incremental tagged releases kept shipping on the canonical ggml-org repo (latest tagged release **b10470**, Aug 2026) — thousands of releases and 5,000+ commits since 2023; actively maintained. Note the project moved to the `ggml-org` org, so point newcomers there.
   Already starred? **No.**

4. **Hugging Face Text Generation Inference — TGI** (github.com/huggingface/text-generation-inference) — open-source, OpenAI-compatible inference server for Hugging Face Hub models, with Turnkey containers and structured output.
   Latest release / maintenance: the last true release line was v3.0.2 (2024-12), with later 3.x builds; the official HF container package was archived by the owner on 2026-03-21, so the ecosystem is retreating — stable but with diminishing support.
   Already starred? **No.**

5. **SGLang** (github.com/sgl-project/sglang) — high-performance serving framework with RadixAttention prefix caching, structured JSON output, and strong agent-workload throughput for LLMs and multimodal models.
   Latest release / maintenance: latest v0.5.x series release is **v0.5.21** (2026-10-01) per release trackers, with CI and serving-layer design work ongoing; actively maintained.
   Already starred? **No.**

## Cross-reference: my five picks vs. your starred list

**None of the five picks are currently starred** — every one reads "already starred? **No.**" Your starred repos skew toward agent-training research (OpenBMB/AgentCPM), a Chinese NLP toolkit (fastNLP), a PaddlePaddle model family (ERNIE/ERNIEKit), and coursework / materials (NTU ML2017 HW, funNLP) plus the 996.ICU protest repo. AgentCPM and ERNIE are LLM-related, but AgentCPM is agent *training/eval* infra and ERNIE ships as model weights on PaddlePaddle — neither is a serving engine. So the modern local-serving stack is entirely un-followed; if the team adopts this stack, starring these five would be an easy hygiene step.

## Currently starred — every repository the lookup returned (6 total, newest starred first)

Five of these were web-checked for maintenance status (the five most recently starred); the sixth is listed for completeness.

- **OpenBMB/AgentCPM** — checked: actively developed. The agent training/eval infrastructure keeps expanding — most recently AgentCPM-Explore (Jan 2026), the first full-parameter 4B open model to rank on eight long-horizon agent benchmarks, plus on-device GUI-agent work (AgentCPM-GUI). No formal release numbers surfaced, but no stagnation.
- **PaddlePaddle/ERNIE** — checked: maintained. ERNIE 4.5 / ERNIE 4.5-VL are now open-source under the Apache 2.0 license (Sep 2025) with continued model releases built on PaddlePaddle for fast inference, and FastDeploy keeps submitting inference-validation PRs; the release branch stays current.
- **FudanNLP/fastNLP** — checked: dormant as a release line. The repo self-describes as "Currently still in incubation"; last formal release v0.6.0 (Nov 2020) and PyPI untouched since 2022. Pre-LLM research / teaching tooling — not part of a modern serving stack.
- **maplezzz/NTU_ML2017_Hung-yi-Lee_HW** — checked: static archive. 2017 Hung-yi Lee machine-learning course homework; no releases, no development.
- **fighting41love/funNLP** — checked: maintained as a curated static list. A huge Chinese/English NLP corpus, lexicon and toolkit catalog (~84k stars, 15k+ forks) with no formal releases; its own description reads "Currently still in incubation" — community-curated, not a maintained project.
- **996icu/996.ICU** — dormant, and outside the five-most-recently-starred batch. Plain awareness/protection repo with no maintained code; no functional relation to serving hardware.

(Recent-change summary: AgentCPM landed compact 4B–8B agent models incl. on-device GUI agents; ERNIE moved to Apache-2.0 open weights with multimodal variants; fastNLP froze pending 1.0 with nothing published since 2022; funNLP is effectively a frozen catalog; NTU homework and 996.ICU unchanged.)

## Bottom-line advice for hardware choice

- **Consumer CPU / Apple Silicon:** llama.cpp raw, or Ollama as the friendly wrapper.
- **Bulk GPU serving:** vLLM (the reference platform).
- **Structured output / agent workloads improving swiftly:** SGLang (day-0 support for the newest models).
- **Hub-native turn-key servers:** TGI, but check its maintenance winds down before depending on it.
