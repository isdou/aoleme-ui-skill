---
name: 熬了么 UI 设计系统
description: 赛博修仙美学设计指南，包含玻璃拟态、流体动效及性能优化的 Tailwind 组件库。
---

# 熬了么 (StayUpApp) UI 设计系统

本 Skill 为“熬了么”项目独特的“赛博修仙”美学提供了完整的设计参考。它完美融合了深邃神秘的视觉风格、现代玻璃拟态（Glassmorphism）以及流畅的流体动效。

## 🚀 快速开始 (Quick Start)

### 1. 配置环境
要使用此设计系统，请确保你的项目已安装并配置了 Tailwind CSS。
将 [resources/tailwind.config.js](./resources/tailwind.config.js) 中的配置复制到你项目的 `tailwind.config.js` 文件中。

### 2. 引入全局样式
将 [resources/global.css](./resources/global.css) 中的全局样式和变量引入到你的主 CSS 文件中（例如 `index.css` 或 `App.css`）。

```css
@import './resources/global.css'; 
/* 或者直接复制文件内容 */
```

## 🎨 视觉语言 (Visual Language)

### 配色方案 (Color Palette)
系统采用极深色背景搭配鲜艳的霓虹色点缀。

- **背景色**: `#020105` (深空黑 / Deep Space Black)
- **主色调**: `#722dcd` (修仙紫 / Cultivation Purple)
- **功德/金币**: `#ffb703` (金丹色 / Golden Core)
- **生命/健康**: `#4ade80` (生命绿 / Life Essence)
- **危险/警告**: `#ef4444` (天劫红 / Tribulation Red)

### 字体系统 (Typography)
- **标题**: `Space Grotesk` (现代科技感)
- **正文**: `Noto Sans SC` (良好的中文阅读体验)
- **图标**: `Material Symbols Outlined`

## 🧩 组件配方 (Component Recipes)

在 React 代码中直接使用以下预构建的组件模式。

### 按钮 (Buttons)

**主要操作按钮 (Primary Action)**
```tsx
<button className="
    px-6 py-3
    rounded-full
    bg-gradient-to-r from-purple-600 to-purple-500
    border border-purple-400/30
    text-white
    font-black
    tracking-widest
    uppercase
    shadow-glow-purple
    active:scale-95
    transition-all duration-200
    hover:shadow-[0_0_30px_rgba(168,85,247,0.6)]
    gpu-accelerated
">
    一键修仙
</button>
```

**玻璃图标按钮 (Glass Icon Button)**
```tsx
<button className="
    w-10 h-10
    rounded-full
    glass-panel
    flex items-center justify-center
    active:scale-95
    transition-transform
    bg-white/5
    border border-white/10
    relative overflow-hidden
    group
">
    <div className="absolute inset-0 bg-gradient-to-br from-purple-500/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity"></div>
    <span className="material-symbols-outlined text-white/80 text-xl relative z-10">
        bolt
    </span>
</button>
```

### 卡片 (Cards)

**玻璃态数据卡片 (Stats Glass Card)**
```tsx
<div className="
    glass-panel
    rounded-2xl
    p-4
    flex flex-col gap-3
    border border-white/5
    shadow-fluid
    relative overflow-hidden
    bg-white/[0.02]
">
    <div className="flex items-center justify-between">
        <div className="p-2 rounded-full bg-purple-500/10 border border-purple-500/20">
            <span className="material-symbols-outlined text-base text-purple-400">
                self_improvement
            </span>
        </div>
        <span className="text-[9px] font-black px-1.5 py-0.5 rounded border tracking-tighter text-purple-300 bg-purple-500/5 border-purple-500/20">
            修炼中
        </span>
    </div>

    <div className="flex flex-col gap-1.5">
        <span className="text-[9px] text-white/40 uppercase font-black tracking-widest">
            当前境界
        </span>
        <span className="text-xl font-bold text-white text-glow">
            结丹期
        </span>
    </div>
</div>
```

### 输入框 (Inputs)

**玻璃态输入框 (Glass Input Field)**
```tsx
<input
    type="text"
    className="
        w-full
        px-4 py-3
        rounded-xl
        glass-panel
        border border-white/10
        bg-white/5
        text-white
        placeholder:text-white/30
        focus:outline-none
        focus:border-primary/50
        focus:ring-2 focus:ring-primary/20
        transition-all duration-200
    "
    placeholder="输入口令..."
/>
```

### 液体进度条 (Liquid Progress Bar)
```tsx
<div className="glass-tube h-5 rounded-full p-1 relative overflow-hidden">
    <div
        className="h-full liquid-fill rounded-full transition-all duration-1000"
        style={{ width: '75%' }}
    >
        <div className="absolute inset-0 bg-gradient-to-r from-transparent via-white/30 to-transparent animate-liquid-shimmer" />
    </div>
    <div className="absolute top-0 left-0 w-full h-1/2 bg-white/10 rounded-t-full pointer-events-none" />
</div>
```

## 🎬 动画与特效 (Animations & Effects)

### 通用工具类 (Common Utilities)
- `glass-panel`: 基础玻璃面板，带边框和 GPU 加速。
- `glass-morphism`: 重度模糊玻璃效果，质感更强。
- `liquid-glass`: 高度模糊，模拟液体流动感的玻璃效果。
- `text-glow`: 白色文字发光效果。
- `text-glow-red`: 红色文字发光效果（用于警告/危险）。

### Tailwind 动画 (Tailwind Animations)
(已在 `tailwind.config.js` 中定义)
- `animate-pulse-fast`: 快速脉冲（用于危险/紧急状态）。
- `animate-float`: 轻柔悬浮（用于模拟冥想/修炼状态）。
- `animate-scan`: 垂直扫描线（用于科技诊断/扫描效果）。
- `animate-liquid-flow`: 液体色相旋转流光效果。

## ⚡ 性能优化指南 (Performance Guidelines)
1.  **GPU 加速**: 对所有动画元素务必添加 `transform: translateZ(0)` 或使用 `.gpu-accelerated` 类，以防止页面重绘 (Repaint)。
2.  **透明度过渡**: 尽量使用 `opacity` 和 `transform` 进行动画过渡，避免改变 `width`、`height`、`top` 或 `left` 属性。
3.  **Will-Change**: 仅在正在进行复杂动画的元素上谨慎使用 `will-change` 属性。
4.  **触控优化**: 确保所有可交互元素的触控区域至少为 44x44px。
