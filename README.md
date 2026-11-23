# swiss-typography · 瑞士国际主义公众号排版 Skill

给 Claude Code（及兼容 [Agent Skills](https://agentskills.io) 标准的 AI 工具）用的排版 skill：
按微信视频号「皮皮爱写作」《公众号排版笔记【第62期】· 瑞士国际主义》的方法和约束，
把公众号推文排成"专业又不花哨"的瑞士国际主义风格，直接产出可粘贴进公众号编辑器的内联样式 HTML。

**四条规矩（硬约束）：**

| # | 规矩 | 核心规格 |
|---|---|---|
| 01 | 全部靠左 | 标题/正文/引用左对齐同一条线，禁止居中 |
| 02 | 字号差四 | 16 → 20 → 24 → 32（引用 18），逐级 +4 |
| 03 | 黑线横切 | 2px 黑线；二级标题上方压一道；分隔线上下各空 50px |
| 04 | 红线竖点 | 全篇一种红（#D00013）：一级标题前 8px 红条、引用前细红线 |

## 安装（Claude Code）

```bash
git clone https://github.com/chenkaihao/swiss-typography.git ~/.claude/skills/swiss-typography
```

项目级使用可 clone 到 `<repo>/.claude/skills/swiss-typography`。

## 使用

直接对 Claude Code 说：

> 用 swiss-typography 给这篇产品介绍排个公众号版式：……

或显式调用 `/swiss-typography`。Claude 会按 SKILL.md 的工作流定层级 → 套规格 → 输出 HTML → 过自检清单。

## 目录

```
swiss-typography/
├── SKILL.md                  # skill 本体（方法 + 四条铁律 + 工作流 + 自检清单）
├── examples.md               # 原视频样章的结构映射（少样本参照）
└── references/
    ├── spec.md               # 完整规格、设计原理、逐条出处、口播逐字稿
    └── template.html         # 可直接粘贴公众号的内联样式 HTML 模板
```

## 规格来源与可信度

全部数字规格（16/18/20/24/32px、+4 阶梯、2px 黑线、50px 间距、8px 红条、细红线、#D00013 红）
均逐帧核对原视频的**画面标注**与**口播逐字稿**（whisper medium 转写 + 字幕校对），无一处为臆造值。
详见 [references/spec.md](references/spec.md) 第 8 节。

来源视频：微信视频号「皮皮爱写作」《公众号排版笔记【第62期】》，排版工具为「句方便」编辑器的「瑞士国际主义」主题。

## License

MIT
