markdown
# Clash Rules Collection

[![GitHub release](https://img.shields.io/github/v/release/aefa6/clash-rules)](https://github.com/aefa6/clash-rules/releases)
[![jsDelivr](https://data.jsdelivr.com/v1/package/gh/aefa6/clash-rules/badge)](https://www.jsdelivr.com/package/gh/aefa6/clash-rules)

一个精心整理的、针对**特定场景**的 Clash 规则集，专注于主流规则集可能忽略或未及时收录的域名。

## 🎯 项目特点

本规则库**不做大而全的通用规则**，而是聚焦于：
- ✅ **开发工具**：如 MICROSOFT Copilot 相关域名
- ✅ **特定服务**：需要特殊处理的直连或代理服务
- ✅ **冷门规则**：主流规则集未覆盖的网站或APP
- ✅ **精细化分流**：针对具体域名而非泛域名规则

## 📦 规则列表

| 规则文件 | 用途 | CDN 链接 |
|---------|------|---------|
| **bypass.txt** | 需要**绕过代理**（直连）的规则<br>（如：Apple、Microsoft 等国内访问良好的服务） | `https://cdn.jsdelivr.net/gh/aefa6/clash-rules@release/bypass.txt` |
| **copilot.txt** | **Microsoft Copilot** 及相关服务的代理规则 | `https://cdn.jsdelivr.net/gh/aefa6/clash-rules@release/copilot.txt` |

## 🚀 快速使用

### Clash 配置示例

在您的 `config.yaml` 中引用这些规则：

```yaml
rules:
  # 引用直连规则 (bypass)
  - RULE-SET,https://cdn.jsdelivr.net/gh/aefa6/clash-rules@release/bypass.txt,DIRECT
  
  # 引用 Copilot 代理规则
  - RULE-SET,https://cdn.jsdelivr.net/gh/aefa6/clash-rules@release/copilot.txt,PROXY
  
  # 其他规则...
  - MATCH,PROXY

📋 当前包含的规则详情
bypass.txt (直连规则)
Apple & Microsoft 直连服务

copilot.txt (代理规则)
Microsoft copilot & M365 copilot

🤝 贡献与反馈
欢迎提交 Issue 或 Pull Request 来完善规则，特别是：

发现新的需要特殊处理的域名

主流规则集遗漏的网站

对现有规则的修正建议

⚠️ 注意事项
本规则集仅包含特定场景的规则，建议与主流规则集（如 Loyalsoldier/clash-rules）配合使用

规则优先级：请将更具体的规则放在前面，本规则集中的条目多为精确域名

使用前请确保您的代理工具支持 RULE-SET 功能（Clash Premium / Clash.Meta / Surge / Quantumult X）

📄 许可
本项目仅供学习交流使用，请遵守当地法律法规。
