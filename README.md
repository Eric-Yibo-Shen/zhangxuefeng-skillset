# zhangxuefeng-skillset

<div align="center">

**张雪峰 · Zhang Xuefeng**

*1984年11月28日 — 2026年3月24日*

---

*他用一张嘴，替无数普通家庭的孩子打探了前路。*
*我们用AI Agent，把这条通向未来的路铺向远方。*

---

[![License: CC BY 4.0](https://img.shields.io/badge/Knowledge-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![License: MIT](https://img.shields.io/badge/Code-MIT-yellow.svg)](LICENSE-CODE)
[![OpenClaw Skills](https://img.shields.io/badge/OpenClaw-Skills%20Compatible-blue.svg)](https://docs.openclaw.ai/skills)
[![WeChat Ready](https://img.shields.io/badge/WeChat-Ready-07C160.svg)](#部署到微信)
[![贡献欢迎](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](CONTRIBUTING.md)

</div>

---

## 这是什么

中国每年超过1200万高考考生，大量来自信息资源匮乏的普通家庭。**志愿填报的信息差，不应该靠花钱来弥补。**

本项目是一套完全开源的高考志愿填报决策知识库，可以：
- 直接阅读使用（Markdown格式）
- 一键部署为 **OpenClaw Skills**，接入微信/企业微信/QQ，让普通家长用熟悉的方式获得AI顾问服务
- 导入任意RAG平台（Dify、FastGPT、RagFlow等）构建问答机器人

**核心差异**：本项目不只是数据匹配工具（分数→学校），而是一套**决策框架**——帮助普通家庭用正确的思维顺序做志愿决策，同时纳入AI时代的行业前景校正。

---

## 快速开始

### 方式一：直接阅读知识库

进入 [`knowledge/`](knowledge/) 目录，按需阅读：

| 文件 | 内容 |
|------|------|
| [`00_ai_era_correction.md`](knowledge/00_ai_era_correction.md) | ⭐ AI时代专业选择动态校正（2026-2030视角） |
| [`01_major_selection.md`](knowledge/01_major_selection.md) | 专业选择决策框架（高确定性 vs 高风险） |
| [`02_volunteer_strategy.md`](knowledge/02_volunteer_strategy.md) | 志愿填报操作框架（冲稳保、城市优先级） |
| [`03_employment_outlook.md`](knowledge/03_employment_outlook.md) | 就业路径分析（五条主路径真实评估） |
| [`04_university_selection.md`](knowledge/04_university_selection.md) | 院校选择参考框架（各分数段逻辑） |
| [`05_study_life_principles.md`](knowledge/05_study_life_principles.md) | 备考策略与决策底层逻辑 |
| [`06_university_life_planning.md`](knowledge/06_university_life_planning.md) | 大学在校阶段规划（英语、社团、考研导师、人脉） |
| [`07_new_gaokao_subject_selection.md`](knowledge/07_new_gaokao_subject_selection.md) | 新高考选科决策（3+1+2模式，物理vs历史） |

### 方式二：部署为 OpenClaw Skills（推荐·接入微信）

```bash
# 1. 克隆仓库
git clone https://github.com/Eric-Yibo-Shen/zhangxuefeng-skillset.git
cd zhangxuefeng-skillset

# 2. 安装到 OpenClaw
openclaw skills install ./skills/gaokao-mentor.skill

# 3. 验证安装
openclaw skills list
```

部署后在微信/企业微信中 `@机器人` 直接对话即可。详见 [部署指南](deploy/DEPLOY.md)。

### 方式三：导入 RAG 平台

将 `knowledge/` 下所有 `.md` 文件导入你的RAG系统，使用 [`prompts/system_prompt.md`](prompts/system_prompt.md) 作为系统提示词。

---

## 项目结构

```
zhangxuefeng-skillset/
├── README.md
├── CONTRIBUTING.md
├── LICENSE                      # CC BY 4.0（知识内容）
├── LICENSE-CODE                 # MIT（代码部分）
│
├── skills/
│   └── gaokao-mentor.skill      # OpenClaw 可直接安装的 skill
│
├── knowledge/                   # 核心知识库（8个模块，完全原创表述）
│   ├── 00_ai_era_correction.md  # AI时代校正框架 ⭐
│   ├── 01_major_selection.md
│   ├── 02_volunteer_strategy.md
│   ├── 03_employment_outlook.md
│   ├── 04_university_selection.md
│   ├── 05_study_life_principles.md
│   ├── 06_university_life_planning.md   # 大学在校规划（新增）
│   └── 07_new_gaokao_subject_selection.md  # 新高考选科（新增）
│
├── prompts/
│   └── system_prompt.md         # AI顾问系统提示词（含四步决策框架）
│
├── deploy/
│   └── DEPLOY.md                # 完整部署指南（腾讯云/自托管/Dify）
│
└── .github/
    ├── ISSUE_TEMPLATE/
    └── workflows/validate.yml   # PR自动验证
```

---

## 核心框架：决策顺序

```
第一步：先定可行集
  → 用分数+省份确定实际能报的院校层次
  → 特殊通道（体育/艺术特长）优先核查

第二步：目标倒推
  → 先问"最终想要什么保障"
  → 再选能达到这个目标的最短路径

第三步：AI时代校正
  → 核查每个候选专业的AI冲击评级（见 00_ai_era_correction.md）

输出规范：最多3个选项 + 明确切换条件
  → "分够X就选A，分不够就选B"
  → 不给模糊备选清单
```

---

## 如何贡献

欢迎以下形式的贡献：纠错、补充专业/院校分析、贡献各省录取数据、分享真实案例（脱敏处理）。

请参阅 [CONTRIBUTING.md](CONTRIBUTING.md)。

---

## 许可证

- **知识内容**（`knowledge/`、`prompts/`）：[CC BY 4.0](LICENSE) — 署名即可自由使用、修改、分发
- **代码**（`skills/`、`deploy/`、`.github/`）：[MIT](LICENSE-CODE)

---

## 致谢

<div align="center">

### 🕯️ 张雪峰先生（1984.11.28 — 2026.03.24）

</div>

本项目以张雪峰先生的名字命名，以纪念他为中国普通家庭消除教育信息差所做出的贡献。

知识库的底层框架——城市优先于学校、学校优先于专业；就业确定性优先于兴趣；特长是工具而非包袱；先定可行集再做决策——这些判断逻辑，是对他十余年公开输出的提炼与传承。

本项目知识内容为社区独立原创表述，与峰学蔚来教育科技有限公司无关联，不代表其商业立场。

---

### 相关开源项目

**[gaokao-mentor-wisdom](https://github.com/dongsheng123132/gaokao-mentor-wisdom)** · dongsheng123132

该项目对张雪峰公开语录进行了系统整理，其六大分类框架（专业选择、就业前景、人生哲理、院校推荐、学习建议、志愿填报策略）为本项目知识库的模块划分提供了重要的组织视角参考。

> 注：本项目知识库内容为社区独立重新表述，未直接引用该仓库中的具体语录原文，以规避版权风险。两个项目定位不同，可互为补充。

---

**[zhang-xuefeng-memorial](https://github.com/bcefghj/zhang-xuefeng-memorial)** · bcefghj

以张雪峰精神为导师的纪念性知识库项目，包含专业就业分析、志愿填报实战指南、AI时代前景、寒门学子生存指南四个知识模块。本项目从中提炼了：城市优先级层级划分、院校录取规则三种类型（分数优先/志愿优先/专业级差）、中外合作办学策略、行业特色院校隐性价值、大类招生策略、大学四年阶段规划，以及"五大坑"框架等新知识点。

---

**[Xue-Feng-Skill](https://github.com/SPA3K/Xue-Feng-Skill)** · SPA3K

使用 OpenAI Whisper 对张雪峰 Bilibili 公开视频进行 ASR 转录，覆盖 137 个视频（约 298,367 字符原始语料），并提炼出六步决策框架。本项目 `06_university_life_planning`、`07_new_gaokao_subject_selection` 两个新模块，以及对现有模块的细粒度补充（口腔医学路径、三阶段人生规划、选科策略、色觉障碍限制、10-30-60人脉模型等），主要来源于对该仓库 ASR 语料的纠错提炼。
