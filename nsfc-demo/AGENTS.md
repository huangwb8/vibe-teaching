# nsfc-demo 项目指令

本项目是「国家自然科学基金青年科学基金项目」标书 LaTeX 撰写 demo，用于演示 AI 辅助与中文科研 LaTeX 模板协作完成标书的流程。

## 项目目标

- 基于 [ChineseResearchLaTeX](https://github.com/huangwb8/ChineseResearchLaTeX) 的 `projects/NSFC_Young/` 模板撰写青年基金标书示例
- 产出可用 XeLaTeX 编译的 LaTeX 源码与成稿 PDF
- 定位为教学/演示材料，不作为真实申报文本

## 核心工作流

标书正文遵循青年科学基金常见结构，按任务阶段组织写作、校对、编译和质检。

交付顺序：

1. 准备 ChineseResearchLaTeX 青年基金模板
2. 分章撰写并补齐参考文献
3. 控制篇幅、润色文风、对齐模板
4. 使用 XeLaTeX 编译：`xelatex -> bibtex -> xelatex -> xelatex`
5. 质检、模拟评审并修订
6. 更新 `CHANGELOG.md` 与 BAC 账本

## 工具链与依赖

- LaTeX 模板：[ChineseResearchLaTeX](https://github.com/huangwb8/ChineseResearchLaTeX)，青年基金模板位于 `projects/NSFC_Young/`
- AI 辅助能力以当前运行环境为准，项目指令中不维护具体名称清单
- 编译器：必须使用 XeLaTeX，不使用 pdflatex
- TeX 发行版：本机已具备 TeX Live 2024
- 其他依赖：Python 3；BAC 账本使用 `bac` 命令

## 目录约定

- `tmp/`：临时文件与测试中间产物
- `tests/`：质检测试脚本及相关结构
- `docs/`：解释性文档、教程等非计划类文档
- `docs/plans/`：AI 为特定问题制定的计划文档
- `docs/contribution.bac`：默认 BAC 贡献记录账本

## 工程原则

- 正确性优先，其次是简洁性、清晰性和可维护性
- 遵循 KISS、YAGNI、DRY 与关注点分离，避免无关重构
- 文档标题不使用序号前缀，依靠 Markdown 层级表达结构
- 只修改与当前任务直接相关的文件；读取足够上下文后再批量编辑
- 涉及前端 UI 优化时，在 `tmp/img-frontend/run-{时间戳}` 保存改动前后 jpg 截图并做视觉质检

## 默认沟通与搜索

- 除非用户明确要求其他语言，始终使用简体中文对话与撰写说明
- 默认优先使用项目内文件与本地上下文；确需联网时说明原因并保留关键链接

## BAC 贡献记录

本项目强制使用 [bensz-auto-contribution](https://github.com/huangwb8/bensz-auto-contribution) 的 `bac` 工具记录协作过程，默认账本为 `docs/contribution.bac`。

- 初始化或修改项目时检查 `bac` 是否可用；不可用时自动安装依赖并初始化账本
- 忠实记录需求来源、AI 生成内容、工具执行结果、人工确认、文件改动与验证证据
- 不记录敏感密钥、完整私有提示词或无关个人隐私
- BAC 是过程审计材料，不替代最终署名或责任判断

## 变更记录

- 影响项目行为、结构、工作流、工程原则或指令文件的变更，必须更新 `CHANGELOG.md`
- 修改 `AGENTS.md` 后，同步检查 `CLAUDE.md` 核心内容是否一致
- `CHANGELOG.md` 遵循 Keep a Changelog，优先记录到 `[Unreleased]`
- 如启用版本号，以配置文件为唯一来源，并遵循 SemVer

## Codex CLI 约定

- 引用文件时使用可点击路径，并尽量带起始行号
- 不输出刚写入的大文件内容，只引用路径并说明变更
- 简单确认避免复杂格式；结束时给出简短后续步骤
- 无效输入早返回，并遵循项目既有日志或通知模式
