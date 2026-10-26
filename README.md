# 小微 Few-shot 格式规范 · 在线发布仓库

此仓库以根目录 `SKILL.md` 为**唯一规范正文**。网站由 GitHub Actions 自动构建，无需手动编辑 HTML。

## 首次上线

1. 在 GitHub 新建仓库 `xiaowei-fewshot-skill`，建议选择 Public（公开网络可访问；先检查内容无保密信息）。
2. 将本文件夹**所有内容（包括隐藏的 `.github` 文件夹）**上传到仓库根目录，默认分支设为 `main`。
3. 进入仓库 **Settings → Pages → Build and deployment → Source → GitHub Actions**。
4. 在 **Actions** 中查看 `Publish latest Skill website` 是否成功；成功后，在 Pages 设置查看实际地址。
5. 常见地址为 `https://<你的GitHub用户名>.github.io/xiaowei-fewshot-skill/`（示例格式，发布后以 Pages 显示地址为准）。将此地址发给团队。

## 日常更新

1. 点击仓库里的 `SKILL.md` → Edit（铅笔）。
2. 修改规则和示例；更新顶部 `version:` 及正文版本号，并修改 `CHANGELOG.md`。
3. Commit changes 到 `main`（协作环境可先开 PR 评审再合并）。
4. GitHub Actions 构建并发布网站；成功后，所有人打开原网址即看到新版本，也可点击“一键复制完整 SKILL.md”。

**注意**：网站是最新线上版本；之前下载或粘贴到个人 Agent 的副本**不会**自动更新。网页可能受浏览器缓存或部署处理时间影响，更新时核对页面版本号即可。

## 版本与协作建议

- 小改动修补例子：`1.1.1`；增加新规则：`1.2.0`；有不兼容的规则调整：`2.0.0`。
- `SKILL.md` 的正文是单一事实源；HTML 由构建脚本生成，不应手工改写。
- 每次更新 `CHANGELOG.md`；敏感内容不要上传公开仓库，注意 GitHub Pages 公开访问属性。
- 如需多人审核，可在 GitHub Settings 中给 `main` 配置分支保护和 PR 审核。

## 本地预览（可选）

```bash
pip install -r requirements.txt
python scripts/build.py
python -m http.server 8000 -d _site
```

打开 `http://localhost:8000`。

## 文件用途

- `SKILL.md`：唯一规范原文
- `CHANGELOG.md`：更新历史
- `CONTRIBUTING.md`：贡献规则
- `scripts/build.py`：从 Markdown 生成网页
- `.github/workflows/pages.yml`：提交后自动部署
- `_site/`：自动生成物，不需要上传
