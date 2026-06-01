# Poster Generator

一个用于生成精美 HTML 海报的 Codex 技能。

这个技能可以根据用户提供的标题、时间、地点、简介、风格偏好等信息，生成一张可直接预览、截图或导出为图片的 HTML 海报。适合活动宣传、节日祝福、课程推广、邀请函、促销海报、品牌概念图等场景。

## 主要能力

- 根据简单描述生成完整 HTML 海报
- 支持竖版、横版、正方形等常见海报比例
- 内置 6 套视觉风格系统
- 内置 18 套主题色预设
- 提供布局骨架、主题色、质量检查清单
- 支持儿童节、亲子、绘本感等童趣复古字绘风格
- 当用户要求严肃、正式、商务、庄重、专业等画风时，会自动禁用童趣风格

## 内置风格

| 风格 | 说明 | 模板 |
|---|---|---|
| Style A · 极简雅致 | 留白、细线、干净高级 | `assets/template-minimal.html` |
| Style B · 商务专业 | 深色、结构感、正式稳重 | `assets/template-business.html` |
| Style C · 科技未来 | 深色背景、发光、网格、科技感 | `assets/template-tech.html` |
| Style D · 活力缤纷 | 明亮、多彩、年轻活泼 | `assets/template-vibrant.html` |
| Style E · 节日庆典 | 红金、中国风、仪式感 | `assets/template-festive.html` |
| Style F · 童趣复古字绘 | 手绘大字、旧纸纹理、儿童绘本感 | `assets/template-retro-child.html` |

## 仓库结构

```text
poster-generator/
├── SKILL.md                 # 技能主说明，包含触发词、工作流程、风格选择规则
├── agents/
│   └── openai.yaml          # 技能展示元数据
├── assets/                  # HTML 海报模板
│   ├── template-minimal.html
│   ├── template-business.html
│   ├── template-tech.html
│   ├── template-vibrant.html
│   ├── template-festive.html
│   └── template-retro-child.html
└── references/              # 主题色、布局、检查清单
    ├── themes.md
    ├── layouts.md
    ├── layouts-horizontal.md
    └── checklist.md
```

## 使用方式

把这个仓库作为 Codex 技能安装或复制到本地技能目录后，在对话中提出类似需求即可触发：

```text
帮我做一张六一儿童节海报，童趣复古字绘风格，标题是“六一快乐”。
```

也可以这样描述：

```text
生成一个极简雅致的活动海报，标题是“设计分享会”，时间是 6 月 15 日晚上 7 点。
```

## 设计规则

- 默认优先生成 HTML 海报，而不是图片文件
- 用户没有指定风格时，优先选择极简雅致风格
- 主题色必须从 `references/themes.md` 的预设中选择
- 不建议随意自定义颜色，避免破坏整体视觉协调
- 一张海报只使用一套风格，不混用模板
- 严肃、正式、商务、政务、峰会等场景禁用童趣复古字绘风格

## 适用场景

- 活动海报
- 节日祝福图
- 邀请函
- 课程宣传图
- 产品发布海报
- 市集/工作坊/沙龙宣传图
- 儿童节、亲子、绘本、幼儿园活动海报

## 不适用场景

- 像素级复刻设计稿
- 复杂插画绘制
- 动态视频海报
- 需要专业印刷出血和 CMYK 管理的印刷文件

## 说明

这个仓库是一个 Codex 技能仓库，核心是 `SKILL.md` 和配套模板资源。README 用于帮助 GitHub 访问者快速理解仓库内容，不影响技能本身的运行。
