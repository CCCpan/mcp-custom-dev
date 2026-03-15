# MCP 5-Platform Publishing Guide

## 1. npm

```bash
npm login
npm publish
```

Key `package.json` fields:
- `"bin"` — enables `npx your-mcp-name`
- `"files"` — only publish dist/README/LICENSE
- `"keywords"` — SEO keywords
- `"prepublishOnly": "npm run build"` — auto-compile before publish

## 2. GitHub

```bash
git init && git add -A && git commit -m "init"
git remote add origin git@github.com:username/your-mcp.git
git push -u origin main
```

Set Topics in repo settings: `mcp`, `mcp-server`, `your-keywords`

## 3. MCP Registry

1. Create `server.json` in project root
2. Push to GitHub
3. Visit https://registry.modelcontextprotocol.io, login with GitHub OAuth
4. Submit your repository

## 4. Smithery

1. Create `smithery.yaml` in project root
2. Visit https://smithery.ai, login with GitHub
3. Import your repository

## 5. mcp.so

1. Visit https://mcp.so
2. Submit your npm package name or GitHub URL
3. Wait for review

## Recommended Order

```
npm → GitHub → MCP Registry → Smithery → mcp.so
```

Publish npm first (other platforms depend on it), then GitHub, then register on each platform.

---

> Need publishing assistance? WeChat: **chenganp**, Email: **345048305@qq.com**
