# 工作条件

- 主题：猪器官移植到人：2021-2026 年临床进展、关键风险与未来 3-5 年研究方向
- 英文检索主题：Pig-to-human xenotransplantation clinical progress and translational research directions
- 时间窗：2021-06-03 至 2026-06-06
- 档位：Premium
- 输出目录：`reviews/pig-to-human-xenotransplantation-clinical-progress/`

## Search Plan

- 核心查询覆盖 pig kidney xenotransplantation、pig heart xenotransplantation、human/decedent/living recipient、gene-edited donor pigs、infection surveillance、PERV/PCMV、clinical trial ethics and regulation。
- 检索源：OpenAlex 多查询检索；PubMed/Crossref/ClinicalTrials.gov 复核关键临床节点和试验记录；2026-06-06 额外联网核验 FDA/IND clearance 公告节点。

## Search Log

- 多查询返回：387 篇。
- 合并去重后候选：294 篇。
- 候选库：`.systematic-literature-review/artifacts/papers_pig-to-human-xenotransplantation-clinical-progress.jsonl`
- 检索日志：`.systematic-literature-review/artifacts/search_log_pig-to-human-xenotransplantation-clinical-progress.json`

## Relevance Scoring & Selection

- 评分方法：按人体猪肾/猪心应用、基因编辑供体设计、免疫/补体/凝血损伤、感染监管、伦理和临床试验准备进行语义分层。
- 选中文献：90 篇；另补充 3 条 NEJM 关键临床文献与 3 条 2025-2026 年临床试验公告来源到 BibTeX。
- 参考文献：`pig-to-human-xenotransplantation-clinical-progress_参考文献.bib`
- 选文文件：`.systematic-literature-review/artifacts/selected_papers_pig-to-human-xenotransplantation-clinical-progress.jsonl`

## Review Structure

- 摘要
- 引言
- 转化时间线与临床证据格局
- 供体猪工程
- 猪肾临床路径
- 猪心经验与试验化边界
- 猪肝、猪肺与机器灌注
- 讨论：免疫、感染、伦理与监管
- 展望：未来 3-5 年研究方向
- 结论

## Validation

- 引用键已检查：正文引用键 38 个，BibTeX 无缺失。
- 已重新导出 Markdown、TeX、PDF、Word；PDF 为 14 页，`pdftotext` 可正常抽取中文。
- Word 导出存在 Pandoc `zh-CN` 术语翻译提示，不影响 `.docx` 文件生成；LaTeX 编译无缺失引用或缺字警告。
