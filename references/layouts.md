# 布局骨架 — 竖版海报 (600px × 850px+)

本文档定义 6 种竖版海报布局骨架，每种均可直接粘贴到 `<div class="poster">` 内部使用。

> **使用方式**：选择合适的布局 → 复制 HTML 代码块 → 粘贴到 `.poster` 容器内 → 替换文字内容 → 搭配对应风格的 CSS 变量即可。

---

## Layout 1: 中心聚焦型 (Center Focus)

### 适用场景
简洁的公告、发布会、品牌活动、产品上线。内容少但需要仪式感。

### ASCII 示意图

```
┌──────────────────────────┐
│                          │
│                          │
│         [badge]          │
│                          │
│       ═══ 主标题 ═══      │
│         副标题            │
│                          │
│       ── 分隔线 ──        │
│                          │
│     📅 时间  📍 地点      │
│                          │
│                          │
│     ─── 底部信息 ───      │
└──────────────────────────┘
```

### HTML 代码

```html
<!-- Layout 1: 中心聚焦型 -->
<div class="badge" style="margin: 0 auto 24px;">活动类型</div>

<h1 class="main-title" style="text-align: center;">主标题文字</h1>
<p class="subtitle" style="text-align: center;">副标题或一句话描述</p>

<div class="divider" style="margin: 32px auto; max-width: 120px;"></div>

<div class="info-list" style="display: flex; flex-direction: column; align-items: center; gap: 12px;">
  <div class="info-row" style="justify-content: center;">
    <span class="info-icon">📅</span>
    <div>
      <span class="info-label">时间</span>
      <span class="info-value">2026年6月15日 14:00</span>
    </div>
  </div>
  <div class="info-row" style="justify-content: center;">
    <span class="info-icon">📍</span>
    <div>
      <span class="info-label">地点</span>
      <span class="info-value">北京·某某空间</span>
    </div>
  </div>
</div>

<div class="footer">
  <span>主办方名称</span>
  <span>www.example.com</span>
</div>
```

### 注意事项
- 利用 flexbox 的 `align-items: center` 让所有内容垂直居中
- 上下留白是关键，`padding-top` 建议 ≥ 80px
- 分隔线控制在 80-120px 宽度，不要撑满
- 信息行最多 2-3 条，过多会破坏留白感

---

## Layout 2: 顶部重心型 (Top Heavy)

### 适用场景
需要强调标题/主视觉的场景，如品牌发布、年度大会、概念活动。

### ASCII 示意图

```
┌──────────────────────────┐
│  [badge]                 │
│                          │
│  ████████████████████    │
│  ██  巨 大 标 题  ██    │
│  ████████████████████    │
│                          │
│  副标题描述文字           │
│                          │
│  ════════════════════    │
│                          │
│  时间 ████  地点 ████    │
│  票务 ████  费用 ████    │
│                          │
│  ─── 底部小字 ───        │
└──────────────────────────┘
```

### HTML 代码

```html
<!-- Layout 2: 顶部重心型 -->
<div class="badge">活动类型</div>

<h1 class="main-title" style="font-size: 58px; margin-bottom: 16px;">巨大标题文字</h1>
<p class="subtitle" style="margin-bottom: 48px;">副标题描述文字，可以稍微长一些来平衡上方的视觉重量</p>

<div class="divider"></div>

<div class="info-grid" style="display: grid; grid-template-columns: 1fr 1fr; gap: 16px 24px; margin-bottom: auto;">
  <div class="info-row" style="flex-direction: column; align-items: flex-start;">
    <span class="info-label">时间</span>
    <span class="info-value">2026年6月15日</span>
  </div>
  <div class="info-row" style="flex-direction: column; align-items: flex-start;">
    <span class="info-label">地点</span>
    <span class="info-value">北京·国家会议中心</span>
  </div>
  <div class="info-row" style="flex-direction: column; align-items: flex-start;">
    <span class="info-label">票务</span>
    <span class="info-value">免费报名</span>
  </div>
  <div class="info-row" style="flex-direction: column; align-items: flex-start;">
    <span class="info-label">规模</span>
    <span class="info-value">限额 300 人</span>
  </div>
</div>

<div class="footer">
  <span>主办方名称</span>
  <span>扫码报名 →</span>
</div>
```

