Account login: HeziLiu, starred repos: 6

# LLM Radar — Local LLM Stack Briefing

A short briefing on the current go-to open-source projects for running and serving large language models on your own hardware (inference engines, serving frameworks, and local runtimes), cross-referenced against the author's currently starred GitHub repositories.

## Top picks

1. **llama.cpp** — Purpose: minimal-setup, high-performance LLM inference engine for local hardware (CPU, CUDA, Vulkan, Metal, ...) using the GGUF model format. Latest release / maintenance: actively maintained under ggml-org; 165+ releases tracked with frequent cadence and recent container images (server-cuda12-b10830); latest precise tag not pinned by search but clearly active. Already star it: No.
2. **vLLM** — Purpose: high-throughput, memory-efficient LLM inference and serving library built around PagedAttention. Latest release / maintenance: latest stable v0.32.0 (published Oct 18, 2026); regular ~2-week release cadence; actively maintained (v4.1 tracking issue open). Already star it: No.
3. **Ollama** — Purpose: easy CLI/runtime for pulling and running local LLMs with a simple REST API on your own machine. Latest release / maintenance: v0.40.10 (Oct 23, 2026), with v0.40.11 adding macOS speech/text-to-speech during model runs; actively maintained. Already star it: No.
4. **LM Studio** — Purpose: desktop GUI for discovering, downloading, and running local LLMs with an OpenAI-compatible server API. Latest release / maintenance: 0.4.24 changelog (Sep 9, 2026); active development with frequent releases; v0.4.0 noted in bug tracker (Feb 2026). Already star it: No.
5. **Text Generation Inference (TGI)** — Purpose: Rust-based high-performance serving engine for deploying and serving transformer LLMs. Latest release / maintenance: upstream repository archived by owner on Mar 21, 2026; latest release v2.0.4; community fork maintained under OPA (Open Platform for AI) with public Helm chart tgi 1.4.0. Already star it: No.

## Currently starred

1. **OpenBMB/AgentCPM** — Actively maintained; end-to-end infrastructure for training and evaluating LLM agents; recent activity observed (repo updated Oct 2026).
2. **PaddlePaddle/ERNIE** — Actively maintained; ERNIE 4.5 models and ERNIEKit industrial toolkit on PaddlePaddle; model releases via ModelArts (ERNIE-4.5-21B-A3B-Paddle updated Dec 2025).
3. **FudanNLP/fastNLP** — Effectively dormant; description reads "Currently still in incubation"; no recent releases found in web search.
4. **maplezzz/NTU_ML2017_Hung-yi-Lee_HW** — Stable archive of Hung-yi Lee's 2017 NLP course homework; not actively maintained.
5. **fighting41love/funNLP** — Community-maintained Chinese/English NLP corpus and tools collection; forks still being updated (2025-2026); still maintained by the community.
6. **996icu/996.ICU** — Still live (277k+ stars) but a cultural reference repo, not software-maintained.

## Notes

- Starred-repos lookup returned a total of 6 repositories; the five picks above are not among them, so none are already starred.
- Web statuses are from search snippets and may lag; for production use, verify exact latest tags on each project's GitHub Releases page.
