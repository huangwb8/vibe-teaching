# Changelog

本文件记录项目重要变更，格式遵循 Keep a Changelog，并优先维护 `[Unreleased]`。

## [Unreleased]

### Added（新增）

- AGENTS.md 新增 `huangwb8/ChineseResearchLaTeX` 与 `huangwb8/skills` 的 skill 清单：列出当前远端仓库中所有 skill 名称及一句作用简介，并补充“按实际任务调用必要 skill”的原则
- 新增 `reviews/` 系列综述交付物：围绕器官移植最近 5 年进展生成 EV/机器灌注、dd-cfDNA/多组学监测、猪到人异种移植临床进展三篇综述，并导出 Markdown、TeX、PDF、Word 与 BibTeX 参考库
- AGENTS.md 新增「工具链与依赖」章节：说明 ChineseResearchLaTeX 模板（青年标书模板位于 `projects/NSFC_Young/`）、huangwb8/skills 技能集与 XeLaTeX 编译环境
- AGENTS.md「核心工作流」新增标书结构与 `nsfc-*` 技能映射表及撰写交付流程
- `.gitignore` 新增 LaTeX 编译中间产物忽略规则（保留成稿 PDF）

### Changed（变更）

- 按 `init-project` 2.3.2 最新规范优化系统文件：补齐 AGENTS.md 必需章节命名、有机更新原则和代码修改闭环约束，并扩展 `.gitignore` 对 AI/skill 中间产物目录的忽略规则
- 移除 AGENTS.md 中具体 AI 辅助能力名称、推荐映射表与职责速查：改为通用阶段化工作流说明，降低项目指令对具体工具清单的依赖
- 精简 AGENTS.md：将冗长的远端 skill 全量清单压缩为项目常用 skill 速查，保留项目目标、核心 workflow、必要 skill 映射、编译、BAC 和变更记录规则
- 为 `ev-machine-perfusion-transplant-iri` 综述插入 4 张机制/平台/质控/标志物决策表：增强 EV 在机器灌注语境下的角色区分、递送窗口、最小证据包和灌注液标志物框架，并重新导出 TeX/PDF/Word
- 细化 `pig-to-human-xenotransplantation-clinical-progress` 综述：扩写临床时间线、供体猪工程、猪肾/猪心/猪肝/猪肺器官差异、免疫感染伦理监管和未来 3-5 年研究方向，并重新导出 TeX/PDF/Word
- 细化 `ev-machine-perfusion-transplant-iri` 与 `ddcfDNA-multiomics-rejection-monitoring` 两篇综述：分别扩写 EV/机器灌注的机制、递送、标志物和转化试验设计，以及 dd-cfDNA/多组学监测的器官场景、证据边界和决策模型，并重新导出 PDF/Word
- 使用 `nsfc-humanization` 对 `reviews/` 系列综述正文做去机器味润色：保留引用、数字、章节结构和证据边界，优化模板化句式与过度对称表达
- 统一 `reviews/` 三篇综述的默认样式：Markdown 章节改为“摘要 / 引言 / 主体段 / 讨论 / 展望 / 结论”骨架，LaTeX 改为 `ctex + natbib + BibTeX` 原生模板，并重新导出 PDF 与 Word
- 将 AGENTS.md / README.md 由「通用项目」模板定制为「国自然青年科学基金标书 demo」：明确项目目标、产出物与 demo 定位

## [1.0.0] - 2026-06-03

### Added（新增）

- 初始化 AI 项目指令文件：生成 `AGENTS.md`、`CLAUDE.md`、`README.md` 与 `.gitignore`
- 配置项目工程原则、工作流和变更记录规范
- 初始化 BAC 贡献记录：默认托管文件为 `docs/contribution.bac`

### Changed（变更）

### Fixed（修复）

---

## 记录规则

- 必须记录影响项目行为、结构、工作流、工程原则、指令文件或关键配置的变更
- 记录应说明改了什么、为什么改，以及影响范围
- 版本号遵循 SemVer：bug fix 递增修订号，新功能递增次版本号，破坏性变更递增主版本号

```markdown
## [版本号] - YYYY-MM-DD

### Added（新增）
- 新增了 XXX：用途是 YYY

### Changed（变更）
- 修改了 XXX：原因是 YYY，影响是 ZZZ

### Fixed（修复）
- 修复了 XXX：表现是 YYY，修复方式是 ZZZ
```
