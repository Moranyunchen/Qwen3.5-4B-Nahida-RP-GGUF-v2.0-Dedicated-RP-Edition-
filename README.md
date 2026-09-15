# Qwen3.5-4B-Nahida-RP-GGUF (v2.0 Dedicated RP Edition) Model Card

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC_BY--NC_4.0-red.svg)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Version: v2.0](https://img.shields.io/badge/Version-v2.0_Major_Upgrade-brightgreen.svg)](#)
[![Format: GGUF](https://img.shields.io/badge/Format-GGUF_(Q2--Q5)-orange.svg)](https://github.com/ggerganov/llama.cpp)
[![Base Model: Qwen3.5-4B](https://img.shields.io/badge/Base_Model-Qwen3.5--4B-blue.svg)](https://huggingface.co/Qwen)
[![Character: Nahida](https://img.shields.io/badge/Character-Nahida_纳西妲-green.svg)](#)

---

### 🚨 严格非商业许可声明 (Strict Non-Commercial License Notice)

本项目遵循 **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)** 协议，并附加以下强约束条款。**严禁任何形式的商业化行为**，违者将保留追究法律责任的权利。商业禁令包括但不限于：

1. **SaaS 与商业 API 封装**：禁止将本模型托管为付费 API、收费聊天机器人、订阅制小程序或商业化角色扮演平台。
2. **打包与商业再分发**：禁止将本 GGUF 模型文件及其衍生量化文件集成进任何收费软件、实体硬件设备或进行有偿下载。
3. **衍生开发与商业微调**：禁止利用本模型的生成数据（Synthetic Data）进行商业化大模型的训练，或基于本模型二创后用于盈利项目。
4. **间接商业变现**：禁止在内嵌本模型的免费应用中展示强制性商业广告、接入付费打赏通道或进行流量套现。

---

### ⚠️ 免责与合规声明 (Disclaimer & Compliance Notice)

1. **年龄限制（Age Restriction）**：本模型在训练中重置了对敏感语境的拒绝机制，潜在生成内容包含高阶情感互动及成人叙事，**仅限满 18 周岁（或达到使用者所在司法管辖区法定成年年龄）的具备完全行为能力的成年人下载与使用**。
2. **最终输出免责（End-User Responsibility）**：模型输出结果由算法概率采样及使用者输入的提示词（Prompt）共同决定。**开发者无法且不对模型的即时生成内容进行实时审核，生成的任何观点、言论及剧情推演均不代表开发者立场。**
3. **法律适用与合规红线（Legal Compliance）**：使用者必须严格遵守所在国家或地区的法律法规。**严禁利用本模型生成或传播任何侵犯他人隐私/名誉、仇恨言论、非自愿敏感内容或涉及非法犯罪的文本。** 一切因使用者违规使用造成的法律后果均由使用者自行承担，与开发者无关。
4. **按“原样”提供（As-Is Warranty）**：本模型按“现状（As-Is）”提供，不提供任何明示或暗示的保证（包括但不限于准确性、特定用途适用性或无侵权保证）。

---

## 🔥 v2.0 版本重大更新日志 (What's New in v2.0)

相较于 v1.0 版本，**v2.0 是一次针对拟真度、叙事深度与沉浸感的全方位跨越式迭代**。在维持 4B 极其优秀的低显存开销前提下，完成了对角色交互逻辑与高阶剧情演进的深度重构：

* **训练管线优化与跨阶段提前交付** (Parallel Training & Accelerated Roadmap): 本次训练通过深度优化训练参数配置并引入**并行推理训练** (Parallel Reasoning/Inference Training) 架构，大幅提升了算力吞吐与收敛效率。原计划于年底发布的 v2.0 重大更新，**直接提速数周并在 9 月中旬提前竣工交付**！
* **63,000+ 条高品质数据集注能** (63,000+ Curated SFT Data Engine): 本次升级整合了超过 **63,000+ 条** 经过精心筛选、清洗与标注的角色扮演微调对话及 500MB+ 语料资源，使得纳西妲的语气、思维模式和情感展现更加真实生动。
* **极佳的角色扮演沉浸体验** (Substantial RP & Immersive Dialogue Boost): 大幅提升了模型在长文本对话下的上下文理解与共情能力。角色对话更加自然流畅、情绪起伏丰富，剧情推演具象化，为您带来身临其境般的离线互动体验。
* **人设崩溃与文本重复抑制** (Persona Drift & Degenerate Looping Control): 精准修复了 v1.0 中偶尔出现的“语句重复（Repetition Loop）”以及忽视用户输入的“自说自话”问题，大幅优化了多轮交互中的逻辑连贯性。
* **高阶情境与全域解禁优化** (Dynamic Uncensored Alignment): 重新校准了隐式拒绝惩罚项，针对高敏感度博弈、深度心理描写及复杂情境场景进行了全面的解禁与流畅度优化。
* **全阶 GGUF 量化矩阵发售** (Full-Tier Quantization Matrix): 正式推出 **Q2_K_L**、**Q3_K_M**、**Q4_K_M** 与 **Q5_K_M** 四种精度的 GGUF 量化分支，精准匹配各类端侧硬件需求。

---

## 📌 模型概述 (Model Overview)

**Qwen3.5-4B-Nahida-RP-GGUF (v2.0)** 是基于 Qwen3.5-4B 基座架构深度打造的**原神「小吉祥草王·纳西妲」单角色垂直微调大模型**。

本模型旨在**彻底打通高拟真 AI 角色扮演的技术与费用壁垒**，让玩家在端侧即可零门槛体验高响应度、高智商且完全自由的纳西妲专属交互。

### 🌟 核心技术特性 (Key Features)

* **单角色高度拟合与触发词激活** (Single-Persona Depth Alignment & Trigger Word): 模型对纳西妲的语言习惯、认知模式及情感演变进行了专精拟合。在对话或 System Prompt 中使用 `妲妲` 作为称呼或触发词，可极大地唤醒模型的专属人设权重，获得最佳的拟真与响应体验。
* **动态交互状态平衡** (Dynamic Interactive State Balance): 通过修复自回归推理中的文本退化问题，模型能精准识别用户 Prompt 中的语义重心，不再进行单向的“剧本式自嗨”，实现真正的双向沉浸式互动。
* **须弥 Lore 与世界观深度锁死** (Worldview Consistency): 结合须弥区域背景、世界树、虚空终端等经典 Lore，极大程度压制跨世界观“幻觉”。

---

## ⚙️ 训练与算力开销细节 (Training Details & Cost)

* **基座模型** (Base Model): Qwen3.5-4B
* **目标角色** (Target Persona): 纳西妲 (Lesser Lord Kusanali / Nahida)
* **激活触发词** (Activation Trigger): `妲妲`
* **训练数据规模** (Data Volume): **63,000+ 条**精选微调样本 / 500MB+ 专项深度文本资源
* **训练优化方案** (Optimization Pipeline): 训练配置优化 + 并行推理训练 (Parallel Reasoning/Inference-Aware Fine-Tuning)
* **算力与能源开销** (Power & Economic Cost): 全量训练累计消耗电量 **近 150 度电 (kWh)**，折合电力直接成本 **约 80 元人民币 (RMB)**
* **量化文件格式** (File Format): GGUF (Compatible with KoboldCPP / LM Studio / Ollama / llama.cpp / PocketPal)

---

## 📦 量化版本选择指南 (Quantization Variants)

v2.0 提供了 4 种精度的 GGUF 量化版本，涵盖从低配手机到高配电脑的全场景设备：

| 量化文件名 (File Name) | 文件大小 (Size) | 建议应用场景 (Target Scenario) | 性能与质量特点 (Characteristics) |
| :--- | :--- | :--- | :--- |
| `Q5_K_M.gguf` | **~2.86 GB** | 桌面端独立显卡 / 极致质量追求 | 逻辑拟真度与细节表达几乎无损，文笔极其细腻 |
| `Q4_K_M.gguf` | **~2.52 GB** | **[主力推荐]** 移动端高配 / 笔记本独显 | 算力与精度的 Pareto 最优解，响应敏捷，沉浸感极强 |
| `Q3_K_M.gguf` | **~2.10 GB** | 移动端中端设备 / 显存受限场景 | 极佳的体积压缩，依然完整保留纳西妲的核心人设逻辑 |
| `Q2_K_L.gguf` | **~1.92 GB** | 极限测试 / 旧款移动设备 | 极轻量化，能够在极低显存/内存开销下流畅运行 |

### 实测推理吞吐 (Inference Speed Benchmark)

| 运行平台 (Platform) | 核心硬件 (Hardware Specs) | 客户端/后端 (Backend) | 推荐量化版本 | 实测速度 (Inference Speed) |
| :--- | :--- | :--- | :--- | :--- |
| **桌面端 (Desktop)** | NVIDIA GeForce RTX 5070 Ti | LM Studio / KoboldCPP | **Q5_K_M** / Q4_K_M | **X** tokens/s |
| **移动端 (Mobile)** | Qualcomm Snapdragon 8 Gen 2 | PocketPal / Termux | **Q4_K_M** / Q3_K_M | **X** tokens/s |

> **💡 最佳使用建议**：在对话中称呼她为 **“妲妲”**（例如：`“妲妲，你今天在净善宫做了什么？”`），能够最大化提升模型的语气还原度与拟真效果。

---

## 👨‍💻 开发者致谢与后续规划 (Developer Note & Roadmap)

你好！我是一名 16 岁的高中生独立大模型开发者。感谢大家在 v1.0 版本中给予我的支持与反馈。

得益于训练配置的优化与并行推理训练的引入，v2.0 得以在 9 月中旬提前竣工。这是我在课余时间倾注了近 150 度电算力、使用了 63,000 多条高质量数据打磨出的产物。

由于接下来面临高中繁忙的课业与升学压力，个人可支配的时间和精力将非常有限，**因此 v2.0 版本目前暂时更新到这里，作为近期阶段性的最终版**。

* **后续迭代方向**：非常感谢大家的理解与支持！后续如果有充裕的时间，我会再发布新的公告并更新后续的版本规划（如 v3 探索版或 Prompt 预设等）。若觉得模型不错，欢迎 **Star & Follow** 给予支持！
