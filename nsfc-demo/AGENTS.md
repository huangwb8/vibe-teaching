# nsfc-demo - 项目指令

本项目是「国家自然科学基金 青年科学基金项目」标书的 LaTeX 撰写 demo，演示「AI 辅助 + 中文科研 LaTeX 模板」协作完成标书的完整流程。

## 项目目标

基于 [ChineseResearchLaTeX](https://github.com/huangwb8/ChineseResearchLaTeX) 的 `projects/NSFC_Young/` 青年基金模板，配合 [huangwb8/skills](https://github.com/huangwb8/skills) 的 `nsfc-*` 系列 AI 技能，撰写并用 XeLaTeX 编译一份结构完整的国自然青年科学基金标书示例。

- 产出物：可编译为 PDF 的标书 LaTeX 源码及成稿 PDF
- 定位：教学/演示用 demo，非真实申报材料

## 核心工作流

本项目围绕「国自然青年标书」的撰写与编译展开。标书正文遵循青年科学基金的标准结构，各环节优先调用对应的 `nsfc-*` skill 辅助。

### 标书结构与对应技能

| 标书环节 | 说明 | 推荐 skill |
|---------|------|-----------|
| 摘要 | 中英文摘要、项目简介 | `nsfc-abstract` |
| 立项依据 | 研究意义、国内外现状、文献支撑 | `nsfc-justification-writer`、`nsfc-research-foundation-writer` |
| 研究目标/内容/关键科学问题 | 研究目标、研究内容、拟解决的关键科学问题 | `nsfc-research-content-writer` |
| 研究方案与技术路线 | 研究方案、可行性分析、技术路线图 | `nsfc-roadmap`、`nsfc-schematic` |
| 研究基础与工作条件 | 已有工作基础、研究条件、承担项目 | `nsfc-research-foundation-writer` |
| 经费预算 | 预算编制与说明 | `nsfc-budget` |
| 参考文献 | 文献管理与引用对齐 | `nsfc-bib-manager`、`nsfc-ref-alignment` |
| 代码/算法（如涉及） | 算法或数据分析代码 | `nsfc-code` |

### 撰写与交付流程

1. 准备模板：获取 ChineseResearchLaTeX，以 `projects/NSFC_Young/` 为 demo 基础
2. 分章撰写：按上表调用对应 skill 生成/完善各章节内容
3. 篇幅与润色：用 `nsfc-length-aligner` 控制篇幅，`nsfc-humanization` 润色行文
4. 模板对齐：版式调整用 `make-latex-model`，旧 LaTeX 迁移用 `transfer-old-latex-to-new`
5. 编译：使用 XeLaTeX，顺序为 `xelatex → bibtex → xelatex → xelatex`
6. 质检与模拟评审：用 `nsfc-qc` 自检，`nsfc-reviewers` 模拟函评
7. 记录变更：更新 `CHANGELOG.md`，并由 BAC 账本记录协作过程

## 工具链与依赖

### LaTeX 模板：ChineseResearchLaTeX

- 来源：https://github.com/huangwb8/ChineseResearchLaTeX
- 用途：提供国自然 / 论文 / 学位论文 / 简历的中文科研 LaTeX 模板
- 青年标书模板目录：`projects/NSFC_Young/`
- 公共样式包：`packages/bensz-*`（字体、NSFC 样式等）
- 当前状态：**尚未引入项目**，需先 clone 到项目内（如 `./ChineseResearchLaTeX/` 或作为 git submodule）

### AI 技能：ChineseResearchLaTeX 与 huangwb8/skills

- 来源：https://github.com/huangwb8/ChineseResearchLaTeX 与 https://github.com/huangwb8/skills
- 用途：提供 `nsfc-*` 系列标书写作、LaTeX 模板、文献综述、工程协作、测试、Git 与 skill 维护工具
- 当前状态：相关 skill 已安装在本机 `~/.claude/skills/`，可直接通过 Skill 调用

#### Skill 调用原则

- 根据任务实际情况调用必要的 skill：用户明确点名某个 skill，或任务意图明显匹配某个 skill 的职责时，才调用对应 skill
- 多个 skill 同时适用时，选择能覆盖任务的最小必要集合，并说明调用顺序；不要为了形式完整而机械调用全部 skill
- 优先调用与当前标书阶段直接对应的 `nsfc-*` / LaTeX / 综述类 skill；通用工程类 skill 仅在任务涉及代码、测试、Git、发布或多代理协作时使用
- 若 skill 清单与远端仓库更新不一致，应以当前本地已安装 skill 和项目实际需求为准，并在更新清单时同步更新 `CHANGELOG.md`

#### huangwb8/ChineseResearchLaTeX skills

以下清单按 `huangwb8/ChineseResearchLaTeX` 当前远端 `skills/` 目录整理，用于科研写作、NSFC 标书、LaTeX 模板与综述交付。

| Skill | 作用简介 |
|------|----------|
| `check-review-alignment` | 核查综述 LaTeX 正文引用与文献内容是否语义一致，并在致命错引时做最小改写与渲染。 |
| `complete-example` | 为 LaTeX 模板补充示例内容，在保护结构的前提下生成连贯示例叙述。 |
| `get-review-theme` | 从文件、图片、网页或自然语言描述中提取综述主题、关键词和核心问题。 |
| `guide-updater` | 将对话中新形成的可复用写作洞见沉淀到指定项目指南文件。 |
| `make-latex-model` | 优化 ChineseResearchLaTeX 模板样式与产品线参数，并按官方构建入口验收。 |
| `nsfc-abstract` | 生成或润色 NSFC 标书中文摘要、英文摘要和题目建议。 |
| `nsfc-budget` | 生成 NSFC 预算说明书 LaTeX 项目并渲染预算说明 PDF。 |
| `nsfc-code` | 基于标书正文推荐 5 组 NSFC 申请代码及理由，默认只读输出报告。 |
| `nsfc-humanization` | 去除 NSFC 标书文本中的 AI 机器味，使表达更接近资深领域专家写作。 |
| `nsfc-justification-writer` | 写作或重构 NSFC 立项依据，包括研究意义、现状不足、科学问题与假说。 |
| `nsfc-length-aligner` | 检查 NSFC 标书篇幅分布，并在尽量不改原意的前提下扩写或压缩到目标篇幅。 |
| `nsfc-qc` | 对 NSFC 标书做只读质量控制，检查文风、引用风险、篇幅结构和逻辑清晰度。 |
| `nsfc-ref-alignment` | 核查 NSFC 标书正文引用与 BibTeX 条目的一致性和真实性风险。 |
| `nsfc-research-content-writer` | 编排写作 NSFC 研究内容、特色与创新、三年年度研究计划。 |
| `nsfc-research-foundation-writer` | 编排写作 NSFC 研究基础、工作条件和风险应对，突出可行性证据链。 |
| `nsfc-reviewers` | 模拟专家评审 NSFC 标书，输出分级问题和可执行修改建议。 |
| `nsfc-roadmap` | 将 NSFC 研究内容转成可编辑、可嵌入文档的技术路线图。 |
| `nsfc-schematic` | 将研究机制、算法架构或模块关系转成可编辑的原理图或机制图。 |
| `paper-explain-figures` | 解读论文 Figure 并生成教会读者读图的 Markdown 报告。 |
| `paper-select-journal` | 基于 manuscript、影响因子数据和联网核验生成 SCI 选刊推荐报告。 |
| `paper-write-sci` | 面向 LaTeX 论文项目进行 SCI 论文撰写、修订、润色与渲染闭环。 |
| `systematic-literature-review` | 执行检索、筛选、评分、写作、引用管理和 PDF/Word 导出的系统综述流水线。 |
| `transfer-old-latex-to-new` | 将旧 LaTeX、Word、PDF、Markdown 或零散正文迁移到 ChineseResearchLaTeX 内容层。 |

#### huangwb8/skills skills

以下清单按 `huangwb8/skills` 当前远端仓库整理，用于通用项目初始化、测试、Git 工作流、提示词优化、多代理开发和 skill 维护。

| Skill | 作用简介 |
|------|----------|
| `auto-draw-plot` | 根据用户绘图需求生成高质量图片 prompt，并调用图像模型迭代产出 PNG。 |
| `auto-test-code` | 对代码进行多轮批判性审查、质量原则检查、问题记录和修复复验。 |
| `auto-test-project` | 对完整项目执行多轮项目级测试、质量检查、问题修复和复验。 |
| `auto-test-skill` | 对 Agent Skill 执行批判性测试、质量原则检查和可追溯文档沉淀。 |
| `awesome-code` | 协调多代理软件开发，按任务复杂度选择单轮、聚焦、并行或串行策略。 |
| `backend-specialist` | 处理后端服务、API 设计、数据库、认证授权、微服务与性能优化任务。 |
| `brainstorming` | 在明确要求设计讨论时进行交互式方案探索和设计优化。 |
| `code-reviewer` | 对实现结果进行代码审查，按严重性指出缺陷、风险和缺失测试。 |
| `context-optimizer` | 优化长对话上下文、token 效率和复杂任务中的上下文管理策略。 |
| `devops-specialist` | 处理 CI/CD、容器化、编排、基础设施即代码、监控告警和自动部署。 |
| `documentation-specialist` | 编写和维护技术文档、API 文档、README 与用户友好说明。 |
| `frontend-specialist` | 实现现代前端应用、设计系统、响应式界面、性能优化和用户体验改进。 |
| `git-workflow` | 规范 Git 分支、提交、Pull Request 和 Conventional Commits 工作流。 |
| `mirror-optimizer` | 为 Docker、Python、Node.js、Go 等包管理和部署场景配置镜像源加速。 |
| `multi-agent-coordinator` | 将独立实现任务分派给多个代理，并在任务间加入审查门禁。 |
| `security-specialist` | 执行应用安全、威胁建模、漏洞扫描、安全配置和合规检查。 |
| `systematic-debugging` | 在修复 bug 前执行根因调查、模式分析、假设验证和修复实施。 |
| `tdd-workflow` | 在功能或 bugfix 实现前执行红绿重构式测试驱动开发流程。 |
| `writing-plans` | 在多步骤代码任务开始前，把需求拆解成可执行计划。 |
| `bensz-collect-bugs` | 记录 Bensz 系列 skills 的设计缺陷，并在明确要求时公开上报。 |
| `better-prompt` | 按 OpenAI 和 Anthropic 最佳实践优化、改写或润色用户提示词。 |
| `compact-bensz-skills` | 在不改变功能的前提下压缩 Agent Skill Markdown 上下文。 |
| `git-commit` | 分析 Git 改动并生成 conventional commit 信息，按需提交和推送。 |
| `git-pr-review` | 只读审查 GitHub Pull Request，评估风险、质量和是否建议 merge。 |
| `git-publish-release` | 分析 tag 间历史变化，生成 Release Notes 并创建 GitHub Release。 |
| `init-project` | 初始化项目指令、README、CHANGELOG、Git 忽略规则和标准 docs 目录。 |
| `install-bensz-skills` | 将本仓库或远端 skills 安装到 Codex 与 Claude Code 的系统级目录。 |
| `parallel-vibe` | 在多个独立工作区并行尝试同一 Vibe Coding 指令并汇总结果。 |
| `write-skill-readme` | 为 Agent Skill 自动生成面向使用者的 README 用户指南。 |

### 编译环境

- 编译器：**必须使用 XeLaTeX**（不可用 pdflatex）
- 编译顺序：`xelatex → bibtex → xelatex → xelatex`
- 发行版：TeX Live / MacTeX（本机已具备 TeX Live 2024）
- 其他：Python 3（部分构建 / 模板对齐脚本依赖）

## 项目目录约定

- `./tmp`：临时文件与测试中间产物，可不定期清理
- `./tests`：质检用测试脚本及相关软件结构
- `./docs`：解释性文档、教程等非计划类文档
- `./docs/plans`：AI 为解决特定问题而制定的计划文档

## 工程原则

本项目遵循以下工程原则：

| 原则 | 核心思想 | 在本项目中的体现 |
|------|----------|------------------|
| **KISS** | Keep It Simple, Stupid | 追求极致简洁，避免过度设计；文档标题不使用序号前缀（用 `##` 而非 `## 1)`） |
| **YAGNI** | You Aren't Gonna Need It | 只实现当前需要的功能 |
| **DRY** | Don't Repeat Yourself | 相似逻辑应抽象复用 |
| **SOLID** | 面向对象设计五大原则 | 单一职责、开闭原则等 |
| **关注点分离** | Separation of Concerns | 不同层次逻辑应分离 |
| **奥卡姆剃刀** | 如无必要，勿增实体 | 优先选择最简单的解决方案；Markdown 本身有层级结构，序号是冗余的形式化标记 |
| **最小惊讶原则** | Principle of Least Astonishment | API 行为应符合用户直觉 |
| **早期返回原则** | Early Return | 尽早返回，减少嵌套 |

**原则冲突时的决策优先级**：
1. **正确性 > 一切**
2. **简洁性 > 灵活性**
3. **清晰性 > 性能**
4. **扩展性 > 紧凑性**

## 默认语言

除非用户明确要求其他语言，始终使用 简体中文 与用户对话与撰写文档/说明。

## 联网与搜索

默认优先使用项目内文件与本地上下文；确需联网获取信息时，优先使用本地搜索工具。仅当本地工具不足以满足需求时再使用其它联网手段，并说明原因与保留关键链接。

## 贡献记录

本项目默认且强制基于 [bensz-auto-contribution](https://github.com/huangwb8/bensz-auto-contribution) 使用 `bac` 工具，客观记录人类与 AI 的协作贡献边界。默认贡献托管文件为 `docs/contribution.bac`；初始化项目时必须检查 Python 环境、确认 `bac` 包可用；若环境未配置好，必须自动安装该 Python 依赖并初始化账本。

- BAC 是默认强制执行步骤；除非项目负责人明确要求使用脚本级 `--disable-bac` 逃生开关，否则不得跳过依赖检查、安装与账本初始化
- 记录应忠实反映需求来源、AI 生成内容、工具执行结果、人工确认、文件改动与验证证据
- 不把 BAC 当作最终署名或责任裁判；它是过程记录与辅助审计材料
- 不记录敏感密钥、完整私有提示词或无关个人隐私

## 代码优化与修改

当判断用户意图与代码优化或修改相关时：

- 允许多代理协作； 特别推荐使用 `awesome-code` skill 辅助规划与优化。
- 发现的所有问题必须全部解决，不留已知缺陷
- 如遇疑问或存在更优方案，自主决定最优方案执行，不中断工作流询问用户
- 不得破坏已有功能，确保最终成品正常、稳定、高效地工作

### 前端优化后质检

当代码更改涉及前端 UI 优化时，应在 `./tmp/img-frontend/run-{时间戳}` 目录下保存改动前后的对比截图（jpg 格式），利用模型的视觉智能判断任务完成情况来决定是否需要进一步优化。

## Codex CLI 特定说明

### 文件与输出

- 引用文件时使用可点击路径，并尽量带起始行号：`src/main.py:42`
- 不输出刚写入的大文件内容，只引用路径并说明变更
- 简单确认避免复杂格式；结束时给出简短后续步骤

### 编辑原则

- 只修改与当前任务直接相关的文件
- 保持现有代码风格、结构和类型安全
- 读取足够上下文后再批量处理相关修改
- 无效输入早返回，遵循项目既有日志/通知模式

## 变更记录与版本

- 影响项目行为、结构、工作流、工程原则或指令文件的变更，必须更新 `CHANGELOG.md`
- 修改 `AGENTS.md` 后，应同步检查 `CLAUDE.md` 的核心内容是否一致
- `CHANGELOG.md` 遵循 Keep a Changelog；优先记录到 `[Unreleased]`
- 如项目启用版本号，以配置文件为唯一来源，并遵循 SemVer：bug fix 递增修订号，新功能递增次版本号，破坏性变更递增主版本号

## 有机更新原则

当需要更新本文档时：

- 先理解变更意图，再把规则放到最合适的章节，避免重复堆叠
- 更新工作流、输出规范或术语时，同步检查相关示例、验证清单和引用位置
- 计划文档统一保存在 `./docs/plans/`
- 代码变化导致 `docs/` 中非 `plans/` 文档过时时，必须同步更新
- 文档标题不使用序号前缀，保持 Markdown 层级清晰
