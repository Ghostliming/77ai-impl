# 企企AI落地中的解决方案 · HTML 演示稿

基于 [html-ppt](https://github.com/lewislulu/html-ppt-skill) 构建的 **22 页**内部汇报演示稿。

## 在线访问（GitHub Pages）

推送 `main` 分支后自动部署：

**https://ghostliming.github.io/77ai-impl/**

首次启用：仓库 **Settings → Pages → Build and deployment → Source** 选择 **GitHub Actions**。

## 打开方式

在 `html` 目录下启动本地服务后访问：

```powershell
cd workspace/企企AI落地中的解决方案/html
python -m http.server 18923
# 浏览器打开 http://127.0.0.1:18923/index.html
```

也可直接用浏览器打开 `index.html`（部分环境对本地 file 协议有限制，推荐 HTTP 服务）。

## 键盘操作

| 按键 | 功能 |
|---|---|
| ← → / Space | 翻页 |
| 触控屏左右滑动 | 翻页（左滑下一页 · 右滑上一页） |
| F | 全屏 |
| S | 演讲者模式（当前/下一页预览 + 备注 + 计时） |
| N | 备注抽屉 |
| O | 幻灯片概览 |
| #/N | 深链到第 N 页，如 `#/7` |

## 文件结构

```
html/
├── index.html              # 22 页主文件
├── deck.css                # 品牌 chrome、布局、响应式
├── themes/
│   └── q7hub-corporate.css # 企企深色蓝紫主题 tokens
├── assets/images/          # 背景、Logo、架构图（从上级 assets 复制）
└── vendor/                 # html-ppt 运行时（base.css / runtime.js 等）
```

## 品牌规范

| 页面类型 | 左上 | 右上 | 背景 |
|---|---|---|---|
| 封面 P1 | 带文字 Logo | — | bg-cover.png |
| 内容 P2–21 | 图标 Logo（加大） | Slogan 图 | bg-content.png 低亮度主视觉 + 深色遮罩 |
| 支撑机制 P22 | 图标 Logo | Slogan 图 | bg-content.png 低亮度主视觉 + 机制链路 |

## 响应式

- 默认按 16:9 全屏演示优化
- ≤1280px / ≤1024px：栅格列数自适应（Pad 横竖屏）
- ≤768px：单列布局、缩小边距

## GitHub Pages 部署说明

| 项 | 说明 |
|---|---|
| 工作流 | `.github/workflows/deploy-pages.yml` |
| 触发 | `push` 到 `main`，或 Actions 页手动 **Run workflow** |
| 静态根目录 | 仓库根目录（`index.html` 即入口） |
| Jekyll | 根目录 `.nojekyll` 禁用 Jekyll，避免 `vendor/` 等目录被忽略 |

资源路径均为相对引用，适配 Pages 子路径 `/77ai-impl/` 托管。
