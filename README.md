# focusapi-docs

FocusAPI 公有云用户文档（Mintlify）。当前仅发布 **中文**；英文占位见 `en/` 目录。

## 本地预览

```bash
npm i -g mint
cd docs/focusapi-docs   # 或你的 clone 路径
mint dev
```

浏览器打开 CLI 提示的地址（通常为 `http://localhost:3000`）。

## 目录结构

```text
├── docs.json           # Mintlify 站点配置与导航
├── index.mdx
├── quickstart.mdx
├── models/
├── api/
├── errors/
├── billing/
├── faq/
└── en/                 # 英文占位（未接入导航）
```

## 部署到 Mintlify（子域名）

1. 将本仓库连接到 [Mintlify Dashboard](https://dashboard.mintlify.com)（GitHub 集成）。
2. 在 Mintlify 中配置 **Custom domain**：`docs.focusapi.com`。
3. 在 DNS 服务商添加记录（以 Mintlify 面板显示的为准），通常为：
   - 类型：`CNAME`
   - 主机：`docs`
   - 目标：Mintlify 提供的 `*.mintlify.app` 或指定 host
4. 等待证书签发后访问 `https://docs.focusapi.com`。

## 与主项目（new-api）的关系

- 本目录是 **独立 Git 仓库**，不要提交到 `new-api` 主仓。
- 主仓 `general_setting.docs_link` 建议设为：`https://docs.focusapi.com` 或 `https://docs.focusapi.com/quickstart`。
- 旧站 `docs.FocusAPI.pro` 可在 DNS/托管层 301 到新域名；`docs.json` 已包含部分路径重定向（如 `/getting-started` → `/quickstart`）。

## 英文文档（后续）

1. 在 `en/` 下补全与根目录同路径的 MDX。
2. 在 `docs.json` 的 `navigation` 中增加 `languages` 配置。
3. 参考：[Mintlify 国际化](https://mintlify.com/docs/guides/internationalization)。

## 搜索

Mintlify Hobby 计划包含站内搜索（`⌘K` / `Ctrl+K`）。无需额外代码；通过各页 `title` / `description` frontmatter 优化检索效果。
