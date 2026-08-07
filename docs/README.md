# SGLang 文档

[SGLang](https://github.com/sgl-project/sglang) 的官方文档与食谱库——SGLang 是一个面向大语言模型和视觉语言模型的高性能推理服务框架。

- **文档**：入门指南、安装说明与参考资料
- **食谱库（Cookbook）**：针对具体模型（Qwen、DeepSeek、Llama、GLM 等）在各类硬件上部署的实战配方


## 项目结构

```
.
├── docs.json              # 站点配置（导航、主题、元数据）
├── index.mdx              # 首页
├── docs/                  # 文档页面
│   └── get-started/
│       └── install.mdx    # 安装指南
├── cookbook/              # 模型部署食谱（每个模型一个 .mdx 页面）
│   ├── intro.mdx          # 食谱库概览与食谱索引
│   └── autoregressive/    # 自回归模型食谱（另有 diffusion/、omni/ 等）
│       └── DeepSeek/
│           └── DeepSeek-V4.mdx
└── src/snippets/          # 配置驱动的食谱引擎
    ├── _deployment.jsx    # 共享的部署矩阵引擎（不含任何模型特定代码）
    ├── _playground.jsx    # 共享的参数覆盖试玩引擎
    └── configs/
        └── deepseek-ai/   # 每个模型的配置 + 基准数据（按 HuggingFace 组织分文件夹）
            └── deepseek-v4.jsx
```

页面是带 YAML frontmatter 的 `.mdx` 文件。导航在 `docs.json` 中定义。

## 本地开发

### 前置条件

- Node.js >= 20

### 环境搭建

```bash
# 安装 CLI
npm i -g mint

# 在 docs/ 目录下（docs.json 所在处）启动开发服务器（热重载）
mint dev
```

预览地址：`http://localhost:3000`。

### 常用命令

```bash
mint dev            # 启动本地预览服务器
mint broken-links   # 检查失效链接
mint update         # 更新 CLI
```

## 贡献

我们欢迎各类贡献！无论你想为新模型添加食谱、改进现有文档，还是修正笔误——都欢迎提交 PR。

### 快速编辑（GitHub 网页端）

1. 在 GitHub 上打开要编辑的文件
2. 点击铅笔图标进行编辑
3. 提交一个 pull request

### 本地开发流程

```bash
# 1. Fork sgl-project/sglang 并克隆你的 fork
git clone https://github.com/<YOUR_USERNAME>/sglang.git
cd sglang/docs

# 2. 创建分支
git checkout -b my-changes

# 3. 启动开发服务器并修改
mint dev

# 4. 确认链接没有失效
mint broken-links

# 5. 提交并推送
git add <files>
git commit -m "docs: describe your change"
git push origin my-changes

# 6. 在 GitHub 上打开 pull request
```

### 添加新的食谱

自回归食谱库是**配置驱动**的：两个共享引擎——
`src/snippets/_deployment.jsx`（部署矩阵）和 `src/snippets/_playground.jsx`
（参数覆盖试玩）——**不含任何模型特定代码**。添加一个模型本质上是添加
*数据*：一份按模型区分的配置（以及可选的基准数据），两个引擎都会消费这份配置，另外再加一个导入它们的 `.mdx` 页面。可以参考 [`DeepSeek-V4`](cookbook/autoregressive/DeepSeek/DeepSeek-V4.mdx) 这个现成实例。

**推荐使用 Claude Code 技能 `/cookbook-add-model`。** 它会以交互方式引导你走完整流程：收集模型卡片 + 经过验证的 `sglang serve` 配方 → 实例化模板 → 接好导航/卡片 → 校验 → 填入实测基准数据。相关技能还有：`/cookbook-migrate-model`（迁移旧模板页面）和 `/cookbook-review-pr`（按检查清单评审食谱 PR）。

**它会创建/编辑的文件——以 DeepSeek-V4 为例：**

| 文件 | 用途 |
|---|---|
| `src/snippets/configs/deepseek-ai/deepseek-v4.jsx` | 按模型区分的配置：`supportedHardware`、`variants`、`quantizations`、`strategies`、`cells[]` 部署矩阵（每个 `硬件 × 变体 × 量化 × 策略 × 节点数` 组合下经过验证的环境与参数），以及 `playgroundFeatures`。 |
| `src/snippets/configs/deepseek-ai/deepseek-v4-benchmarks.jsx` | 每个 cell 一条实测速度/精度数据，附运行所用的 `sglang_version`。可选——拿到数据后再填。 |
| `cookbook/autoregressive/DeepSeek/DeepSeek-V4.mdx` | 页面本体：导入引擎和配置，渲染 `<Deployment>` / `<Playground>`，并补充文字（介绍 + 规格 + 许可证、配置技巧、进阶用法）。 |
| `docs.json` | 在 Cookbook → 分类 → 厂商下添加导航条目。 |
| `cookbook/autoregressive/intro.mdx` | 在分类首页添加厂商 `<Card>`。 |

注意两个文件夹命名约定：`configs/` 下按 **HuggingFace 组织** 命名（`deepseek-ai`）；`cookbook/` 下按**展示厂商**命名（`DeepSeek`）。页面只用数据把一切串起来——不需要改动引擎：

```mdx
import { Deployment } from "/src/snippets/_deployment.jsx";
import { Playground } from "/src/snippets/_playground.jsx";
import { config }     from "/src/snippets/configs/deepseek-ai/deepseek-v4.jsx";
import { benchmarks } from "/src/snippets/configs/deepseek-ai/deepseek-v4-benchmarks.jsx";

<Deployment config={config} benchmarks={benchmarks} />
<Playground config={config} />
```

在新页面上保留 `tag: NEW`，并从同厂商的其他页面上移除它（每个厂商最多 1 个），然后在 `docs/` 下做校验：`mint validate`、`mint broken-links`，最后 `mint dev` 做一次可视化冒烟测试。

> Diffusion / omni / specbundle 页面各自遵循自己的分类结构——不要强行套用自回归的配置驱动模板。

### 写作规范

- 使用主动语态："运行这个命令"，而不是"该命令应被运行"
- 以"你"来称呼读者
- 句子保持简洁——一句话一个意思
- 先给出目标，再给出步骤
- 使用一致的术语
- 包含具体的示例和代码片段

## 致谢

感谢所有为 `sglang/docs/` 原始文档和 [`sgl-cookbook`](https://github.com/sgl-project/sgl-cookbook) 原始食谱库做出贡献的作者。迁移到新版基于 Mintlify 的文档站由以下 [ACM-VIT](https://github.com/ACM-VIT) 同学主导完成：

[@Adhyan Jain](https://github.com/Adhyan-Jain)、[@Maitri-shah29](https://github.com/Maitri-shah29)、[@architnigam](https://github.com/architnigam)、[@Nakul-Sinha](https://github.com/Nakul-Sinha)、[@divyamagrawal06](https://github.com/divyamagrawal06)、[@A-Taman](https://github.com/A-Taman)、[@nimeshas](https://github.com/nimeshas)、[@IshhanKheria](https://github.com/IshhanKheria)、[@Krishang-Zinzuwadia](https://github.com/Krishang-Zinzuwadia)、[@pokymono](https://github.com/pokymono)、[@Ishitajoshii](https://github.com/Ishitajoshii)、[@AdityaVKochar](https://github.com/AdityaVKochar)

由 [@adarshxs](https://github.com/adarshxs)（ACM-VIT）以及 [@wisclmy0611](https://github.com/wisclmy0611)、[@Richardczl98](https://github.com/Richardczl98)（LMSYS）指导。

## 社区

- [GitHub](https://github.com/sgl-project/sglang)
- [Slack](https://slack.sglang.io/)
- [Discord](https://discord.gg/4ugb2t6YY2)
- [X / Twitter](https://x.com/lmsysorg)
- [LinkedIn](https://www.linkedin.com/company/sgl-project/)

## 许可证

Apache License 2.0——详见 [LICENSE](LICENSE)。
