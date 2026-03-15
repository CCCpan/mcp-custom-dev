# Service Specification & Delivery Standards

## Delivery Checklist (22+ files)

| Category | File | Purpose |
|----------|------|---------|
| Core | `src/server.ts` | MCP Server entry point |
| Core | `src/clients/*.ts` | API client modules |
| Core | `src/utils/*.ts` | Helper functions |
| Docs | `README.md` | Chinese documentation |
| Docs | `README_EN.md` | English documentation |
| Docs | `docs/MCP_CALLING_SPEC.md` | AI calling specification |
| Config | `package.json` | npm package config |
| Config | `tsconfig.json` | TypeScript config |
| Config | `server.json` | MCP Registry config |
| Config | `smithery.yaml` | Smithery platform config |
| Config | `.env.example` | Environment variables |
| Scripts | `install.sh` | One-click install script |
| Community | `LICENSE` | MIT License |
| Community | `CODE_OF_CONDUCT.md` | Code of conduct |
| Community | `CONTRIBUTING.md` | Contribution guide |
| Community | `SECURITY.md` | Security policy |

## Technical Standards

- **Language**: TypeScript (strict mode)
- **Runtime**: Node.js >= 18
- **MCP SDK**: @modelcontextprotocol/sdk (latest)
- **Validation**: Zod schemas, every parameter has `.describe()`
- **Tool descriptions**: 6-dimension optimization (Purpose/Guidelines/Limitations/Parameters/Completeness/Examples)

## Monetization Architecture

- **Free tier**: Every response includes branding with contact info
- **Paid tier**: ACCESS_TOKEN removes branding, unlocks higher limits

## Quality Assurance

- ✅ Zero TypeScript compile errors
- ✅ CLI MCP protocol test passed
- ✅ Each tool individually tested
- ✅ AI client (Claude/Cursor) live test
- ✅ 6-dimension tool description review
- ✅ No third-party brand information leaks

---

> Learn more: WeChat: **chenganp**, Email: **345048305@qq.com**
