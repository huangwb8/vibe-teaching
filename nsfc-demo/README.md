# nsfc-demo

国家自然科学基金 青年科学基金项目标书的 LaTeX 撰写 demo —— 演示「AI 辅助 + 中文科研 LaTeX 模板」协作写标书的完整流程。

> 教学/演示用途，非真实申报材料。

## 特性

- 基于 [ChineseResearchLaTeX](https://github.com/huangwb8/ChineseResearchLaTeX) 的 `projects/NSFC_Young/` 青年基金模板
- 配合 `nsfc-*` 系列 AI 技能分章撰写（摘要、立项依据、研究内容、预算、路线图等）
- XeLaTeX 一键编译为 PDF

## 快速开始

### 环境要求

- TeX Live / MacTeX（含 XeLaTeX、bibtex、latexmk）
- Python 3（部分模板对齐脚本依赖）
- 已安装 [huangwb8/skills](https://github.com/huangwb8/skills) 中的 `nsfc-*` 系列与 `make-latex-model` 技能

### 获取模板

```bash
# 在项目根目录获取国自然 LaTeX 模板（二选一）
git clone https://github.com/huangwb8/ChineseResearchLaTeX.git
# 或作为子模块
git submodule add https://github.com/huangwb8/ChineseResearchLaTeX.git
```

### 编译

```bash
# 进入青年基金模板目录（projects/NSFC_Young/），对主文件使用 XeLaTeX 编译
latexmk -xelatex <主文件>.tex
# 或手动按顺序编译
xelatex <主文件>.tex && bibtex <主文件> && xelatex <主文件>.tex && xelatex <主文件>.tex
```

## 目录结构

```
nsfc-demo/
├── ChineseResearchLaTeX/   # 国自然 LaTeX 模板（需自行获取，含 projects/NSFC_Young/）
├── docs/                   # 文档
│   └── plans/              # AI 计划文档
├── AGENTS.md               # 通用项目指令（Single Source of Truth）
├── CLAUDE.md               # Claude Code 适配（@./AGENTS.md）
├── CHANGELOG.md            # 变更记录
└── Prompts.md              # 需求记录
```

## AI 辅助开发

本项目配置了 AI 辅助开发支持，可以使用以下工具进行智能开发：

### Claude Code

使用 `CLAUDE.md` 作为项目指令。

```bash
# 在项目目录启动 Claude Code
claude

# Claude Code 会自动读取 CLAUDE.md 理解项目上下文
```

### OpenAI Codex CLI

使用 `AGENTS.md` 作为项目指令。

```bash
# 在项目目录启动 Codex CLI
codex

# Codex 会自动读取 AGENTS.md 理解项目上下文
```

### AI 开发最佳实践

1. **新功能开发**：描述需求，AI 会按照项目工作流进行开发
2. **代码审查**：请求 AI 审查代码，它会按照工程原则给出建议
3. **文档更新**：AI 会自动同步更新相关文档
4. **问题排查**：描述问题现象，AI 会分析并给出解决方案
5. **贡献记录**：默认使用 `docs/contribution.bac` 记录人类与 AI 协作过程；如项目决定关闭，可在初始化时使用 `--disable-bac`
6. **变更记录**：**重要** - 凡是项目的更新，都要统一在 `CHANGELOG.md` 文件里记录。这是项目管理的强制性要求。

## 贡献

欢迎提交 Issue 和 Pull Request。

## 许可证

MIT License
