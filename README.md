# SparkleWares Studio

Handmade 2-inch (5 cm) mini vinyl records — one-page site.

Live: https://sparklewares.pages.dev

## 结构

    deploy/          可直接部署的静态站点（index.html + assets）
    v10-single.html  单文件版本（图片内嵌，双击即开）
    plan/            方案、设计系统、优化清单
    build/           构建与部署脚本

## 本地预览

    cd deploy && python -m http.server 8000

## 部署

推到 `main` 自动部署（GitHub Actions + wrangler）。
手动部署：

    node build/npmglobal/node_modules/wrangler/bin/wrangler.js \
      pages deploy deploy --project-name sparklewares --branch main

需要在仓库 Secrets 里配置：

- `CLOUDFLARE_API_TOKEN`
- `CLOUDFLARE_ACCOUNT_ID`

## Auto-deploy

Connected to Cloudflare Pages — pushing to `main` rebuilds the site.