### 注意事项
- 主标题字号推荐 56-64px，确保视觉重心在上半部分
- 信息网格用 2 列 grid 布局，紧凑但清晰
- 副标题与信息区之间的 divider 是视觉分割的关键
- 底部保持极简，不要与上方抢注意力

---

## Layout 3: 信息密集型 (Info Rich)

### 适用场景
活动详情多的场景 —— 多位嘉宾、多个议题、多场次安排、工作坊等。

### ASCII 示意图

```
┌──────────────────────────┐
│  [badge]   主标题        │
│  副标题描述              │
│  ════════════════════    │
│  📅 时间: xxxxx         │
│  📍 地点: xxxxx         │
│  🎫 票务: xxxxx         │
│  ════════════════════    │
│  嘉宾 ┌──┐ ┌──┐ ┌──┐   │
│       │  │ │  │ │  │   │
│       └──┘ └──┘ └──┘   │
│  ════════════════════    │
│  简介描述文字            │
│  [CTA 按钮]             │
│  ─── 底部 ───           │
└──────────────────────────┘
```

### HTML 代码

```html
<!-- Layout 3: 信息密集型 -->
<div class="badge-area">
  <span class="badge">活动类型</span>
</div>

<h1 class="main-title" style="font-size: 42px; margin-bottom: 8px;">活动主标题</h1>
<p class="subtitle">副标题或活动口号，一句话说明</p>

<div class="divider"></div>

<div class="info-list">
  <div class="info-row">
    <div class="info-icon">📅</div>
    <div>
      <span class="info-label">时间</span>
      <span class="info-value">2026年6月15日 14:00 – 18:00</span>
    </div>
  </div>
  <div class="info-row">
    <div class="info-icon">📍</div>
    <div>
      <span class="info-label">地点</span>
      <span class="info-value">北京·某某空间 3F</span>
    </div>
  </div>
  <div class="info-row">
    <div class="info-icon">🎫</div>
    <div>
      <span class="info-label">票务</span>
      <span class="info-value">早鸟票 ¥99 / 现场 ¥199</span>
    </div>
  </div>
</div>

<div class="divider"></div>

<div class="speakers" style="margin-bottom: 24px;">
  <div class="speaker">
    <div class="speaker-avatar">张</div>
    <div>
      <div class="speaker-name">张明远</div>
      <div class="speaker-role">某公司 · CTO</div>
    </div>
  </div>
  <div class="speaker">
    <div class="speaker-avatar">李</div>
    <div>
      <div class="speaker-name">李思源</div>
      <div class="speaker-role">某机构 · 研究员</div>
    </div>
  </div>
</div>

<p class="description">活动简介描述文字。可以 2-3 句话概括活动核心内容和亮点。</p>

<div class="footer">
  <span>主办方名称</span>
  <span>报名链接 / 二维码</span>
</div>
```

### 注意事项
- 标题字号适当缩小（40-44px）为信息区腾出空间
- 使用多个 divider 做视觉分段
- 嘉宾区用 flex 横排，2-3 人为宜
- 如果嘉宾超过 3 人，改用列表式而非卡片式
- description 控制在 2-3 行以内

---

## Layout 4: 左右分栏型 (Split)

### 适用场景
需要视觉冲击力的场景 —— 艺术展览、品牌活动、产品发布。左侧纯装饰，右侧承载信息。

### ASCII 示意图

```
┌────────────┬─────────────────┐
│            │                 │
│            │  [badge]        │
│   渐变色   │                 │
│   装饰区   │  主标题         │
│            │  副标题         │
│   40%      │                 │
│            │  ── 分隔 ──     │
│  （可放    │                 │
│   大数字   │  📅 时间        │
│   或符号） │  📍 地点        │
│            │                 │
│            │  简介文字       │
│            │                 │
│            │  ─── 底部 ───   │
└────────────┴─────────────────┘
```

### HTML 代码

