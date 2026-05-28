# PM Agent Skills 安装指南

本目录包含 PM Agent 使用的全部 OpenClaw Skills，可在全新设备上快速恢复环境。

## 快速安装

在 OpenClaw 中执行以下命令安装全部 Skills：

```bash
skillhub_install install_skill docx
skillhub_install install_skill xlsx
skillhub_install install_skill pdf
skillhub_install install_skill mcporter
skillhub_install install_skill kdocs
skillhub_install install_skill another_them
skillhub_install install_skill multi-search-engine
skillhub_install install_skill frontend-design
skillhub_install install_skill cloud-upload-backup
skillhub_install install_skill email-skill
skillhub_install install_skill find-skills
```

## Skill 清单

| Skill | 用途 |
|-------|------|
| **docx** | Word 文档生成、编辑 |
| **xlsx** | Excel/CSV 表格生成、编辑 |
| **pdf** | PDF 读取、合并、分割、水印、表单 |
| **mcporter** | 腾讯文档 MCP（搜索、读取、管理） |
| **kdocs** | 腾讯文档全套操作（智能文档/表格/PPT/思维导图） |
| **another_them** | 蒸馏人/主题为完整 Agent 人设包 |
| **multi-search-engine** | 17 个搜索引擎聚合（国内+国际） |
| **frontend-design** | 高质量前端界面生成（HTML/React） |
| **cloud-upload-backup** | 腾讯 SMH 云存储上传备份 |
| **email-skill** | 邮件路由层（public-skill / imap-smtp-email） |
| **find-skills** | 技能发现与安装 |
| **aippt** | AI PPT 生成 |
| **bdpan-storage** | 百度网盘存储 |
| **fbs_bookwriter** | 书籍创作 |
| **layered-scene-builder** | 分层场景构建 |
| **meituan-travel** | 美团旅行 |
| **persona-switch** | 人格切换 |
| **product-manager** | 产品经理专业技能 |
| **tencent-esign-contract** | 腾讯电子签合同 |
| **tencent-meeting-mcp** | 腾讯会议 MCP |
| **wecom-weisheng-scrm** | 企业微信微盛 SCRM |

## MCP 工具配置

部分功能需要配置 MCP 工具（见 `config/` 目录）。配置方式：

1. 编辑 `~/.qclaw/openclaw.json`（或通过 OpenClaw CLI）
2. 在 `mcpServers` 中添加对应配置
3. 重启 Gateway：`openclaw gateway restart`

### 墨刀 MCP（原型生成）

```json
{
  "mcpServers": {
    "modao-proto-mcp": {
      "command": "node",
      "args": ["<全局npm路径>\\modao-proto-mcp\\cli.js"],
      "env": {
        "MODAO_TOKEN": "你的墨刀Token"
      }
    }
  }
}
```

Token 获取：登录 [墨刀](https://modao.cc) → 右上角头像 → 令牌设置 → 创建/查看 Token

### 摹客 RP MCP（Axure 原型提取）

```json
{
  "mcpServers": {
    "axure-mcp-server": {
      "command": "npx",
      "args": ["-y", "@axure-mcp/axure-proto-mcp"]
    }
  }
}
```

## 文件说明

每个 Skill 目录包含：
- `SKILL.md` — 技能说明与使用规则
- `scripts/` — Python/Shell 脚本（核心逻辑）
- `references/` — 参考文档（部分技能）
- `reference.md` / `forms.md` — 补充文档（部分技能）

## 注意事项

- 本目录不包含 API Token，请自行配置
- SkillHub 安装会自动下载最新版本，以 SkillHub 版本为准
- 部分 Skill 需要系统依赖（Python3、Node.js、ImageMagick 等），参考各 SKILL.md

## 同步方式

```bash
# 从 GitHub 拉取后，进入 skills 目录
cd skills

# 安装全部 Skill（逐个执行）
# 或使用 OpenClaw CLI 的 skillhub_install 功能
```

---

*本目录由 `skillhub_install` 安装的 Skill 源码组成，可在新设备上重建环境。*
