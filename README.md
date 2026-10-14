# my-docs

使用 MkDocs + Material 主题构建的文档站点，通过 GitHub Actions 自动构建并部署到 GitHub Pages。

## 目录结构

```
my-docs/
├── docs/                  # Markdown 文档源文件
│   ├── index.md           # 主页
│   ├── about.md           # 关于页面
│   ├── guide.md           # 使用指南
│   └── api.md             # API 参考
├── .github/workflows/
│   └── deploy.yml         # 自动部署工作流
├── mkdocs.yml             # MkDocs 配置
└── README.md
```

## 本地预览

```bash
pip install mkdocs-material
mkdocs serve          # 打开 http://127.0.0.1:8000
```

## 部署

推送到 `main` 分支后，GitHub Actions 会自动构建并把 `site/` 目录发布到 `gh-pages` 分支。

访问地址：`https://<用户名>.github.io/<仓库名>/`

## 前置配置

- 仓库 **Settings → Actions → General → Workflow permissions** 选择 **Read and write permissions**，否则工作流无法推送到 `gh-pages`。
- 仓库 **Settings → Pages** 的 Source 选择 **Deploy from a branch**，分支选 `gh-pages` / `(root)`。
