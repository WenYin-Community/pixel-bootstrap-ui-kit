# Pixel Bootstrap 5 UI Kit

![version](https://img.shields.io/badge/version-4.0.0-blue.svg) ![license](https://img.shields.io/badge/license-MIT-blue.svg)

Pixel 是一个免费、完全响应式的 Bootstrap 5 UI 组件库，帮助你快速构建专业美观的网站。提供丰富的可复用组件和区块，通过 Sass 变量自定义样式，灵活搭建各类页面。

## 主要特性

- 基于 Bootstrap 5 构建，无 jQuery 依赖
- 80+ UI 组件，5 个示例页面
- Sass/SCSS 主题定制，Gulp 自动化构建
- Vanilla JavaScript，轻量高效
- 完全响应式，移动端优先
- FontAwesome 图标库集成

## 快速开始

### 环境要求

- Node.js
- Gulp CLI

### 安装与运行

```bash
# 安装 Gulp CLI（全局）
npm install gulp-cli -g

# 安装项目依赖
npm install

# 启动开发服务器（BrowserSync 热重载）
gulp
```

按 `CTRL+C` 停止开发服务器。

### 构建输出

```bash
# 生成未压缩的 HTML/CSS 版本（html&css/ 目录）
gulp build:dev

# 生成压缩后的生产版本（dist/ 目录）
gulp build:dist
```

## 项目结构

```
.
├── src/                    # 源代码
│   ├── index.html          # 首页
│   ├── html/pages/         # 页面模板
│   ├── partials/           # 可复用 HTML 片段
│   ├── assets/
│   │   ├── img/            # 图片资源
│   │   └── js/             # 自定义 JavaScript
│   └── scss/               # Sass 样式源文件
├── html&css/               # 构建输出（未压缩）
├── dist/                   # 构建输出（压缩）
├── gulpfile.js             # Gulp 构建配置
└── package.json            # 项目依赖
```

## Gulp 任务

| 命令 | 说明 |
|------|------|
| `gulp` | 启动开发服务器，实时监听文件变化 |
| `gulp build:dev` | 构建未压缩版本到 `html&css/` |
| `gulp build:dist` | 构建压缩版本到 `dist/` |

## 浏览器支持

支持以下浏览器的最近两个版本：

- Chrome
- Firefox
- Edge
- Safari
- Opera

## 问题反馈

如遇到问题，请通过 GitHub Issues 提交，并附上：

1. 问题的复现步骤
2. 使用的浏览器及版本
3. 相关的错误信息或截图

## 许可证

MIT License - 详见 [LICENSE](./LICENSE) 文件

## 相关资源

- [Bootstrap 官方文档](https://getbootstrap.com/)
- [Gulp 官方文档](https://gulpjs.com/)
- [Sass 官方文档](https://sass-lang.com/)
- [FontAwesome 图标](https://fontawesome.com/)
