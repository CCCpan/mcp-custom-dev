# How to Write Tool Descriptions That AI Actually Selects

> Based on the paper "MCP Tool Descriptions Are Smelly": 97.1% of MCP tools have description issues. Optimization improves AI selection rate by 5.85%.

## 6-Dimension Scoring

| Dimension | Standard | Common Issue |
|-----------|----------|-------------|
| **Purpose** | One sentence explaining what the tool does | 56% of tools have unclear purpose |
| **Guidelines** | When should AI use this tool | No usage scenarios described |
| **Limitations** | Known constraints (char limit, rate limit) | AI calls blindly and fails |
| **Parameters** | Each param: meaning + format + default | Unclear param names, no .describe() |
| **Completeness** | 1-3 sentences, key info first | Too short or too long |
| **Examples** | Typical usage scenarios | No examples provided |

## Good vs Bad

**❌ Bad:**
```
"Check words"
```

**✅ Good:**
```
"Detect sensitive words in Chinese text for social media (实名认证). 
Returns risk level, category, and replacement suggestions. Use when 
checking marketing copy for compliance. Max 3000 chars. Free: 100/day."
```

## Template

```
[Function] ([Chinese name]). Returns [what]. Use when [scenario]. 
[Limitations]. Free tier: N requests/day.
```

## Parameter Best Practices

```typescript
// ❌ Bad
name: z.string()

// ✅ Good
name: z.string().describe("Person's real name in Chinese (姓名), e.g. '张三'")
```

## Bilingual Strategy

Use English as primary + Chinese keywords:
```
"Verify identity card (身份证二要素验证). Returns match result..."
```

Both Chinese and English AI clients can match this.

---

> Need professional tool description optimization? WeChat: **chenganp**, Email: **345048305@qq.com**
