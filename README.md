# Arkmana.github.io

构建产物仓库（旧方案，**已迁移到 Cloudflare Pages**）。

## 当前部署架构

```
Obsidian 库（D:\obsidain\数学）
   │  图片 → CloudFlare ImgBed（https://cloudflare-imgbed-9wx.pages.dev）
   │  笔记 → scripts/publish-vault.mjs 同步
   ↓
Arkmana/blog-source  (私有)
   ├─ main   ← Cloudflare Pages 监听这个分支
   └─ firefly ← 同一份内容（保留兼容）
   ↓
Cloudflare Pages「arkmana」→ https://arkmana.pages.dev/
```

## 本仓库的现状

| 分支 | 用途 |
| --- | --- |
| `main` | 只放 GitHub Actions 工作流（备用） |
| `gh-pages` | 更早期的 Astro+Vue 站点产物，已停用 |

## 为什么保留这个仓库

- `build-astro.yml` 工作流作为**备用部署通道**（Cloudflare 出问题时可切回 GitHub Pages）
- 部署地址：`https://arkmana.github.io/`（内容可能是旧的）

主站已切换至 **https://arkmana.pages.dev/**。
