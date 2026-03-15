# 如何写出让 AI 选中的 Tool 描述

> 基于论文《MCP Tool Descriptions Are Smelly》的研究成果，97.1% 的 MCP 工具描述至少存在一种问题。优化描述可提升 AI 选中率 5.85%。

## 六维度评分标准

| 维度 | 满分标准 | 常见问题 |
|------|---------|---------|
| **Purpose（目的）** | 一句话说清工具做什么 | 56% 的工具目的不清 |
| **Guidelines（使用指南）** | 说明什么场景该用这个工具 | 没说什么时候用 |
| **Limitations（限制）** | 标明已知约束 | 没提限制，AI 盲目调用 |
| **Parameters（参数）** | 每个参数含义+格式+默认值 | 参数名不直观，没 describe |
| **Completeness（完整性）** | 关键信息前置，1-3句 | 太短或太长 |
| **Examples（示例）** | 典型调用场景 | 没有示例 |

## 好的 Tool 描述模板

```
[一句话说清功能]。[什么场景该用]。[有什么限制]。Free tier: N requests/day.
```

### 示例：

**❌ 差的描述：**
```
"Check words"
```

**✅ 好的描述：**
```
"Detect sensitive/prohibited words in Chinese text for social media platforms 
(Xiaohongshu, Douyin, Kuaishou, Bilibili). Returns risk level (high/medium/low), 
word category, position, and safe replacement suggestions. Use when users need 
to check marketing copy or social media posts for compliance. Max 3000 characters. 
Free tier: 100 requests/day."
```

## 参数描述技巧

每个参数都必须有 `.describe()`：

```typescript
// ❌ 差
name: z.string()

// ✅ 好
name: z.string().describe("Person's real name in Chinese (姓名), e.g. '张三'")

// ✅ 好
id_card: z.string().length(18).describe("18-digit Chinese ID card number (身份证号码)")
```

## 中英双语策略

Tool 描述用英文为主 + 中文关键词补充：

```
"Verify if a person's name matches their Chinese ID card number (实名认证/身份证二要素验证)."
```

这样中文用户和英文用户的 AI 都能匹配到。

## 自检清单

- [ ] 描述是否一句话说清了功能？
- [ ] 是否说明了什么场景该用？
- [ ] 是否标明了限制（字数、额度等）？
- [ ] 每个参数是否都有 .describe()？
- [ ] 描述长度是否在 1-3 句之间？
- [ ] 是否包含中英文关键词？

---

> 需要专业的 Tool 描述优化服务？联系微信：**chenganp**，邮箱：**345048305@qq.com**
