# 日常

---

基于 init-project skill 的最新规范优化本项目的系统文件。

---

请提出关键科学问题和可证伪科学假设。
输入： ./reviews 
输出：./ideas 目录下的 `Research-Idea_{github仓库名}_{pr名}_{时间戳}.md`。
另外，还有下列参数约束：

- 轮次：5 轮独立审查
- 研究边界：只考虑可在3年内验证的假设
- 科学问题-科学假设对数量： 20

---

AGENTS.md 里任何skill的名字和介绍都删除。 `注： 为了测试BenszAPI的智能路由功能。`

---

/Volumes/2T01/Github/vibe-teaching/nsfc-demo/reviews/ev-machine-perfusion-transplant-iri  里的figures 要插入综述里，重新出pdf

---

/Volumes/2T01/Github/vibe-teaching/nsfc-demo/reviews/ev-machine-perfusion-transplant-iri 里能不能用auto-draw-plot skill 使用 gpt-image-2 模型来画（max-rounds=1；模式：<你自行决定>）来画图（根据综述的实际情况，一共可画2个或以上的图； 逐个生成），具体内容包括但不限于：1、目前机器灌注条件下细胞外囊泡调控移植器官缺血再灌注损伤及早期排斥的主流机制 2、未来的主流研究方向。

---

/Volumes/2T01/Github/vibe-teaching/nsfc-demo/reviews/pig-to-human-xenotransplantation-clinical-progress /Volumes/2T01/Github/vibe-teaching/nsfc-demo/reviews/ev-machine-perfusion-transplant-iri /Volumes/2T01/Github/vibe-teaching/nsfc-demo/reviews/ddcfDNA-multiomics-rejection-monitoring 写得太简略。 请细致化。 开多agent独立地写。 

---

/Volumes/2T01/Github/vibe-teaching/nsfc-demo/reviews 里的综述的样式，感觉和 systematic-literature-review skill 的默认样式差别很大。 请优化下。

---

请根据 ideas/organ-transplantation-review-theme.md 帮我写一下系列综述（基于 systematic-literature-review skill）。 级别： Premium级； 时间：最近5年。 要提出未来3-5年的可行、新颖的研究方向。还要关注临床研究的进展（特别猪器官移植到人身上的相关研究）。结果保存在 ./reviews 文件夹里； 如果你觉得有多个不同的主题，可以写多篇综述。

---

我对器官移植领域比较感兴趣。使用 get-review-theme skill 获得研究主题。

---

请使用 Init-project skill 为本项目进行初始化： 我在这个项目里面准备写一个国自然青年的标书的demo。 我需要使用 https://github.com/huangwb8/ChineseResearchLaTeX 和 https://github.com/huangwb8/skills 相关工具。