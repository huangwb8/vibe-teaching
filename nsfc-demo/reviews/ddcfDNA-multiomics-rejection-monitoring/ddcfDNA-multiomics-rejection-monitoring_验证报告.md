# 验证报告

- 主稿：`ddcfDNA-multiomics-rejection-monitoring_review.md`
- 参考文献库：90 条 BibTeX 记录
- 正文字符数：10339
- 引用键检查：通过，无缺失
- 导出文件：`.md`、原生 BibTeX `.tex`、`.pdf`、`.docx`
- 结构检查：按默认骨架包含摘要、引言、主体段、讨论、展望、结论；新增肾移植证据边界、器官差异、fraction/absolute quantity、多组学整合、机器灌注先验、AI 风险模型和决策试验细化内容
- 残余风险：PDF 参考文献区有少量字符字体警告；正文可读性与文件生成未受影响
- 篇幅说明：已由教学演示初稿扩写为更细致的临床证据-器官场景-决策模型讨论稿；仍未按 systematic-literature-review 默认 10000-15000 词长文强行扩展
- 样式检查：LaTeX 已改为 `ctex + natbib + BibTeX`，摘要使用 `abstract` 环境，参考文献由 `.bib` 文件生成
- 编译检查：按 `xelatex → bibtex → xelatex → xelatex` 成功生成 14 页 PDF，并用 Pandoc 重新导出 Word
