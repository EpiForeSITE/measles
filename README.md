![](measles-foresite.png)

[![ForeSITE Group](https://github.com/EpiForeSITE/software/raw/e82ed88f75e0fe5c0a1a3b38c2b94509f122019c/docs/assets/foresite-software-badge.svg)](https://github.com/EpiForeSITE)

# Measles response and tools by ForeSITE

Also available in: [🇨🇱 Español](es/README.md) | [🇨🇳 中文](zh/README.md) | [🇮🇳 हिंदी](hi/README.md)

Last update: ![GitHub last commit](https://img.shields.io/github/last-commit/EpiForeSITE/measles)


Since the beginning of the 2025 Measles outbreaks in the United States, ForeSITE (a member of the [InsightNet](https://insightnet.us/) modeling network) has been collaborating with local and state health departments creating tools and analysis assisting the public health response. One of the closest collaborations has been with the Utah Department of Health and Human Services (Utah DHHS). This repository contains a list of the tools and other resources that ForeSITE has developed. At the end of this file you will also find links to other resources created by other InsightNet members.

If you have any questions or would like to collaborate with us (or need some help using any of these tools), please contact us at george.vegayon@utah.edu or just open an issue in this repository.

## Tools and Resources by ForeSITE

1. **Single school outbreak simulator shiny app**: As an extension of the [`epiworldRShiny` package](https://cran.r-project.org/package=epiworldRShiny), we developed a shiny app that allows users to simulate measles outbreaks in a single school setting. The app runs two scenarios: one with quarantine and another without quarantine, and compares the results in terms of number of cases and hospitalizations. The app is available [here](https://ggv.cl/shiny/measles).

2. **Single school outbreak simulator in R**: The shiny app is a wrapper of the `ModelMeaslesSchool` model in the [`measles` package](https://cran.r-project.org/package=measles). The `epiworldR` package itself (which includes the measles models' headers) is a wrapper of the `epiworld` C++ library ([link](https://github.com/UofUEpiBio/epiworld)), which provides the core simulation engine for all its models.

3. **Measles school letters**: In a close collaboration with Utah DHHS, we created a template repository that other health departments can use to create customized letters with scenario results from our single school outbreak simulator. The template repository, which is available [here](https://github.com/EpiForeSITE/measles-school-letters), uses a [`quarto`](https://quarto.org/) document to generate the letters. Utah DHHS used this document to create customized letters for schools in Utah and provide information about potential measles outbreaks and the impact of quarantine measures to local health departments.

4. **Mixing model with Quarantine**: We extended the single school model to include multiple schools (or entities) to assess the impact of measles outbreaks at the community level. The model is available in the `measles` R package as [`ModelMeaslesMixing()`](https://uofuepibio.github.io/measles/reference/ModelMeaslesMixing.html) and features a quarantine process using contact tracing. The main difference from the single school model is that in the single school model all unvaccinated agents are quarantined, whereas in the mixing model only contacts of detected cases are quarantined.

5. **Measles risk quarantine level**: Following the question regarding the optimal quarantine length for measles exposure, we developed a model, [`ModelMeaslesMixingRiskQuarantine()`](https://uofuepibio.github.io/measles/reference/ModelMeaslesMixingRiskQuarantine.html), that allows specifying varying quarantine lengths based on risk levels: high risk (same group as the reported case), medium risk (different group, but in direct contact), and low risk (different group, no direct contact). As of October 29, 2025, we have a report showing preliminary results from this model, which can be found [here](https://github.com/EpiForeSITE/measles-tiered-quarantine).

6. **Stochastic Compartmental Models with Multiple Groups**: Similar to the mixing model, a team led by Dr. Damon Toth from University of Utah recently released the R package [`multigroup.vaccine`](https://cran.r-project.org/package=multigroup.vaccine). Among its features, the authors created examples applied to the Short Creek in the Utah-Arizona border, using vaccination coverage from the region, as well as US Census information. A similar example analysis can be found in one of the vignettes of the [`measles`](https://github.com/UofUEpiBio/measles) R package.

7. **Epidemiologic Cost Calculator (EPICC)**: A simple online tool that allows users to estimate the lower bound of measles outbreaks in terms of public health costs, hospitalizations, and economic losses. This tool is the result of research by our team at the University of Utah. The tool is available [here](https://epiforesite.github.io/epicc/).

8. **FIFA 2026 World Cup Measles Outbreak Risk Dashboard**: This tool was designed in collaboration with other InsightNet Centers and the CDC to provide an early risk estimate of measles outbreaks in U.S. host cities for the 2026 World Cup. The dashboard was rapidly prototyped using AI and leverages our existing modeling tools, particularly the `measles` and `epiworldR` R packages. The tool is available [here](https://epiforesite.github.io/idcup/).

All the ABM models listed here are available in C++ in the `epiworld` library ([link](https://github.com/UofUEpiBio/epiworld)), the `measles` R package (Which wraps `epiworld` via `epiworldR`), as well as Python in the `epiworldpy` library ([link](https://github.com/UofUEpiBio/epiworldpy)).

## Other Resources by InsightNet Members

- Compartmental Model for School outbreaks by the **epiENGAGE** group ([link](https://epiengage-measles.tacc.utexas.edu/)).
- CDC's information sheet on Measles ([link](https://www.cdc.gov/measles/data-research/index.html)).
- Texas Department of Health and Human Services' Measles Communication Kit ([link](https://www.dshs.texas.gov/vaccine-preventable-diseases/measles-rubeola/measles-communication-toolkit)).
- CDC's Center for Forecasting and Outbreak Analytics' Measles simulator ([link](https://cdcposit.cdc.gov/measles-simulator/)).
