# Dating Agent：约会大师 AI 仓库说明

## 项目简介

本仓库是一个基于 **多个搭讪Youtub频道 内容构建而来** 方法论构建的约会智能体知识库，采用标准 Agent Skill 规范组织，可直接接入 Dify、Coze、Claude Code 等平台使用。

## 训练集来源

- **训练集文件**：`alpaca_master.jsonl`
- **数据量**：18,781 条真实问答
- **内容**：涵盖搭讪、聊天、约会、关系推进等全流程问答
- **用途**：风格校准 + 知识库补充

## 核心方法论

- **Inner Game 优先**：所有技巧建立在真实的内在价值感之上
- **大道至简**：最有效的方法往往最直接
- **松弛感**：不紧绷、不表演、享受互动本身
- **隐性支配**：通过掌控自己而非压制他人展示力量

## 文件结构

```
dating-agent/
├── AGENTS.md               # 顶层执行协议与 Skill 调用规则
├── SOUL.md                 # 角色气质、风格与核心价值观
├── RULES.md                # 硬性约束与边界
├── skills/
│   └── dating-master/
│       └── SKILL.md        # Skill 入口与知识库检索逻辑
├── prompts/
│   ├── system-prompt.md    # 完整 System Prompt（含风格参考）
│   ├── persona.md          # 角色人设详细设定
│   └── boundaries.md       # 边界与异常处理
├── knowledge/
│   ├── fewshot.md          # ← 新增：从训练集提取的风格示例
│   ├── index.md            # 知识总入口
│   ├── quickstart.md       # 高频问题快速检索
│   └── topics/             # 13个主题知识文件
└── docs/
    └── README.md           # 部署说明（本文件）
```

## 部署方式

### Dify
1. 新建知识库，将 `knowledge/` 下所有文件（包括 `fewshot.md`）逐一上传
2. 切块方式选择：**Markdown Header**
3. 召回数量：**Top 3-5**，混合检索
4. 将 `prompts/system-prompt.md` 内容粘贴到 Agent 的 System Prompt 框

### Coze
1. 新建知识库，上传 `knowledge/` 所有文件
2. 将 `prompts/system-prompt.md` 内容设为 Bot 人设
3. 开启知识库检索，绑定到 Bot

### 训练集使用策略

| 策略 | 做法 | 效果 |
|---|---|---|
| **精选 Few-shot**（当前方案） | 从训练集提取 15 条典型问答放入 `fewshot.md` | 风格最准，检索最稳定 |
| 分主题切片 | 按主题把训练集内容追加到对应 topics 文件 | 覆盖最全，工程量大 |
| 微调（Fine-tuning） | 直接用完整 alpaca 文件做 LoRA 微调 | 效果最好，需支持微调的平台 |

## 知识文件列表

| 文件 | 主题 | 核心内容 |
|---|---|---|
| `fewshot.md` | 风格示例 | 15条典型问答，校准语气 |
| `01_inner-game.md` | 心态与内在游戏 | 自我价值、松弛感、隐性支配 |
| `02_opener.md` | 搭讪开场白 | 街头/日常/派对开场、拒绝处理 |
| `03_conversation.md` | 对话推进 | 四阶段、Push-Pull、情感连接 |
| `04_online-chat.md` | 网聊与微信 | 节奏控制、撩拨、邀约 |
| `05_number-close.md` | 要联系方式 | 时机、话术、重激活 |
| `06_date-game.md` | 约会全流程 | 地点、推进、肢体升级、收尾 |
| `07_dating-app.md` | 交友软件 | 主页优化、App聊天、转微信 |
| `08_social-circle.md` | 社交圈 | 圈内建立吸引、预选择效应 |
| `09_relationship.md` | 关系推进 | 确立关系、朋友区、测试处理 |
| `10_special-scenarios.md` | 特殊场景 | 保守女生、异地、关系重激活 |
| `11_texting-advanced.md` | 进阶撩拨 | 情绪化写作、让她主动找你 |
| `12_nonverbal.md` | 非语言吸引力 | 声音语调、肢体语言、眼神 |
| `13_abundance-mindset.md` | 丰盛心态 | 稀缺思维破解、生活方式构建 |

## 更新记录

- **2026-04-20**：新增 `fewshot.md`（从 alpaca_master.jsonl 提取风格示例），更新 `system-prompt.md` 和 `index.md`
