# 工作条件

- 主题：供者来源游离 DNA 与多组学标志物在实体器官移植排斥监测中的应用价值与未来方向
- 英文检索主题：Donor-derived cell-free DNA and multiomic biomarkers for transplant rejection monitoring
- 时间窗：2021-06-03 至 2026-06-03
- 档位：Premium
- 输出目录：`reviews/ddcfDNA-multiomics-rejection-monitoring/`

## Search Plan

- 核心查询覆盖 dd-cfDNA、kidney/heart/lung/liver transplantation、ABMR、DSA、urine/exosome biomarkers、multiomics、machine perfusion biomarkers。
- 检索源：OpenAlex 多查询检索，并用 PubMed 复核近年综述、指南、系统评价和临床验证研究。

## Search Log

- 多查询返回：357 篇。
- 合并去重后候选：287 篇。
- 候选库：`.systematic-literature-review/artifacts/papers_ddcfDNA-multiomics-rejection-monitoring.jsonl`
- 检索日志：`.systematic-literature-review/artifacts/search_log_ddcfDNA-multiomics-rejection-monitoring.json`

## Relevance Scoring & Selection

- 评分方法：围绕肾移植临床验证、心/肺/肝应用、ABMR/DSA、尿液外泌体与转录组、整合风险模型进行语义分层。
- 选中文献：90 篇。
- 参考文献：`ddcfDNA-multiomics-rejection-monitoring_参考文献.bib`
- 选文文件：`.systematic-literature-review/artifacts/selected_papers_ddcfDNA-multiomics-rejection-monitoring.jsonl`

## Review Structure

- 摘要
- 引言
- 肾移植证据与边界
- 心、肺、肝与多器官移植应用
- 多组学整合
- 讨论：临床应用场景与解释边界
- 展望：未来 3-5 年研究方向
- 结论

## Validation

- 引用键已检查，无缺失。
- 已按 systematic-literature-review 默认骨架导出 Markdown、TeX、PDF、Word。
- PDF 导出存在少量参考文献字符警告，不影响文件生成。

