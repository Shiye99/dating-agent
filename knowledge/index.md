# Knowledge Index：知识总入口

本仓库知识库覆盖约会吸引力的完整方法论，共 13 个主题模块 + 风格示例库。

## 知识库结构

```
knowledge/
├── fewshot.md              # Mikey 风格示例（优先加载，校准语气）
├── index.md                # 本文件，知识总入口
├── quickstart.md           # 高频问题快速入口
└── topics/
    ├── 01_inner-game.md        # 心态与内在游戏
    ├── 02_opener.md            # 搭讪开场白体系
    ├── 03_conversation.md      # 对话推进四阶段
    ├── 04_online-chat.md       # 网聊与微信策略
    ├── 05_number-close.md      # 要联系方式与重激活
    ├── 06_date-game.md         # 约会全流程
    ├── 07_dating-app.md         # 交友软件完整策略
    ├── 08_social-circle.md     # 社交圈与预选择
    ├── 09_relationship.md      # 关系推进与确立
    ├── 10_special-scenarios.md # 特殊场景合集
    ├── 11_texting-advanced.md  # 进阶文字撩拨
    ├── 12_nonverbal.md         # 声音肢体语言
    └── 13_abundance-mindset.md # 丰盛心态与生活方式
```

## 检索优先级

回答问题时按以下顺序检索：
1. `fewshot.md` → 风格校准（第一优先）
2. `quickstart.md` → 高频问题快速答案
3. `topics/` 对应文件 → 深度内容

## 主题与问题类型对照

| 用户问题类型 | 优先检索文件 |
|---|---|
| 心态/自信/恐惧/价值感 | `01_inner-game.md` |
| 怎么开口/搭讪/第一句话 | `02_opener.md` |
| 线下聊天/话题/沉默 | `03_conversation.md` |
| 微信/网聊/回复节奏 | `04_online-chat.md` |
| 要号码/聊死了/不回消息 | `05_number-close.md` |
| 约会/见面/去哪/收尾 | `06_date-game.md` |
| 第二三次约会/亲吻 | `06_date-game.md` + `09_relationship.md` |
| Tinder/探探/主页/App聊天 | `07_dating-app.md` |
| 朋友介绍/聚会/社交圈 | `08_social-circle.md` |
| 表白/朋友区/确立关系 | `09_relationship.md` |
| 测试/忽冷忽热/Drama | `09_relationship.md` |
| 保守女生/异地/挽回 | `10_special-scenarios.md` |
| 进阶撩拨/让她主动 | `11_texting-advanced.md` |
| 声音/肢体语言/眼神 | `12_nonverbal.md` |
| 丰盛心态/自我提升 | `13_abundance-mindset.md` |

## 训练集信息

- **原始文件**：`knowledge/raw/alpaca_master.jsonl`
- **数据量**：18,781 条问答
- **用途**：风格校准与真实案例参考
- **精选示例**：`fewshot.md`（15条典型问答）

## 完整目录结构

```
knowledge/
├── raw/
│   └── alpaca_master.jsonl    # 训练集原始文件（12MB）
├── fewshot.md                 # 风格示例（从训练集提取）
├── index.md                   # 本文件
├── quickstart.md              # 高频问题速查
└── topics/                    # 主题知识文件
```
