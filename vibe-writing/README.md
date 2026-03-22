# vibe-writing

通用项目，遵循工程最佳实践

## 特性

- 模块化设计
- 可扩展架构
- 完善的文档

## 快速开始

### 环境要求

- 根据项目需求配置

### 安装

```bash
# 根据项目需求进行安装
```

### 使用

```bash
# 根据项目需求运行
```

## 目录结构

```
vibe-writing/
└── vibe-writing.code-workspace
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
5. **变更记录**：**重要** - 凡是项目的更新，都要统一在 `CHANGELOG.md` 文件里记录。这是项目管理的强制性要求。

## 贡献

欢迎提交 Issue 和 Pull Request。

## 许可证

MIT License
