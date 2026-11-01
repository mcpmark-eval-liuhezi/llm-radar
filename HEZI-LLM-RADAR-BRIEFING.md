Account login: HeziLiu, starred repos: 6

# LLM Radar — Local LLM Serving Briefing

A short briefing for the team picking a stack to run and serve large language models on our own hardware. It combines current open-source tooling picks for local inference and serving with a cross-reference against the author's GitHub starred-repository list.

## Top picks

1. **llama.cpp** (ggerganov/llama.cpp, now under ggml-org) — C/C++ inference engine for GGUF-quantized models, the de-facto local-runtime backbone. Latest release ~1.2 (Mar 2025); actively maintained under the ggml-org organisation. **Already star?** No.
2. **Ollama** (ollama/ollama) — one-command CLI for pulling and running local LLMs with an OpenAI-compatible API. Latest release v0.1.48 (with v0.40.x RC lines per release trackers); actively maintained. **Already star?** No.
3. **vLLM** (vllm-project/vllm) — high-throughput LLM serving engine with PagedAttention, optimised for GPUs. Latest PyPI release 0.30.0 (Sep 2025) plus 3.0 (Dec 2025); actively maintained with frequent releases. **Already star?** No.
4. **LM Studio** (lmstudio-ai/LM Studio) — desktop GUI for experimenting with local models plus an OpenAI/Anthropic-compatible API. Latest stable 0.3.38 (Jan 2026); actively maintained. **Already star?** No.
5. **text-generation-webui** (oobabooga/text-generation-webui) — feature-rich web UI for running LLMs with multiple backends. Recent desktop spin-off (oobabooga/textgen) and ongoing updates; maintained at a moderate pace. **Already star?** No.

None of the five picks appear in the starred list, so the author does not currently star any of them.

## Currently starred

The lookup returned 6 starred repositories:

1. **OpenBMB/AgentCPM** — end-to-end infrastructure for training and evaluating LLM agents; recently active (repo updated 2026-10-30, ~833 stars).
2. **PaddlePaddle/ERNIE** — official repository for ERNIE 4.5 and ERNIEKit (PaddlePaddle toolkit); Baidu open-sourced ERNIE 4.5 in Jul 2025 and it remains actively developed (updated 2026-10-31, ~7.7k stars).
3. **FudanNLP/fastNLP** — modular, extensible NLP framework; self-described as "currently still in incubation" and not heavily active recently (~3.1k stars).
4. **maplezzz/NTU_ML2017_Hung-yi-Lee_HW** — NTU Hung-yi Lee machine-learning course homework (2017); educational archive, not a maintained LM project.
5. **fighting41love/funNLP** — large Chinese/English NLP resource collection; largely a passive reference list with no recent major changes (~84k stars).
6. **996icu/996.ICU** — "Repo for counting stars and contributing"; a protest/star-counting repository, not a technical project.

Web status for the five most recently starred repos checked: AgentCPM and ERNIE are both recently active; fastNLP is in incubation and quiet; the NTU homework repo is static course material; funNLP is an evergreen but largely unmaintained resource dump.

None of the five LLM serving picks (llama.cpp, Ollama, vLLM, LM Studio, text-generation-webui) are in the starred list.
