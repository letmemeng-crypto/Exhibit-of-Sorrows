# CLAUDE.md — 项目规则（Exhibit of Sorrows 单页站）

你在一个纯静态网站项目里工作，为独立恐怖游戏 “Exhibit of Sorrows” 制作英文单页站。
目标：生成/更新 `index.html`，加载极快，恐怖暗黑风格。

## 1) 硬性要求（必须）
- 纯静态：只用 HTML5 + CSS3。不要框架，不要复杂依赖。
- 用 iframe 嵌入游戏：
  - 地址：https://html-classic.itch.zone/html/14611877/index.html
  - 必须支持全屏：iframe 需要 `allowfullscreen` 和 `allow="fullscreen"`.
- 自适应：
  - 游戏窗口固定比例 1060:805。
  - 手机端要等比缩小，不溢出。
  - 使用 `aspect-ratio: 1060 / 805`，并提供旧浏览器 fallback。
- 布局：
  - 游戏必须放页面最上方
  - 游戏介绍必须放在游戏下面
- 视觉风格：
  - Dark Mode：黑/灰/深红，恐怖氛围
  - 轻微发光/描边即可，不要亮色
- SEO：
  - 必须包含 `<title>`、`<meta name="description">`、页面中必须有 `<h1>`
  - title 固定：
    - Exhibit of Sorrows Unblocked - Play Free Horror Game Online
  - description 固定：
    - Step into Exhibit of Sorrows, a chilling point-and-click horror game. Solve macabre puzzles, interact with twisted circus dolls, and don’t upset the clown.

## 2) UI 必须实现
- 顶部 header：
  - 删除所有徽章和文字
  - 只保留一个“首页”链接，点击回到页面顶部（#top）
- 标题位置：
  - iframe 上方不要任何标题栏
  - 只在 iframe 下方显示 “Exhibit of Sorrows”
- 按钮（和标题同一条下方栏，右侧）：
  - Fullscreen 按钮：让“游戏容器”进入全屏（兼容 requestFullscreen/webkit/ms）
  - Like 按钮：带数字计数，本地 localStorage 保存，切换状态
- JS 只能用于：Fullscreen + Like。其余尽量不用。

## 3) 内容（必须使用下面英文文案，放在游戏下方）
【H1】Exhibit of Sorrows: Can You Survive the Circus Museum?
【正文】(保持你给的英文原文，不要改意思)
【H2】Meet the Dolls in Exhibit of Sorrows
【H2】Why You Should Play Exhibit of Sorrows
【H3】How to Play Exhibit of Sorrows
【H2】Exhibit of Sorrows FAQ

## 4) 禁止项（不要做）
- 不要引入 React/Vue/Bootstrap/Tailwind CDN 等任何框架
- 不要写作者/开发者介绍
- 不要加顶部广告/徽章条
- 不要引入外部资源（除非必要）

## 5) 验收清单
- 页面加载快：单文件、CSS/JS 极少
- iframe 正常显示并按比例自适应
- Fullscreen 可用
- Like 可用且本地保存
- 顶部只有“首页”
- “Exhibit of Sorrows”只出现在 iframe 下方栏
- SEO 三件套齐全 + 有 H1
