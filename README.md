# 中文 SEO 博客底座

这是一个专为中文内容打造的高级 SEO 博客架构，基于现代 Web 技术栈构建。

## 技术栈

*   **框架**: [Astro](https://astro.build)
*   **语言**: TypeScript
*   **内容格式**: Markdown / MDX
*   **样式**: Tailwind CSS (v4)
*   **部署**: 静态站点生成 (SSG) -> Cloudflare Pages

## 特性

*   **极致性能**: Astro 默认不发送客户端 JavaScript，实现了极快的页面加载速度。
*   **SEO 优先**: 完整的 TDK (Title, Description, Keywords) 管理、Open Graph 支持和结构化数据 (JSON-LD) 预留。
*   **高级 UI**: 借助 Tailwind CSS v4 实现了毛玻璃 (Glassmorphism)、平滑动画、暗黑模式支持。
*   **内容优先**: 专为长篇图文、深度评测和教程打造了优化的阅读排版（行高、段落间距、引用框）。

## 快速开始

```bash
# 1. 安装依赖
npm install

# 2. 启动本地开发服务器
npm run dev

# 3. 构建静态文件
npm run build
```

## Cloudflare Pages 部署指南

本项目已经为您配置好了 GitHub Actions 工作流，可以实现自动部署到 Cloudflare Pages：

1.  将本项目推送到您的 GitHub 仓库。
2.  在 Cloudflare Dashboard 中创建一个新的 **Pages** 项目（选择直接上传资产或不关联 GitHub 仓库，因为我们将使用 Actions 部署）。
3.  在您的 GitHub 仓库设置中，添加以下 **Secrets** (Settings -> Secrets and variables -> Actions)：
    *   `CLOUDFLARE_API_TOKEN`: 您的 Cloudflare API 令牌（需要具备 Pages 的编辑权限）。
    *   `CLOUDFLARE_ACCOUNT_ID`: 您的 Cloudflare Account ID（可在 Dashboard 侧边栏找到）。
4.  编辑 `.github/workflows/deploy.yml` 文件，将 `projectName: 'your-cloudflare-project-name'` 替换为您在 Cloudflare 中创建的真实项目名称。
5.  提交更改并推送到 `main` 分支，GitHub Actions 将自动触发构建并将 `dist` 目录部署到 Cloudflare 的全球边缘网络。

## 目录结构

*   `src/components/`: 可复用的 UI 组件 (Header, Footer, SEO)。
*   `src/layouts/`: 全局页面骨架。
*   `src/pages/`: 页面路由 (首页、博客列表、评测列表等)。
*   `src/styles/`: 全局样式入口 (`global.css`)，包含 Tailwind v4 的 `@theme` 配置。
