# nsfc-demo 项目指令

本项目是「国家自然科学基金青年科学基金项目」标书 LaTeX 撰写 demo，用于演示 AI 辅助与中文科研 LaTeX 模板协作完成标书的流程。

## 项目目标

- 基于 [ChineseResearchLaTeX](https://github.com/huangwb8/ChineseResearchLaTeX) 的 `projects/NSFC_Young/` 模板撰写青年基金标书示例
- 产出可用 XeLaTeX 编译的 LaTeX 源码与成稿 PDF
- 定位为教学/演示材料，不作为真实申报文本

## 核心工作流

标书正文遵循青年科学基金常见结构，优先按任务阶段调用对应 `nsfc-*` skill：

| 环节 | 推荐 skill |
|------|------------|
| 摘要、中英文项目简介 | `nsfc-abstract` |
| 立项依据、研究意义、国内外现状 | `nsfc-justification-writer` |
| 研究目标、研究内容、关键科学问题、创新点、年度计划 | `nsfc-research-content-writer` |
| 研究方案、技术路线、机制图 | `nsfc-roadmap`、`nsfc-schematic` |
| 研究基础、工作条件、风险应对 | `nsfc-research-foundation-writer` |
| 经费预算 | `nsfc-budget` |
| 文献与引用核查 | `nsfc-bib-manager`、`nsfc-ref-alignment` |
| 篇幅、文风、质量与评审 | `nsfc-length-aligner`、`nsfc-humanization`、`nsfc-qc`、`nsfc-reviewers` |

交付顺序：

1. 准备 ChineseResearchLaTeX 青年基金模板
2. 分章撰写并补齐参考文献
3. 控制篇幅、润色文风、对齐模板
4. 使用 XeLaTeX 编译：`xelatex -> bibtex -> xelatex -> xelatex`
5. 质检、模拟评审并修订
6. 更新 `CHANGELOG.md` 与 BAC 账本

## 工具链与依赖

- LaTeX 模板：[ChineseResearchLaTeX](https://github.com/huangwb8/ChineseResearchLaTeX)，青年基金模板位于 `projects/NSFC_Young/`
- AI 技能：[huangwb8/skills](https://github.com/huangwb8/skills) 与 ChineseResearchLaTeX 相关 skill；以本机已安装 skill 为准
- 编译器：必须使用 XeLaTeX，不使用 pdflatex
- TeX 发行版：本机已具备 TeX Live 2024
- 其他依赖：Python 3；BAC 账本使用 `bac` 命令

## Skill 使用原则

- 用户明确点名 skill，或任务意图明显匹配某个 skill 职责时，必须使用对应 skill
- 多个 skill 适用时，选择覆盖需求的最小集合，并说明调用顺序
- 标书写作优先使用 `nsfc-*`、LaTeX、综述类 skill；通用工程 skill 仅在代码、测试、Git、发布或多代理协作任务中使用
- 下表是本项目常用 skill 速查，不替代本机已安装 skill 清单；如远端或本地 skill 变化，仅维护与本项目相关的条目
- 更新本指令或 skill 说明时同步更新 `CHANGELOG.md`

### 常用 Skill 速查

| Skill | 主要用途 |
|------|----------|
| `nsfc-abstract` | 生成或润色中文摘要、英文摘要、项目简介和题目建议 |
| `nsfc-justification-writer` | 写作或重构立项依据、研究意义、现状不足、科学问题与假说 |
| `nsfc-research-content-writer` | 编排研究目标、研究内容、关键科学问题、特色创新和年度计划 |
| `nsfc-research-foundation-writer` | 写作研究基础、工作条件、已有积累、风险应对和可行性证据链 |
| `nsfc-budget` | 生成经费预算说明，必要时输出可渲染的预算 LaTeX/PDF |
| `nsfc-roadmap` | 将研究内容转成可编辑、可嵌入标书的技术路线图 |
| `nsfc-schematic` | 将机制、算法架构或模块关系转成原理图/机制图 |
| `nsfc-length-aligner` | 检查篇幅分布，并在尽量不改原意的前提下扩写或压缩 |
| `nsfc-humanization` | 降低 AI 机器味，优化句式、节奏和专家写作质感 |
| `nsfc-qc` | 对标书做只读质量控制，检查文风、引用风险、篇幅结构和逻辑 |
| `nsfc-reviewers` | 模拟函评专家，输出分级问题和可执行修改建议 |
| `nsfc-code` | 基于标书正文推荐 NSFC 申请代码及理由 |
| `nsfc-bib-manager` | 新增、核验和整理参考文献及 BibTeX 条目 |
| `nsfc-ref-alignment` | 核查正文引用与 BibTeX 条目、文献语义的一致性风险 |
| `get-review-theme` | 从文件、图片、网页或描述中提取综述主题、关键词和核心问题 |
| `systematic-literature-review` | 执行系统综述流程：检索、筛选、评分、写作、引用管理和导出 |
| `paper-write-sci` | 面向 LaTeX 论文项目进行 SCI 论文撰写、修订、润色与渲染 |
| `paper-select-journal` | 基于 manuscript 和期刊信息生成投稿期刊推荐 |
| `check-review-alignment` | 核查综述正文引用与文献内容是否语义一致 |
| `complete-example` | 为 LaTeX 模板补充结构安全、连贯的示例内容 |
| `make-latex-model` | 调整 ChineseResearchLaTeX 模板样式与产品线参数，并按构建入口验收 |
| `transfer-old-latex-to-new` | 将旧 LaTeX、Word、PDF、Markdown 或零散正文迁移到新模板内容层 |
| `auto-test-project` | 对完整项目做多轮项目级测试、质量检查、问题修复和复验 |
| `auto-test-code` | 对代码做多轮审查、质量原则检查、问题记录和修复复验 |
| `awesome-code` | 在明确需要多代理协作时协调规划、实现、审查和整合 |
| `git-commit` | 分析 Git 改动并生成 conventional commit 信息，按需提交 |
| `git-pr-review` | 只读审查 GitHub PR，评估风险、质量和是否建议合并 |
| `git-publish-release` | 分析 tag 间历史，生成 Release Notes 并创建 GitHub Release |
| `init-project` | 初始化项目指令、README、CHANGELOG、Git 忽略规则和标准目录 |

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