```html
<!-- Layout 4: 左右分栏型 -->
<!-- 注意：此布局需要将 .poster 的 padding 设为 0，flex-direction 改为 row -->
<div class="poster-left" style="width: 40%; background: linear-gradient(180deg, var(--primary, #0066ff), var(--accent, #00d4ff)); display: flex; align-items: center; justify-content: center; position: relative; overflow: hidden;">
  <div style="font-size: 120px; font-weight: 900; opacity: 0.15; color: #fff; font-family: 'Inter', sans-serif;">AI</div>
</div>

<div class="poster-right" style="width: 60%; padding: 48px 36px; display: flex; flex-direction: column;">
  <div class="badge" style="margin-bottom: 24px;">活动类型</div>

  <h1 class="main-title" style="font-size: 36px; margin-bottom: 8px;">活动主标题</h1>
  <p class="subtitle" style="margin-bottom: 32px;">副标题或一句话说明</p>

  <div class="divider"></div>

  <div class="info-list" style="margin-bottom: 24px;">
    <div class="info-row">
      <span class="info-icon">📅</span>
      <div>
        <span class="info-label">时间</span>
        <span class="info-value">2026年6月15日</span>
      </div>
    </div>
    <div class="info-row">
      <span class="info-icon">📍</span>
      <div>
        <span class="info-label">地点</span>
        <span class="info-value">线上直播</span>
      </div>
    </div>
  </div>

  <p class="description" style="flex: 1;">简短活动描述，1-2 句话即可。</p>

  <div class="footer" style="border-top: 1px solid rgba(0,0,0,0.08);">
    <span>主办方</span>
    <span>www.example.com</span>
  </div>
</div>
```

### 注意事项
- `.poster` 容器需额外设置 `flex-direction: row; padding: 0;`
- 左侧装饰区不放文字内容，只做视觉
- 左侧可放：渐变色块、大号数字/符号、几何图案
- 右侧字号整体偏小（标题 34-40px），因为空间只有 60%
- 在深色主题下，左侧用亮色渐变；浅色主题下，左侧用深色/饱和色

---

## Layout 5: 卡片堆叠型 (Card Stack)

### 适用场景
多话题活动、多场次安排、培训课程、系列活动。每张卡片承载独立信息块。

### ASCII 示意图

```
┌──────────────────────────┐
│  [badge]   主标题        │
│  副标题                  │
│                          │
│  ┌────────────────────┐  │
│  │ 📅 时间 + 📍 地点  │  │
│  └────────────────────┘  │
│                          │
│  ┌────────────────────┐  │
│  │ 👤 嘉宾介绍       │  │
│  └────────────────────┘  │
│                          │
│  ┌────────────────────┐  │
│  │ 📝 活动简介       │  │
│  └────────────────────┘  │
│                          │
│  ─── 底部 ───            │
└──────────────────────────┘
```

### HTML 代码

```html
<!-- Layout 5: 卡片堆叠型 -->
<div class="badge-area">
  <span class="badge">活动类型</span>
</div>

<h1 class="main-title" style="font-size: 40px; margin-bottom: 8px;">活动主标题</h1>
<p class="subtitle" style="margin-bottom: 28px;">副标题或活动口号</p>

<!-- 卡片 1: 时间地点 -->
<div class="card" style="background: rgba(255,255,255,0.05); border: 1px solid rgba(255,255,255,0.1); border-radius: 12px; padding: 20px; margin-bottom: 16px;">
  <div class="info-row" style="margin-bottom: 10px;">
    <span class="info-icon">📅</span>
    <div>
      <span class="info-label">时间</span>
      <span class="info-value">2026年6月15日 14:00</span>
    </div>
  </div>
  <div class="info-row">
    <span class="info-icon">📍</span>
    <div>
      <span class="info-label">地点</span>
      <span class="info-value">北京·某某空间</span>
    </div>
  </div>
</div>

<!-- 卡片 2: 嘉宾 -->
<div class="card" style="background: rgba(255,255,255,0.05); border: 1px solid rgba(255,255,255,0.1); border-radius: 12px; padding: 20px; margin-bottom: 16px;">
  <div style="font-size: 12px; letter-spacing: 2px; text-transform: uppercase; opacity: 0.5; margin-bottom: 12px;">嘉宾阵容</div>
  <div class="speakers" style="flex-direction: column; gap: 12px;">
    <div class="speaker">
      <div class="speaker-avatar">张</div>
      <div>
        <div class="speaker-name">张明远</div>
        <div class="speaker-role">某公司 · 技术总监</div>
      </div>
    </div>
    <div class="speaker">
      <div class="speaker-avatar">王</div>
      <div>
        <div class="speaker-name">王晓芳</div>
        <div class="speaker-role">某大学 · 教授</div>
      </div>
    </div>
  </div>
</div>

<!-- 卡片 3: 简介 -->
<div class="card" style="background: rgba(255,255,255,0.05); border: 1px solid rgba(255,255,255,0.1); border-radius: 12px; padding: 20px; margin-bottom: auto;">
  <p class="description" style="margin: 0;">活动简介文字。2-3 句话概括核心内容和参加价值。</p>
</div>

<div class="footer">
  <span>主办方名称</span>
  <span>限额报名中</span>
</div>
```

