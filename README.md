<div align="center" id="sglangtop">
<img src="https://raw.githubusercontent.com/sgl-project/sglang/main/assets/logo.png" alt="logo" width="400" margin="10px"></img>

[![PyPI](https://img.shields.io/pypi/v/sglang)](https://pypi.org/project/sglang)
![PyPI - Downloads](https://static.pepy.tech/badge/sglang?period=month)
[![license](https://img.shields.io/github/license/sgl-project/sglang.svg)](https://github.com/sgl-project/sglang/tree/main/LICENSE)
[![issue resolution](https://img.shields.io/github/issues-closed-raw/sgl-project/sglang)](https://github.com/sgl-project/sglang/issues)
[![open issues](https://img.shields.io/github/issues-raw/sgl-project/sglang)](https://github.com/sgl-project/sglang/issues)
[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/sgl-project/sglang)

</div>

--------------------------------------------------------------------------------

<p align="center">
<a href="https://lmsys.org/blog/"><b>博客</b></a> |
<a href="https://docs.sglang.io/"><b>文档</b></a> |
<a href="https://roadmap.sglang.io/"><b>路线图</b></a> |
<a href="https://slack.sglang.io/"><b>加入 Slack</b></a> |
<a href="https://meet.sglang.io/"><b>每周开发会议</b></a> |
<a href="https://github.com/sgl-project/sgl-learning-materials?tab=readme-ov-file#slides"><b>幻灯片</b></a>
</p>

## 新闻
- [2026/07] 🔥 SGLang 与 Miles 为 Kimi K3 提供 Day-0 支持（[博客](https://lmsys.org/blog/2026-07-27-kimi-k3-day0-support/)）。
- [2026/07] RadixArk 与 Google 将 SGLang 的完整特性带到 TPU（[博客](https://lmsys.org/blog/2026-07-30-sglang-google-tpu/)）。
- [2026/07] 用 SGLang 承载 GLM5.2 NVFP4 Agent 工作负载：两周内达到 500 TPS（[博客](https://lmsys.org/blog/2026-07-13-glm52-optimization/)）。
- [2026/06] 🔥 下一代投机解码：DFlash 与 Spec V2（[博客](https://lmsys.org/blog/2026-06-15-next-generation-speculative-decoding-dflash-v2/)）。
- [2026/06] SGLang 为最新开源模型提供 Day-0 支持（[Nemotron 3 Ultra](https://lmsys.org/blog/2026-06-04-nvidia-run-nemotron-3-ultra/)、[Nemotron 3 Super](https://lmsys.org/blog/2026-03-11-run-nvidia-nemotron-3-super/)、[Higgs Audio v3 TTS](https://lmsys.org/blog/2026-06-04-higgs-audio-v3-tts/)）。
- [2026/04] 🔥 DeepSeek-V4 Day-0 支持：从快速推理到基于验证的强化学习（SGLang 与 Miles）（[博客](https://lmsys.org/blog/2026-04-25-deepseek-v4/)）。
- [2026/02] 🔥 在 NVIDIA GB300 NVL72 上用 SGLang 实现 25 倍推理性能提升（[博客](https://lmsys.org/blog/2026-02-20-gb300-inferencex/)）。
- [2026/01] SGLang Diffusion 加速视频与图像生成（[博客](https://lmsys.org/blog/2026-01-16-sglang-diffusion/)）。

<details>
<summary>更多</summary>

- [2025/12] SGLang 为最新开源模型提供 Day-0 支持（[MiMo-V2-Flash](https://lmsys.org/blog/2025-12-16-mimo-v2-flash/)、[Nemotron 3 Nano](https://lmsys.org/blog/2025-12-15-run-nvidia-nemotron-3-nano/)、[Mistral Large 3](https://github.com/sgl-project/sglang/pull/14213)、[LLaDA 2.0 Diffusion LLM](https://lmsys.org/blog/2025-12-19-diffusion-llm/)、[MiniMax M2](https://lmsys.org/blog/2025-11-04-miminmax-m2/)）。
- [2025/11] SGLang Diffusion 加速视频与图像生成（[博客](https://lmsys.org/blog/2025-11-07-sglang-diffusion/)）。
- [2025/10] SGLang 现在通过 SGLang-Jax 后端原生运行在 TPU 上（[博客](https://lmsys.org/blog/2025-10-29-sglang-jax/)）。
- [2025/10] PyTorch 大会 2025 SGLang 演讲（[幻灯片](https://github.com/sgl-project/sgl-learning-materials/blob/main/slides/sglang_pytorch_2025.pdf)）。
- [2025/10] SGLang × NVIDIA 旧金山 Meetup（[回顾](https://x.com/lmsysorg/status/1975339501934510231)）。
- [2025/09] 在 GB200 NVL72 上通过 PD 分离和大规模 EP 部署 DeepSeek（第二部分）：3.8 倍预填充、4.8 倍解码吞吐（[博客](https://lmsys.org/blog/2025-09-25-gb200-part-2/)）。
- [2025/09] SGLang 为带稀疏注意力的 DeepSeek-V3.2 提供 Day-0 支持（[博客](https://lmsys.org/blog/2025-09-29-deepseek-V32/)）。
- [2025/08] SGLang × AMD 旧金山 Meetup（8/22）：动手 GPU 工作坊、AMD/xAI/SGLang 技术演讲与交流（[路线图](https://github.com/sgl-project/sgl-learning-materials/blob/main/slides/amd_meetup_sglang_roadmap.pdf)、[大规模 EP](https://github.com/sgl-project/sgl-learning-materials/blob/main/slides/amd_meetup_sglang_ep.pdf)、[亮点](https://github.com/sgl-project/sgl-learning-materials/blob/main/slides/amd_meetup_highlights.pdf)、[AITER/MoRI](https://github.com/sgl-project/sgl-learning-materials/blob/main/slides/amd_meetup_aiter_mori.pdf)、[Wave](https://github.com/sgl-project/sgl-learning-materials/blob/main/slides/amd_meetup_wave.pdf)）。
- [2025/08] SGLang 为 OpenAI gpt-oss 模型提供 Day-0 支持（[说明](https://github.com/sgl-project/sglang/issues/8833)）
- [2025/06] SGLang 作为每天承载数万亿 token 的高性能推理服务基础设施，获得 a16z 第三批开源 AI 资助（[a16z 博客](https://a16z.com/advancing-open-source-ai-through-benchmarks-and-bold-experimentation/)）。
- [2025/06] 在 GB200 NVL72 上通过 PD 分离和大规模 EP 部署 DeepSeek（第一部分）：2.7 倍解码吞吐提升（[博客](https://lmsys.org/blog/2025-06-16-gb200-part-1/)）。
- [2025/05] 在 96 块 H100 GPU 上用 PD 分离和大规模专家并行部署 DeepSeek（[博客](https://lmsys.org/blog/2025-05-05-large-scale-ep/)）。
- [2025/03] 在 AMD Instinct MI300X 上加速 DeepSeek-R1 推理（[AMD 博客](https://rocm.blogs.amd.com/artificial-intelligence/DeepSeekR1-Part2/README.html)）
- [2025/03] SGLang 加入 PyTorch 生态：高效的 LLM 推理服务引擎（[PyTorch 博客](https://pytorch.org/blog/sglang-joins-pytorch/)）
- [2025/02] 解锁 AMD Instinct™ MI300X GPU 上的 DeepSeek-R1 推理性能（[AMD 博客](https://rocm.blogs.amd.com/artificial-intelligence/DeepSeekR1_Perf/README.html)）
- [2025/01] SGLang 在 NVIDIA 与 AMD GPU 上为 DeepSeek V3/R1 提供 Day-1 支持，并包含针对 DeepSeek 的专项优化（[说明](https://github.com/sgl-project/sglang/tree/main/benchmark/deepseek_v3)、[AMD 博客](https://www.amd.com/en/developer/resources/technical-articles/amd-instinct-gpus-power-deepseek-v3-revolutionizing-ai-development-with-sglang.html)、[10 余家公司](https://x.com/lmsysorg/status/1887262321636221412)）
- [2024/12] v0.4 发布：零开销批处理调度器、缓存感知的负载均衡器、更快的结构化输出（[博客](https://lmsys.org/blog/2024-12-04-sglang-v0-4/)）。
- [2024/10] 首次 SGLang 线上 Meetup（[幻灯片](https://github.com/sgl-project/sgl-learning-materials?tab=readme-ov-file#the-first-sglang-online-meetup)）。
- [2024/09] v0.3 发布：DeepSeek MLA 快 7 倍、torch.compile 快 1.5 倍、支持多图/视频的 LLaVA-OneVision（[博客](https://lmsys.org/blog/2024-09-04-sglang-v0-3/)）。
- [2024/07] v0.2 发布：SGLang Runtime 让 Llama3 推理服务更快（对比 TensorRT-LLM、vLLM）（[博客](https://lmsys.org/blog/2024-07-25-sglang-llama3/)）。
- [2024/02] SGLang 用压缩有限状态机实现 **3 倍更快的 JSON 解码**（[博客](https://lmsys.org/blog/2024-02-05-compressed-fsm/)）。
- [2024/01] SGLang 借助 RadixAttention 实现高达 **5 倍更快的推理**（[博客](https://lmsys.org/blog/2024-01-17-sglang/)）。
- [2024/01] SGLang 为官方 **LLaVA v1.6** 发布 Demo 提供推理服务（[用法](https://github.com/haotian-liu/LLaVA?tab=readme-ov-file#demo)）。

</details>

## 关于
SGLang 是一个面向大语言模型和多模态模型的高性能推理服务框架。
它旨在从单张 GPU 到大规模分布式集群的各种场景下，提供低延迟、高吞吐的推理能力。核心特性包括：

- **高性能运行时**：提供基于 RadixAttention 的前缀缓存、零开销 CPU 调度器、预填充-解码分离（PD 分离）、投机解码、连续批处理、分页注意力、张量/流水线/专家/数据并行、结构化输出、分块预填充、量化（FP4/FP8/INT4/AWQ/GPTQ）以及多 LoRA 批处理。
- **广泛的模型支持**：支持大量语言模型（Llama、Qwen、DeepSeek、Kimi、GLM、GPT、Gemma、Mistral 等）、嵌入模型（e5-mistral、gte、mcdse）、奖励模型（Skywork）和扩散模型（WAN、Qwen-Image），并易于扩展新模型。兼容大多数 Hugging Face 模型与 OpenAI API。
- **广泛的硬件支持**：支持 NVIDIA GPU（GB200/B300/H100/A100/Spark/5090）、AMD GPU（MI355/MI300）、Intel Xeon CPU、Google TPU、昇腾 NPU 等。
- **活跃的社区**：SGLang 开源且拥有蓬勃的社区，被业界广泛采用，全球驱动超过 40 万张 GPU。
- **强化学习与后训练骨干**：SGLang 是训练许多前沿模型时经过验证的 rollout 后端，内置原生 RL 集成，并被 [**AReaL**](https://github.com/inclusionAI/AReaL)、[**Miles**](https://github.com/radixark/miles)、[**slime**](https://github.com/THUDM/slime)、[**Tunix**](https://github.com/google/tunix)、[**verl**](https://github.com/volcengine/verl) 等知名后训练框架采用。

## 快速开始
- [安装 SGLang](https://docs.sglang.io/get_started/install.html)
- [快速上手](https://docs.sglang.io/basic_usage/send_request.html)
- [后端教程](https://docs.sglang.io/basic_usage/openai_api_completions.html)
- [前端教程](https://docs.sglang.io/references/frontend/frontend_tutorial.html)
- [贡献指南](https://docs.sglang.io/developer_guide/contribution_guide.html)

## 基准测试与性能
更多内容请参阅发布博客：[v0.2 博客](https://lmsys.org/blog/2024-07-25-sglang-llama3/)、[v0.3 博客](https://lmsys.org/blog/2024-09-04-sglang-v0-3/)、[v0.4 博客](https://lmsys.org/blog/2024-12-04-sglang-v0-4/)、[大规模专家并行](https://lmsys.org/blog/2025-05-05-large-scale-ep/)、[GB200 机架级并行](https://lmsys.org/blog/2025-09-25-gb200-part-2/)、[GB300 长上下文](https://lmsys.org/blog/2026-02-19-gb300-longctx/)。

## 采用与赞助
SGLang 已大规模部署，每天在生产环境生成数万亿 token，被 xAI、NVIDIA、AMD、Intel、LinkedIn、Cursor、Oracle Cloud、Google Cloud、Microsoft Azure、AWS、Atlas Cloud、Voltage Park、Nebius、DataCrunch、Novita、RunPod、InnoMatrix、Modal、MIT、UCLA、华盛顿大学、斯坦福、UC Berkeley、清华大学、Baseten、百度、蚂蚁集团、阿里巴巴、腾讯等众多领先企业和机构信任与采用。
作为开源 LLM 推理引擎，SGLang 已成为事实上的行业标准，全球部署运行在超过 40 万张 GPU 上。
SGLang 目前托管于非营利开源组织 [LMSYS](https://lmsys.org/about/) 之下。

<img src="https://raw.githubusercontent.com/sgl-project/sgl-learning-materials/refs/heads/main/slides/adoption.png" alt="logo" width="800" margin="10px"></img>

## 联系我们
有意在大规模场景采用或部署 SGLang 的企业（包括技术咨询、赞助机会或合作洽谈），请通过 [sglang@lmsys.org](mailto:sglang@lmsys.org) 联系我们。

长期活跃的 SGLang 贡献者有机会获得编码代理赞助（如 Cursor、Claude Code 或 OpenAI Codex）。请将你最重要的提交或 PR 通过邮件发送至 [sglang@lmsys.org](mailto:sglang@lmsys.org)。

## 致谢
我们借鉴了以下项目的设计并复用了其代码：[Guidance](https://github.com/guidance-ai/guidance)、[vLLM](https://github.com/vllm-project/vllm)、[LightLLM](https://github.com/ModelTC/lightllm)、[FlashInfer](https://github.com/flashinfer-ai/flashinfer)、[Outlines](https://github.com/outlines-dev/outlines)、[LMQL](https://github.com/eth-sri/lmql)。
