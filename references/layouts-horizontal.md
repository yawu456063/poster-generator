# 布局骨架 — 横版 & 正方形海报

本文档为横版海报（960px × 540px）和正方形海报（600px × 600px）提供布局骨架。

---

## 横版海报 (960px × 540px)

### H-Layout 1: 左右分割型 (Horizontal Split)

#### 适用场景
线上活动横幅、社交媒体封面、宣传 banner。左侧视觉区 + 右侧信息区。

#### ASCII 示意图

```
┌─────────────────────────┬────────────────────────────────────┐
│                         │                                    │
│                         │  [badge]                           │
│     视觉装饰区          │                                    │
│     (渐变/图案/         │  主标题                            │
│      大号字符)          │  副标题                            │
│                         │                                    │
│       45%               │  📅 时间  📍 地点                  │
│                         │                                    │
│                         │  底部信息                           │
└─────────────────────────┴────────────────────────────────────┘
```

#### HTML 代码

```html
<!-- H-Layout 1: 横版左右分割型 -->
<!-- .poster 需设置: width: 960px; min-height: 540px; flex-direction: row; padding: 0; -->
<div class="poster-left" style="width: 45%; background: linear-gradient(135deg, var(--primary, #0066ff), var(--accent, #00d4ff)); display: flex; align-items: center; justify-content: center; position: relative; overflow: hidden;">
  <!-- 装饰：大号文字或几何图形 -->
  <div style="font-size: 140px; font-weight: 900; opacity: 0.12; color: #fff; font-family: 'Inter', sans-serif; line-height: 1;">∞</div>
</div>

<div class="poster-right" style="width: 55%; padding: 40px 36px; display: flex; flex-direction: column; justify-content: center;">
  <div class="badge" style="margin-bottom: 20px;">活动类型</div>

  <h1 class="main-title" style="font-size: 36px; margin-bottom: 8px;">活动主标题</h1>
  <p class="subtitle" style="margin-bottom: 28px; font-size: 14px;">副标题或一句话描述，简明扼要</p>

  <div class="divider" style="margin-bottom: 20px;"></div>

  <div class="info-list" style="display: flex; gap: 24px; margin-bottom: auto;">
    <div class="info-row" style="flex-direction: column; align-items: flex-start;">
      <span class="info-label">📅 时间</span>
      <span class="info-value" style="font-size: 14px;">2026.06.15 14:00</span>
    </div>
    <div class="info-row" style="flex-direction: column; align-items: flex-start;">
      <span class="info-label">📍 地点</span>
      <span class="info-value" style="font-size: 14px;">线上直播</span>
    </div>
  </div>

  <div class="footer" style="padding-top: 16px;">
    <span>主办方名称</span>
    <span>www.example.com</span>
  </div>
</div>
```

#### 注意事项
- 横版空间扁平，标题字号缩小到 34-40px
- 左侧装饰区不承载可读信息
- 右侧信息区垂直居中（`justify-content: center`）
- 信息行改为横排以节省纵向空间
- 适合在社交媒体头图、邮件 banner 中使用

---

### H-Layout 2: 上下分割型 (Horizontal Stack)

#### 适用场景
活动直播封面、会议横幅、网站 hero banner。上方大标题 + 下方信息栏。

#### ASCII 示意图

```
┌──────────────────────────────────────────────────────────────┐
│  [badge]                                                     │
│                                                              │
│                 主标题（大号居中）                              │
│                 副标题                                        │
│                                                              │
├──────────────────────────────────────────────────────────────┤
│  📅 2026.06.15    📍 某某空间    🎫 免费     主办方 logo     │
└──────────────────────────────────────────────────────────────┘
```

#### HTML 代码

```html
<!-- H-Layout 2: 横版上下分割型 -->
<!-- .poster 需设置: width: 960px; min-height: 540px; padding: 48px 56px; -->
<div class="badge" style="margin-bottom: 16px;">活动类型</div>

<div style="flex: 1; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center;">
  <h1 class="main-title" style="font-size: 48px; margin-bottom: 12px;">活动主标题居中展示</h1>
  <p class="subtitle" style="max-width: 600px;">副标题描述文字，保持在两行以内，居中对齐效果最佳</p>
</div>

<div class="divider" style="margin: 0;"></div>

<div class="footer" style="padding-top: 24px; display: flex; align-items: center; justify-content: center; gap: 36px; flex-wrap: wrap;">
  <div class="info-row" style="margin: 0;">
    <span class="info-icon" style="font-size: 16px;">📅</span>
    <span class="info-value" style="font-size: 14px;">2026年6月15日 14:00</span>
  </div>
  <div class="info-row" style="margin: 0;">
    <span class="info-icon" style="font-size: 16px;">📍</span>
    <span class="info-value" style="font-size: 14px;">北京·某某空间</span>
  </div>
  <div class="info-row" style="margin: 0;">
    <span class="info-icon" style="font-size: 16px;">🎫</span>
    <span class="info-value" style="font-size: 14px;">免费参加</span>
  </div>
  <span style="opacity: 0.4; font-size: 13px;">主办方名称</span>
</div>
```

#### 注意事项
- 上方 70% 空间留给标题，底部 30% 做信息栏
- 底部信息栏用 flex + gap 横排所有信息
- 标题居中显示，字号可用 44-52px
- divider 横贯全宽，分割感要强
- 底部信息控制在一行内，避免换行

---

## 正方形海报 (600px × 600px)

### S-Layout 1: 中心居中型 (Square Center)

#### 适用场景
社交媒体帖子（Instagram、小红书）、朋友圈分享、正方形广告位。

#### ASCII 示意图

