# 工作条件

- 主题：机器灌注条件下细胞外囊泡调控移植器官缺血再灌注损伤及早期排斥风险的机制与转化应用
- 英文检索主题：Extracellular vesicles and machine perfusion in transplant ischemia-reperfusion injury
- 时间窗：2021-06-03 至 2026-06-03
- 档位：Premium
- 输出目录：`reviews/ev-machine-perfusion-transplant-iri/`

## Search Plan

- 核心查询覆盖 EV、machine perfusion、normothermic machine perfusion、hypothermic oxygenated perfusion、transplant IRI、MSC-EV、perfusate biomarkers、dd-cfDNA。
- 检索源：OpenAlex 多查询检索，并用 PubMed 题名/日期线索复核近年关键文献。

## Search Log

- 多查询返回：400 篇。
- 合并去重后候选：229 篇。
- 候选库：`.systematic-literature-review/artifacts/papers_ev-machine-perfusion-transplant-iri.jsonl`
- 检索日志：`.systematic-literature-review/artifacts/search_log_ev-machine-perfusion-transplant-iri.json`

## Relevance Scoring & Selection

- 评分方法：按 EV 递送、IRI 固有免疫、机器灌注、灌注液标志物和临床转化进行语义分层。
- 选中文献：90 篇。
- 参考文献：`ev-machine-perfusion-transplant-iri_参考文献.bib`
- 选文文件：`.systematic-literature-review/artifacts/selected_papers_ev-machine-perfusion-transplant-iri.jsonl`

## Review Structure

- 摘要
- 引言
- IRI 的免疫机制
- 机器灌注作为 EV 递送窗口
- 灌注液 EV 与分子标志物
- 讨论：主要瓶颈
- 展望：未来 3-5 年研究方向
- 结论

## Validation

- 引用键已检查，无缺失。
- 已按 systematic-literature-review 默认骨架导出 Markdown、TeX、PDF、Word。
- PDF 导出存在少量参考文献非拉丁字符字体警告，不影响文件生成。
