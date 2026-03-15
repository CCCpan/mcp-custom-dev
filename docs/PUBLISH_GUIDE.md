# MCP 五平台发布完整教程

## 1. npm 发布

```bash
npm login
npm publish
```

发布后用户可直接 `npx your-mcp-name` 使用。

**关键配置（package.json）：**
- `"bin"` — 让 npx 可执行
- `"files"` — 只发布 dist/README/LICENSE
- `"keywords"` — SEO 关键词
- `"prepublishOnly": "npm run build"` — 发布前自动编译

## 2. GitHub

```bash
git init && git add -A && git commit -m "init"
git remote add origin git@github.com:你的用户名/你的包名.git
git push -u origin main
```

设置 Topics（仓库设置页）：`mcp`, `mcp-server`, `你的关键词`

## 3. MCP Registry（官方注册表）

1. 在项目根目录创建 `server.json`
2. 提交到 GitHub
3. 访问 https://registry.modelcontextprotocol.io 用 GitHub OAuth 登录
4. 提交你的仓库地址

`server.json` 格式：
```json
{
  "$schema": "https://static.modelcontextprotocol.io/schemas/2025-12-11/server.schema.json",
  "name": "io.github.你的用户名/你的包名",
  "title": "你的MCP标题",
  "description": "英文描述",
  "version": "1.0.0",
  "packages": [{
    "registryType": "npm",
    "identifier": "你的包名",
    "registryBaseUrl": "https://registry.npmjs.org",
    "transport": "stdio"
  }]
}
```

## 4. Smithery

1. 在项目根目录创建 `smithery.yaml`
2. 访问 https://smithery.ai 用 GitHub 登录
3. 导入你的 GitHub 仓库

## 5. mcp.so

1. 访问 https://mcp.so
2. 提交你的 npm 包名或 GitHub 地址
3. 等待审核收录

## 发布顺序建议

```
npm publish → GitHub push → MCP Registry → Smithery → mcp.so
```

先发 npm（其他平台都依赖 npm 包），再推 GitHub，最后注册各平台。

---

> 需要代发布服务？联系微信：**chenganp**，邮箱：**345048305@qq.com**
