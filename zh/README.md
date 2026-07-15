![](../measles-foresite.png)

> [!CAUTION]
> 本 README 由 GitHub Copilot 根据英文版自动生成。

[![ForeSITE 团队](https://github.com/EpiForeSITE/software/raw/e82ed88f75e0fe5c0a1a3b38c2b94509f122019c/docs/assets/foresite-software-badge.svg)](https://github.com/EpiForeSITE)

# ForeSITE 的麻疹应对与工具

亦可阅读： [🇺🇸 English](../README.md) | [🇨🇱 Español](../es/README.md) | [🇮🇳 हिंदी](../hi/README.md)

最后更新：![GitHub last commit](https://img.shields.io/github/last-commit/EpiForeSITE/measles)

自 2025 年美国爆发麻疹以来，ForeSITE（[InsightNet](https://insightnet.us/) 建模网络成员）一直与地方与州级卫生部门合作，创建工具与分析以协助公共卫生响应。我们与犹他州卫生与公共服务部（Utah DHHS）的合作尤为紧密。本仓库汇总了 ForeSITE 已开发的工具与其他资源。在文末还提供了由 InsightNet 其他成员创建的相关资源链接。

如有任何问题、希望与我们合作，或需要使用上述工具的协助，请通过 george.vegayon@utah.edu 与我们联系，或直接在本仓库提交 issue。

## ForeSITE 提供的工具与资源

1. **单校麻疹暴发模拟 Shiny 应用**：作为 [`epiworldRShiny` 包](https://cran.r-project.org/package=epiworldRShiny) 的扩展，我们开发了一个 Shiny 应用，允许用户在单一学校情境下模拟麻疹暴发。应用包含两个情景：实施隔离与不实施隔离，并在病例数与住院数方面比较结果。应用地址见[此处](https://ggv.cl/shiny/measles)。

2. **R 版单校暴发模拟**：该 Shiny 应用封装了 [`measles` 包](https://cran.r-project.org/package=measles)中的 `ModelMeaslesSchool` 模型。`epiworldR` 本身封装了 C++ 库 `epiworld`（[链接](https://github.com/UofUEpiBio/epiworld)），该库为所有模型提供核心仿真引擎。

3. **学校麻疹通知信模板**：我们与 Utah DHHS 紧密合作，创建了一个模板仓库，供其他卫生部门基于我们的单校暴发模拟结果生成定制化通知信。该模板仓库见[此处](https://github.com/EpiForeSITE/measles-school-letters)，使用 [`quarto`](https://quarto.org/) 文档生成通知信。Utah DHHS 已使用该文档为犹他州学校生成个性化通知，并向地方卫生部门提供关于潜在麻疹暴发及隔离措施影响的信息。

4. **含隔离的混合接触模型**：我们将单校模型扩展至包含多所学校（或实体），以评估社区层面的麻疹暴发影响。该模型在 R 包 `measles` 中以 [`ModelMeaslesMixing()`](https://uofuepibio.github.io/measles/reference/ModelMeaslesMixing.html) 提供，并通过接触者追踪实现隔离流程。与单校模型不同的是，单校模型会对所有未接种者进行隔离，而混合模型仅隔离被检测病例的接触者。

5. **按风险分层的隔离时长**：针对“麻疹暴露后最佳隔离时长”为何的问题，我们开发了模型 [`ModelMeaslesMixingRiskQuarantine()`](https://uofuepibio.github.io/measles/reference/ModelMeaslesMixingRiskQuarantine.html)，可根据风险级别设定不同隔离时长：高风险（与报告病例同组）、中风险（不同组但有直接接触）与低风险（不同组且无直接接触）。截至 2025 年 10 月 29 日，我们已有一份展示该模型初步结果的报告，可在[此处](https://github.com/EpiForeSITE/measles-tiered-quarantine)查阅。

6. **多群体随机分仓模型**：与混合模型类似，犹他大学 Damon Toth 博士领导的团队最近发布了 R 包 [`multigroup.vaccine`](https://cran.r-project.org/package=multigroup.vaccine)。该包的功能包括应用于犹他州-亚利桑那州边境 Short Creek 地区的实例，使用了该地区的疫苗接种覆盖率以及美国人口普查信息。类似的示例分析可在 [`measles`](https://github.com/UofUEpiBio/measles) R 包的某个 vignette 中找到。

7. **流行病学成本计算器（EPICC）**：这是一款简单的在线工具，允许用户估算麻疹暴发在公共卫生成本、住院人数和经济损失方面的下限。该工具是犹他大学团队研究成果。工具可在[此处](https://epiforesite.github.io/epicc/)使用。

8. **FIFA 2026 世界杯麻疹暴发风险仪表板**：该工具由我们与其他 InsightNet 中心及 CDC 合作设计，旨在对 2026 年世界杯美国主办城市的麻疹暴发风险提供早期估计。该仪表板使用 AI 快速构建原型，并利用了我们现有的建模工具，尤其是 `measles` 和 `epiworldR` R 包。工具可在[此处](https://epiforesite.github.io/idcup/)使用。

以上列出的所有 ABM 模型均可在 C++ 的 `epiworld` 库（[链接](https://github.com/UofUEpiBio/epiworld)）、R 包 `measles`（通过 `epiworldR` 封装 `epiworld`）以及 Python 的 `epiworldpy` 库（[链接](https://github.com/UofUEpiBio/epiworldpy)）中获得。

## InsightNet 其他成员的资源

- **epiENGAGE** 团队的学校暴发舱室模型（[链接](https://epiengage-measles.tacc.utexas.edu/)）。
- 美国疾控中心（CDC）的麻疹信息页（[链接](https://www.cdc.gov/measles/data-research/index.html)）。
- 得克萨斯州卫生与公众服务部的麻疹传播沟通工具包（[链接](https://www.dshs.texas.gov/vaccine-preventable-diseases/measles-rubeola/measles-communication-toolkit)）。
- CDC 疫情预测与分析中心的麻疹模拟器（[链接](https://cdcposit.cdc.gov/measles-simulator/)）。
