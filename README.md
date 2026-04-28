# PM Agent 工作流

> 不想被蒸馏，那就先蒸馏自己。

把资深产品经理的思考路径、判断逻辑、经验规则结构化，让 AI 学会像 PM 一样思考。

---

## 📁 仓库结构

```
pm-agent/
├── README.md                              ← 本文件
├── .gitignore                             ← 忽略本地配置和输出文件
├── workflow/
│   └── PM_Agent_工作流_v2.2.md           ← 主工作流（意图驱动智能路由器）
├── prompts/
│   ├── 公众号选题规则.md                 ← 4周轮换选题规则 Prompt
│   └── 公众号内容创作自动化流程.md       ← 全流程自动化 Prompt
└── config/
    └── config-template.json               ← 配置文件模板（复制后填写）
```

---

## 🚀 快速上手

### 第一步：克隆仓库

```bash
git clone https://github.com/bigsmart-zhu/pm-agent.git
cd pm-agent
```

### 第二步：配置本地环境

```bash
cp config/config-template.json config/config.json
# 编辑 config.json，填入你的 API Key 和路径
```

### 第三步：使用工作流

将 `workflow/PM_Agent_工作流_v2.2.md` 的内容复制到 AI 助手（WorkBuddy / Claw / ChatGPT 等），即可启动 PM 工作流。

---

## 📋 工作流模块

| 模块 | 功能 | 核心判断 |
|------|------|----------|
| ① 需求发现 | 问题陈述 + 证据 + 功能清单 | 这个问题真不真？ |
| ② 机会评估 | Build/Explore/Defer/Kill | 为什么是现在？ |
| ③ PRD 撰写 | 完整 PRD 文档 | 这个需求能执行吗？ |
| ④ 设计方案 | 结构化描述 + AI 设计工具 Prompt | 用户能顺畅走完吗？ |
| ⑤ 度量追踪 | 指标体系 + 埋点方案 | 怎么知道做对了？ |
| ⑥ 复盘优化 | 归因分析 + 迭代方案 | 为什么没达预期？ |

---

## 📰 公众号自动化（AI前沿）

| 文件 | 功能 |
|------|------|
| `prompts/公众号选题规则.md` | 4周轮换机制：新闻/深度/工具/案例 |
| `prompts/公众号内容创作自动化流程.md` | 热点抓取 → 选题 → 文章生成 → 草稿箱发布 |

---

## 🔄 更新方式

```bash
# 拉取最新版本
git pull origin main

# 推送本地更新（修改 workflow 或 prompts 后）
git add .
git commit -m "feat: 描述你的改动"
git push origin main
```

---

## ⚠️ 注意事项

- `config/config.json` 包含敏感信息，**已被 .gitignore 忽略，不会上传 GitHub**
- 本地的 `output/` 和 `context/` 目录也不会同步
- Mac 和 Windows 使用同一份 `config-template.json`，各自在本地填入对应路径

---

*当前版本：v2.2*
*维护者：明天要去动物园了*
