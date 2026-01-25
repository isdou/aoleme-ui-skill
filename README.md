# 熬了么 UI Skill (Aoleme UI Skill)

## 简介
这是一个专为打造“赛博修仙”风格应用而设计的 UI Skill 包。它包含了一套完整的设计语言、Tailwind 配置、以及 React 组件范式，旨在帮助开发者快速构建出具有深邃神秘感与现代科技感融合的界面。

核心风格：**赛博修仙 (Cyberpunk Cultivation)**
- 🌌 **深空黑背景**：沉浸式体验
- 🔮 **修仙紫主调**：神秘与高贵
- 💧 **流体动效**：灵动与生机
- 🧊 **玻璃拟态**：现代感与层次感

## 包含内容

本仓库包含以下核心资源：

1.  **[SKILL.md](./SKILL.md)**: 核心指南文件。详细描述了设计系统的视觉规范、配色方案、以及各类组件（按钮、卡片、输入框等）的实现代码。
2.  **resources/**: 资源目录。
    - `tailwind.config.js`: 预设的 Tailwind 动画与色彩配置。
    - `global.css`: 全局样式定义，包含一系列实用的 CSS 工具类。

## 如何使用

### 作为 Agent Skill 使用
如果你正在使用支持 Skill 的 AI Agent（如 Antigravity），该 Skill 会为 Agent 提供关于“熬了么”UI 风格的完整上下文。Agent 将能够：
- 理解并应用特定的配色方案（#020105 背景, #722dcd 主色等）。
- 直接生成符合风格的 React 组件代码。
- 遵循性能优化指南编写动画。

### 手动集成
你也可以手动参考本 Skill 中的设计规范：

1.  **配置 Tailwind**: 参考 `resources/tailwind.config.js` 将配置合并到你的项目中。
2.  **引入样式**: 将 `resources/global.css` 引入你的项目。
3.  **使用组件**: 参考 `SKILL.md` 中的“组件配方”部分，复制并使用预构建的 UI 组件。

## 贡献
欢迎提交 Issue 或 Pull Request 来丰富这套“赛博修仙”设计系统！

## License

[MIT](./LICENSE) © 2026 isdou
