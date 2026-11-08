# CSS Tips

平时收集的 CSS 效果速查表，方便随时翻看。

每条 tip 都是仓库里真实可运行的 HTML/CSS：demo 可直接打开，代码就是展示的那份，不依赖 CodePen 等外部服务。

**在线浏览：https://ximuli.github.io/css-tips/**

## 本地预览

首页的代码块通过 `fetch` 加载同目录的 `style.css`（Prism file-highlight），所以不能直接双击 `index.html`，需要起一个本地 HTTP 服务：

```bash
python3 -m http.server 8000
```

然后打开 `http://localhost:8000`。

## 目录结构

```
.
├── index.html              # 首页：侧边目录 + 搜索 + demo + 代码
├── index.css               # 首页样式
├── assets/                 # Prism 代码高亮
└── tips/
    ├── 001-text-overflow/
    │   ├── demo.html       # 可独立打开的演示页
    │   └── style.css       # 技巧本身（首页展示的代码）
    └── 002-typing-effect/
        ├── demo.html
        └── style.css
```

## 添加一条新 tip

1. 新建 `tips/NNN-slug/`，放入 `demo.html` 和 `style.css`；
   - `demo.html` 直接 `<link>` 同目录的 `style.css`，可独立打开
   - `style.css` 只放技巧本身的代码，页面排版样式写在 `demo.html` 的 `<style>` 里
2. 在 `index.html` 里复制一个 `<section class="tip">`，修改编号、标题、`data-search` 关键词和路径；
3. 在侧边目录 `.toc` 里加一条对应链接。