### 注意事项
- 卡片背景用半透明色（深色主题用 `rgba(255,255,255,0.05)`，浅色主题用 `rgba(0,0,0,0.03)`）
- 卡片圆角统一为 12px，间距统一为 16px
- 卡片内部 padding 20px，信息紧凑排列
- 最多 3-4 张卡片，超过则考虑合并信息
- 卡片边框用 1px 半透明线条，不要太重

---

## Layout 6: 大字报型 (Statement)

### 适用场景
概念发布、哲学/文化活动、艺术展、品牌宣言。极少信息，纯氛围感。

### ASCII 示意图

```
┌──────────────────────────┐
│                          │
│  [小标签]                │
│                          │
│                          │
│  ██████████████████████  │
│  ██                  ██  │
│  ██   超 大 标 题    ██  │
│  ██                  ██  │
│  ██████████████████████  │
│                          │
│                          │
│                          │
│                          │
│  2026.06.15 · 某某空间   │
└──────────────────────────┘
```

### HTML 代码

```html
<!-- Layout 6: 大字报型 -->
<div class="badge" style="margin-bottom: auto; opacity: 0.6; font-size: 11px;">小标签文字</div>

<h1 class="main-title" style="font-size: 72px; line-height: 1.05; margin-bottom: auto; letter-spacing: -2px;">
  超大<br>标题文字
</h1>

<div class="footer" style="justify-content: flex-start; gap: 24px;">
  <span class="info-value" style="font-size: 14px; opacity: 0.6;">2026.06.15</span>
  <span style="opacity: 0.3;">·</span>
  <span class="info-value" style="font-size: 14px; opacity: 0.6;">某某空间</span>
</div>
```

### 注意事项
- 标题字号 64-80px，是整张海报的绝对主角
- 利用 `margin-bottom: auto` 将标题和底部信息撑开
- 底部只保留一行：日期 + 地点，用 `·` 分隔
- badge 可省略，如保留则 opacity 降低不抢风头
- 标题可用 `<br>` 手动换行，制造节奏感
- 标题适合 2-6 个字的短语，太长就不适合此布局
- 装饰元素要极度克制，最多一个渐变圆

---

## 布局选择指南

| 信息量 | 推荐布局 | 理由 |
|--------|----------|------|
| 极少（标题+日期） | Layout 6 大字报型 | 留白最大化，氛围感最强 |
| 少（标题+时间+地点） | Layout 1 中心聚焦型 | 对称平衡，简洁有力 |
| 中等（+嘉宾+简介） | Layout 2 顶部重心型 | 信息有网格化，标题仍突出 |
| 较多（+议程+多嘉宾） | Layout 3 信息密集型 | 分段清晰，信息全面 |
| 多（多话题/多场次） | Layout 5 卡片堆叠型 | 卡片隔离信息，不混乱 |
| 需视觉冲击 | Layout 4 左右分栏型 | 色块+文字，视觉张力强 |