```
┌──────────────────────────┐
│                          │
│         [badge]          │
│                          │
│        主标题            │
│        副标题            │
│                          │
│      ── 分隔 ──          │
│                          │
│   📅 时间  📍 地点       │
│                          │
│      ─── 底部 ───        │
└──────────────────────────┘
```

#### HTML 代码

```html
<!-- S-Layout 1: 正方形中心居中型 -->
<!-- .poster 需设置: width: 600px; min-height: 600px; height: 600px; align-items: center; justify-content: center; text-align: center; -->
<div style="display: flex; flex-direction: column; align-items: center; justify-content: center; height: 100%; width: 100%; padding: 48px;">
  <div class="badge" style="margin-bottom: 24px;">活动类型</div>

  <h1 class="main-title" style="font-size: 40px; text-align: center; margin-bottom: 10px;">活动主标题</h1>
  <p class="subtitle" style="text-align: center; margin-bottom: 28px; font-size: 15px;">副标题或一句话说明文字</p>

  <div class="divider" style="max-width: 100px; margin: 0 auto 28px;"></div>

  <div class="info-list" style="display: flex; gap: 24px; margin-bottom: 0;">
    <div class="info-row" style="flex-direction: column; align-items: center;">
      <span class="info-icon">📅</span>
      <span class="info-value" style="font-size: 13px;">2026.06.15</span>
    </div>
    <div class="info-row" style="flex-direction: column; align-items: center;">
      <span class="info-icon">📍</span>
      <span class="info-value" style="font-size: 13px;">某某空间</span>
    </div>
  </div>
</div>

<div class="footer" style="position: absolute; bottom: 24px; left: 0; right: 0; text-align: center; padding: 0 40px;">
  <span style="font-size: 12px; opacity: 0.4;">主办方名称 · www.example.com</span>
</div>
```

#### 注意事项
- 正方形空间紧凑，标题字号 36-42px
- 所有元素居中对齐，上下左右均匀留白
- footer 用 absolute 定位贴底，不占正文空间
- 信息行用纵向排列（图标在上、文字在下），横排摆放
- 内容少时效果最好，不适合信息密集场景

---

### S-Layout 2: 四象限型 (Square Quadrant)

#### 适用场景
多信息需要组织的正方形海报、活动日程卡、多要素并列展示。

#### ASCII 示意图

```
┌─────────────┬────────────┐
│             │            │
│  主标题     │  📅 时间   │
│  副标题     │  📍 地点   │
│             │            │
├─────────────┼────────────┤
│             │            │
│  简介描述   │  主办方    │
│             │  logo/名   │
│             │            │
└─────────────┴────────────┘
```

#### HTML 代码

```html
<!-- S-Layout 2: 正方形四象限型 -->
<!-- .poster 需设置: width: 600px; min-height: 600px; height: 600px; padding: 0; display: grid; grid-template-columns: 1fr 1fr; grid-template-rows: 1fr 1fr; -->
<div class="quadrant q-topleft" style="padding: 36px; display: flex; flex-direction: column; justify-content: center; border-right: 1px solid rgba(255,255,255,0.08); border-bottom: 1px solid rgba(255,255,255,0.08);">
  <div class="badge" style="margin-bottom: 16px; font-size: 10px;">活动类型</div>
  <h1 class="main-title" style="font-size: 30px; margin-bottom: 8px;">活动主标题</h1>
  <p class="subtitle" style="font-size: 13px; margin: 0;">副标题文字</p>
</div>

<div class="quadrant q-topright" style="padding: 36px; display: flex; flex-direction: column; justify-content: center; border-bottom: 1px solid rgba(255,255,255,0.08);">
  <div class="info-row" style="margin-bottom: 14px;">
    <span class="info-icon" style="font-size: 16px;">📅</span>
    <div>
      <span class="info-label">时间</span>
      <span class="info-value" style="font-size: 14px;">2026.06.15</span>
    </div>
  </div>
  <div class="info-row">
    <span class="info-icon" style="font-size: 16px;">📍</span>
    <div>
      <span class="info-label">地点</span>
      <span class="info-value" style="font-size: 14px;">某某空间</span>
    </div>
  </div>
</div>

<div class="quadrant q-bottomleft" style="padding: 36px; display: flex; flex-direction: column; justify-content: center; border-right: 1px solid rgba(255,255,255,0.08);">
  <p class="description" style="font-size: 13px; line-height: 1.8; margin: 0;">活动简介描述文字，2-3 句话概括核心内容和亮点。适合放稍多的描述。</p>
</div>

<div class="quadrant q-bottomright" style="padding: 36px; display: flex; flex-direction: column; align-items: center; justify-content: center; text-align: center;">
  <div style="font-size: 11px; letter-spacing: 2px; text-transform: uppercase; opacity: 0.5; margin-bottom: 8px;">主办方</div>
  <div style="font-size: 16px; font-weight: 700;">品牌名称</div>
  <div style="font-size: 12px; opacity: 0.5; margin-top: 6px;">www.example.com</div>
</div>
```

#### 注意事项
- `.poster` 容器需改为 `display: grid` 布局
- 四象限用 1px 半透明线条分隔
- 每个象限独立居中，padding 统一 36px
- 标题字号大幅缩小（28-32px），适配小空间
- 信息密度高但组织清晰，每象限职责单一
- 浅色主题分隔线用 `rgba(0,0,0,0.08)`
- 不同象限可用不同背景色深浅制造层次

---

## 尺寸速查

| 类型 | 尺寸 | .poster 关键设置 |
|------|------|-----------------|
| 竖版 | 600×850+ | `flex-direction: column` |
| 横版 | 960×540 | 按布局设 `row` 或 `column` |
| 正方形 | 600×600 | `height: 600px`（固定高度） |
