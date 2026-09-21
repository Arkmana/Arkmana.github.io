# Arkmana.github.io

这是一个**构建产物仓库**，不是源码仓库。请不要在这里直接编辑内容。

## 它是怎么工作的

```
Arkmana/blog-source  (私有，真正的源码)
   └─ firefly 分支   ← Firefly / Astro 7 源码
          │
          ↓  .github/workflows/build-astro.yml
   checkout → pnpm install → pnpm run build → deploy-pages
          │
          ↓
   https://arkmana.github.io/
```

线上文件**不提交到这个仓库**，由 GitHub Actions 通过
`actions/upload-pages-artifact` + `actions/deploy-pages` 直接发布到 Pages。

## 分支说明

| 分支 | 用途 |
| --- | --- |
| `main` | 只放工作流与说明（本文件） |
| `gh-pages` | 早期 Astro+Vue 站点的产物，已停用，保留备查 |

## 构建触发方式

| 方式 | 延迟 | 说明 |
| --- | --- | --- |
| push 到本仓 `main` | 立即 | 改了工作流或本文件时 |
| `repository_dispatch` (`blog-updated`) | 立即 | 供 blog-source 远端触发 |
| `workflow_dispatch` | 立即 | 手动 Run workflow |
| `schedule`（每 6 小时） | ≤6 小时 | 无凭据兜底 |

## 源码与归档

- 源码：`Arkmana/blog-source`（私有）的 `firefly` 分支
- 旧站源码：同仓库 `preview` 分支（Astro + Vue 3，5 篇文章，已停用但保留）
