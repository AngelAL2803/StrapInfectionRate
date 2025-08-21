<h1>Staphylocous Infection Risk in Burn Victims</h1>

<h2>Description</h2>
This was a <b>group final project</b> for a survival analysis course, conducted by <b>Matthew Aydin, Angel Alcantara, and Adam Sztonyk</b>. The project applies <b>survival analysis techniques</b> to investigate the risk of <b>Staphylococcus aureus infection</b> in burn patients, using the <b>burn dataset</b> from the `KMsurv` package.

The dataset contains clinical records of 154 burn patients, with infection time (`T3`), excision time (`T1`), and multiple demographic and clinical covariates. We modeled infection risk using <b>Cox proportional hazards models</b>, incorporating <b>time-varying covariates</b> to account for excision events.

The primary scientific question was: How does body cleansing treatment (vs. routine bathing) affect the hazard of Staphylococcus aureus infection, and how does this risk change depending on whether excision is performed?
<br />


<h2>Languages and Utilities Used</h2>

- <b>R (R Markdown for reporting & visualization)</b>
- <b>RStudio</b>
- <b>Git & GitHub for version control</b>
- <b>KMsurv</b>, <b>survival</b>, <b>survminer</b> (R packages)

<h2>Dataset</h2>

- <b>Source:</b> Burn dataset (`KMsurv` R package, Ichida study)
- <b>Sample Size:</b> 154 burn patients
- <b>Variables:</b>
  - <b>Outcome:</b> Time to Staphylococcus aureus infection (`T3`), indicator (`D3`)
  - <b>Time-varying covariate:</b> Excision event (`T1`, `D1`)
  - <b>Predictors:</b> Treatment type, gender, race, % burn area, burn site indicators, burn type

<h2>Methods</h2>

- <b>Exploratory Data Analysis</b>
  - Kaplan-Meier survival curves stratified by treatment type
  - Log-rank tests comparing infection risk across subgroups
- <b>Cox Proportional Hazards Models</b>
  - Baseline Cox model with treatment and covariates
  - Extended Cox model with excision as a <b>time-varying covariate</b>
- <b>Model Diagnostics</b>
  - Schoenfeld residuals for proportional hazards assumption
  - Martingale & deviance residuals for model fit
- <b>Visualization</b>
  - Survival and hazard curves
  - Forest plots of hazard ratios
 
<h2>Results</h2>

- <b>Treatment Effect:</b> Body cleansing treatment reduced the hazard of Staphylococcus aureus infection compared to routine bathing.
- <b>Excision Effect:</b> Modeling excision as a time-varying covariate improved fit; excision significantly modified infection risk.
- <b>Other Risk Factors:</b> Larger % burn area and certain burn sites (e.g., respiratory tract) were associated with higher infection hazards.

<h2>Results Visualization</h2>

- <b>Kaplan-Meier Curves:</b> Plotted survival probabilities for infection across treatment groups (body cleansing vs. routine bathing). The curves diverged, showing a lower cumulative hazard of infection for patients receiving cleansing treatment.
- <b>Time-Varying Excision Analysis:</b> Visualized how the hazard of infection changed before and after excision surgery. The plots showed that excision significantly altered infection risk, validating the importance of modeling it as a time-varying covariate.
- <b>Hazard Ratio Forest Plot:</b> Displayed estimated hazard ratios (HRs) with 95% confidence intervals for all covariates. This highlighted which patient characteristics (e.g., % burn area, respiratory tract involvement) had the strongest association with infection hazard.
- <b>Diagnostic Plots:</b>
  - <b>Schoenfeld residual plots</b> confirmed proportional hazards held for most covariates.
  - <b>Martingale residual plots</b> checked functional form assumptions for continuous variables like % burn area.
  - <b>Deviance residual plots</b> helped detect influential observations or outliers.

Together, these visualizations showed that (1) treatment and excision timing are clinically meaningful predictors of infection, (2) certain patient factors elevate infection risk, and (3) the final extended Cox model adequately met key assumptions.

<h2>My Role & Contributions (Angel Alcantara)</h2>

- <b>Data prep & restructuring:</b> Cleaned variables, created person-period structure to encode <b>time-varying excision</b>; validated event/censoring logic.

- <b>Modeling:</b> Implemented Cox PH baseline and extended models; tuned covariate sets; compared nested models via likelihood-ratio tests and AIC.

- <b>Diagnostics:</b> Led proportional-hazards assessment (Schoenfeld tests/plots) and residual analyses; documented interpretation and mitigations.

- <b>Visualization:</b> Built KM plots, HR forest plots, and diagnostic figures with <code>survminer</code>/<code>ggplot2</code> for publication-quality output.

- <b>Reproducibility:</b> Assembled the R Markdown pipeline, set seeds, organized figure exports, and structured the final report.

- <b>Writing:</b> Drafted Methods & Results sections (model specification, diagnostics, visual interpretations).

<h2>Project Structure</h2>

- <b>StrapInfection.Rmd</b> → R Markdown analysis (full code & methods)
- <b>StrapInfection.pdf</b> → final report with results and figures (pdf)
- <b>StrapInfection.html</b> → final report with results and figures (html)

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
