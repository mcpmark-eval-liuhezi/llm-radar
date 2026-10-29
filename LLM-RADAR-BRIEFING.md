Account login: HeziLiu, starred repos: 6

# Local LLM Stack Radar — Briefing

Artifact for the team briefing on running and serving large language models on your own hardware. Folds together two lookups: a starred-repository list from the account, and the current open-source landscape of inference engines, serving frameworks and local runtimes (one entry per project with latest release / maintenance status, and whether you already star it).

Generated from the starred lookup, fresh GitHub-API release lookups, and web follow-ups.

## Top picks

1. **vLLM (vllm-project/vllm)** — High-throughput GPU inference and serving engine for LLMs; the production-serving reference for large models on a GPU.
   Latest release / maintenance: **v0.32.0** (latest release, 814 commits from 363 contributors); continues DeepSeek V4 day-0 support and ships CUDA 13.0 / ROCm / XPU wheels, with docs pages reaching up to v0.31.0 in October 2026. Very actively maintained.
   Already starred: **No.** (not in the lookup list)

2. **llama.cpp (ggml-org/llama.cpp)** — C/C++ LLM inference engine for CPU and Apple Silicon (and GPU); foundation behind many local runtimes and the raw base of GPU serving projects.
   Latest release / maintenance: **v0.8.0**, shipping the LiquidAI LFM3 pack (LFM3-1.7B text, LFM3-VL-2B vision, LFM3-Audio-2B/TTS) with new streaming-audio API; releases continue at the front line (every-negative-merge cadence), and the canonical ggml-org repo keeps shipping while the osllm/llama.cpp fork went read-only in February 2026.
   Already starred: **No.** (not in the lookup list)

3. **Ollama (ollama/ollama)** — One-command local-LLM runtime with an OpenAI-compatible API; the mainstream developer-first local stack.
   Latest release / maintenance: **v0.40.13** (published 2026-10-28), with the entire LiquidAI LFM3 family now runnable on Linux and Windows alongside Apple silicon; fixed issues landed consistently through Q4 2026.
   Already starred: **No.** (not in the lookup list)

4. **SGLang (sgl-project/sglang)** — High-performance serving framework with day-0 support for the latest open models, structured-output / JSON generation, and multiclient serving.
   Latest release / maintenance: **v0.5.22** (950 PRs from 245 contributors); CUDA 13 + PyTorch 2.11 handling, DSpark / HiSparse speculation, instant mmap loading, and the highest-tier support moved from **Apple Silicon Macs with the standard PyTorch backend alongside MLX**.
   Already starred: **No.** (not in the lookup list)

5. **TensorRT-LLM (NVIDIA/TensorRT-LLM)** — NVIDIA's high-performance inference engine for NVIDIA GPUs; deepest raw performance tuning per GPU with CUDA graph support and custom kernels.
   Latest release / maintenance: **v1.2.1** (released 2026-04-20, fixed an NV-cache corruption issue and bumped xgrammar / flashinfer); a vendor roadmap was announced in August 2025, NVIDIA standalone release images still ship for Darwin / Linux / Windows, and regular bug-fix cycles (e.g., the 0.20.x RTX / vLLM bridge line in June 2026) keep the track active.
   Already starred: **No.** (not in the lookup list)

## Cross-reference with your starred list

None of the five top picks appear in the starred list — you do not currently follow any of them. For a team stack, Ollama + llama.cpp cover the CPU side while vLLM or SGLang serve the GPU side; TensorRT-LLM is the NVIDIA-hardware-flavoured option if raw on-GPU perf wins out.

## Currently starred — every repository the lookup returned (6 total, newest-starred first)

- **OpenBMB/AgentCPM** — Still actively maintained: latest commit 2026-10-22 ("fix AgentDock security vulnerabilities"), and the AgentCPM ecosystem (AgentCPM-GUI, AgentCPM-Explore) is still rolling releases. ARC-AGI-weight models floated in reviews in 2026; not dormant.
- **PaddlePaddle/ERNIE** — Maintained anchor, but quiet on the repo itself: ERNIE 4.5 was open-sourced June 2025 with a large family (including ERNIE-4.5-VL, ERNIEKit, FastDeploy 2.0 adding OpenAI-compatible inference); however the repo's last merged commit is only 2025-12-26 and the default branch is release/v1.5.
- **FudanNLP/fastNLP** — Dormant: the repo states "Currently still in incubation", and its last real change was elasticbert feature merge in December 2022 with no activity since.
- **maplezzz/NTU_ML2017_Hung-yi-Lee_HW** — Course artifact archive from 2017: last commit "hw4 description" on March 15, 2019 and nothing meaningful in years.
- **fighting41love/funNLP** — Lazy maintenance: last commit August 24, 2023 (README note about OpenCompass); after 84k+ stars the repo has slowed to no observably recent improvements.
- **996icu/996.ICU** — Awareness repo, dormant: last commit April 2021; fully open with massive star counts, but there's no maintained project behind it.
