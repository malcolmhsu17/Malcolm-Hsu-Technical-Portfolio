# Malcolm Hsu Technical Portfolio

Welcome to my technical project portfolio! I am a first year Master of Science in Business Analytics candidate at Brandeis University, concentrating in Artificial Intelligence and graduating in May 2026. As an undergraduate at Wesleyan University I double majored in Mathematics and Economics and was also a captain on the varsity baseball team. I am extremely passionate about using time series analysis and AI/ML methods to leverage metrics and big data to provide actionable insights for companies and their clients to enhance performance and business decisions. I have advanced proficiencies in R, Python, SQL, Tableau, Stata, and Excel. More specifically, I have extensive experience with and am passionate about LLM training and fine tuning, generative AI models, RAG development, and big data management.


## Contact Information:
Email: malcolmhsu@brandeis.edu
Cell: (408)839-7078
LinkedIn: https://www.linkedin.com/in/malcolm-hsu/

## Table of Contents
- [Research Projects](#Research)
- [Baseball Analytics](#Baseball)
- [R](#R)
- [SQL](#sql)
- [Python](#python)
- [Tableau](#tableau)

# Research

| Project & Link | Completion Date | Tools | Project Description | Skills |
|---|---|---|---|---|
| [Forecasting Firearm Innovation: A Time Series Analysis of U.S. Patent Trends and Macroeconomic Influencers, 1820-2025](https://github.com/malcolmhsu17/Malcolm-Hsu-Technical-Portfolio/blob/main/Patent%20Project) | June 2025 - Present | R, Python, SQL | In this project, I built an end-to-end analytics pipeline to study long-run innovation patterns in firearm-related patents, with a focused sub-analysis on F41A17 (“safety arrangements”). Using patent classification data and publication dates, I engineered monthly patent count time series for multiple F41 subclasses and connected these outcomes to macro and conflict-related drivers (e.g., government spending, GDP, military expenditure, and arms trade flows). The goal was to quantify how innovation in specific firearm technology areas evolves over time, identify structural changes in innovation regimes, and evaluate which modeling approaches are most appropriate for forecasting and inference on patent counts. Technically, the workflow emphasized reproducible data engineering and rigorous time-series diagnostics. I cleaned and standardized raw patent datasets (joins/keys, date parsing, missingness handling, and time aggregation), then validated time-series assumptions using stationarity testing (ADF and KPSS) and transformations (differencing, log1p, interpolation when needed). I implemented a modeling stack that included baseline benchmarks, ARIMA/FARIMA, and Threshold AutoRegressive (TAR / SETAR) models, using information criteria and out-of-sample forecast construction to compare performance—particularly in the F41A17 safety series where TAR materially outperformed ARIMA on fit.Beyond classical forecasting, I extended the analysis to nonlinear dynamics and regime behavior using Markov regime-switching models (estimating low- vs high-innovation states and transition behavior) and complemented this with spectral analysis (periodograms on detrended log-transformed series) to detect cyclical structure in innovation intensity. For inference on drivers of patent counts, I estimated a set of regression specifications ranging from linear/polynomial/spline time trends to count models (Poisson and Negative Binomial), including interaction structures (e.g., war-period effects) and fixed-effects/count-panel tools where appropriate. The final deliverable is a modular research codebase and published academic paper that cleanly separates data construction, exploratory diagnostics, model estimation, and publication-ready visual outputs. | (1) R data engineering: dplyr, tidyr, readr/readxl, robust date handling (lubridate), reproducible joins and aggregation to monthly series; (2) Time-series econometrics: ADF/KPSS diagnostics, differencing/log transforms, ARIMA/FARIMA (forecast, TSA), TAR/SETAR (tsDyn); (3) Regime & frequency-domain modeling: Markov switching (MSwM), spectral analysis / periodograms (spec.pgram); (4) Count-data modeling: Poisson + Negative Binomial (including applied modeling choices for overdispersion; (5) MASS, fixest where used); External data integration: arms trade data pulls via comtradr and integration with macro/conflict covariates; (6) Communication & outputs: high-signal plots (ggplot2) and structured tables for writeups/papers |
| [Trade Policy Shocks and Market Reactions: An Event Study with LLM-Derived Measures of USTR Tariff Announcements](https://github.com/malcolmhsu17/Malcolm-Hsu-Technical-Portfolio/blob/main/Semiconductor%20Industry%20&%20Tariff%20Actions) | August 2025 - Present | Python | In this project, I studied how U.S. trade policy shocks ripple through the semiconductor supply chain by measuring equity market reactions to USTR Section 301 tariff announcements—focusing on TSMC and a curated universe of semiconductor, downstream tech, energy/chemicals, and renewables firms. Technically, I built an end-to-end empirical finance + NLP pipeline: (1) assembled a corpus of USTR Section 301 documents and engineered event-level features (event date, list/type, cleaned text, direction/action labels) using automated parsing and text cleaning; (2) pulled daily price data (2010–present) via yfinance, computed returns as percent changes, and used the S&P 500 as the market benchmark; (3) implemented a standard market-model event study with a pre-event estimation window (−120 to −20) and an event window (−5 to +5) to compute abnormal returns (AR) and cumulative abnormal returns (CAR); and (4) layered in Generative AI by running Ollama 3.2 to convert unstructured policy text into structured JSON outputs—severity (0–3), surprise (0–1), direction, and rationale—then compared manual vs LLM labels and their combined use. To explain cross-firm and cross-sector variation, I estimated CAR regressions with clustered standard errors at the event-date level (to account for correlated reactions across firms to the same announcement), plus sector fixed effects in extended specifications, and I constructed a numeric “severity index” to reduce dimensionality in the policy-intensity measures. Results-wise, the consistent signal was that “relief” announcements tend to produce positive abnormal returns, while severity/surprise were weaker predictors—suggesting markets respond more to information resolution/uncertainty than to the raw “intensity” of policy text. | (1) Event study design (market model): Built an event-study framework around USTR tariff announcements with a clean separation between the estimation window (−120 to −20 days) and event window (−5 to +5 days) to estimate expected returns and isolate abnormal price responses. (2) Abnormal returns + CAR construction: Computed abnormal returns (AR) at the firm-day level and aggregated them into cumulative abnormal returns (CAR) over event windows. (3) Market + firm return data pipeline: Pulled firm-level equity data via yfinance, computed returns as percent changes, and used the S&P 500 as the market benchmark for expected returns. (4) Policy text engineering + manual labeling: Structured a policy-text corpus into analysis-ready features (document type, action type, direction), and built manual severity scoring plus a severity index (categorical → numeric) for regression use. (5) LLM-driven feature extraction (Ollama 3.2): Used prompt-engineering to force strictly formatted JSON outputs from policy text—severity (0–3), surprise (0–1), direction, rationale—then integrated those outputs as regression covariates. (6) Econometric modeling of CARs: Estimated multiple linear CAR regressions, including specifications using severity indices and direction, and models with sector fixed effects to control for unobserved heterogeneity. (7) Robust inference for event clustering: Applied cluster-robust standard errors at the event-date level to address cross-firm correlation in returns around the same announcements. |
| [Identifying the Relationship Between Macroeconomic Signals and the California Housing Market Surrounding Economic Downturns in the 21st Century](https://github.com/malcolmhsu17/Malcolm-Hsu-Technical-Portfolio/blob/main/California%20Housing%20Market) | January 2025 - May 2025 | R | This project analyzes how major economic downturns, the 2008 Financial Crisis and the COVID-19 Pandemic, affected California’s housing market using monthly data from Zillow from 2004 to 2024. Using housing data and U.S. macroeconomic indicators such as GDP, CPI, mortgage rates, consumer confidence, population, and unemployment, this paper utilzes advanced time series and econometric models including ARIMA, SARIMAX, TAR, VAR, and Markov Switching models, as well as linear, polynomial, Fourier, and spline regressions to capture cyclical and nonlinear dynamics. Via county level clustering, cross county VAR analysis, and rolling window cross validation, the project identifies how housing markets respond to macroeconomic shocks, revealing that inflation, mortgage rates, and unemployment are key drivers of housing price fluctuations. Overall, the results demonstrate a strong link between national economic conditions and California’s housing market performance, providing an interpretable, data driven foundation for forecasting future market trends. | Skills |
| [The Effect of Remote Work on Wage Dispersion: The Repercussions of the Pandemic on Job Industries](https://github.com/malcolmhsu17/Malcolm-Hsu-Technical-Portfolio/blob/main/Remote%20Work%20Wage%20Dispersion) | August 2024 - December 2024 | Stata | This project examines how the COVID-19 pandemic reshaped wage structures across U.S. industries through the rise of remote work. Using American Community Survey (ACS) data from IPUMS (2018–2022), the study compares income differences between remote and onsite workers, focusing on four representative sectors: finance, professional services, construction, and agriculture, to capture variation between technology and labor intensive industries. Through a series of OLS regressions, interaction models, and instrumental variable estimation, the paper measures how telework influenced wage dispersion. Results show that remote workers earned higher wages in technology intensive industries, while effects were ambiguous in labor intensive sectors. Overall, the findings reveal that remote work amplified existing wage inequalities across industries, highlighting how technological capacity and job characteristics shape the post pandemic labor market. | Skills |

***

# Baseball

| Project & Link | Completion Date | Tools | Project Description | 
|---|---|---|---|
| [MLB Statistics Research Paper](https://github.com/malcolmhsu17/Malcolm-Hsu-Technical-Portfolio/blob/main/MLB%20Statistics%20Paper) | August 2023 - December 2023 | Stata | This paper investigates how Major League Baseball players’ performance metrics and career accolades affect their salaries, focusing on whether pay accurately reflects on field success. Using data from the 2023 MLB season, the study combines player statistics from Baseball Reference, including batting average (AVG), on-base plus slugging percentage (OPS), All-Star selections, MVP awards, and years of experience, with salary data from USA Today. A multivariate OLS regression model estimates the relationship between salary and these performance indicators, finding that OPS, All-Star selections, MVP awards, and years played are all positively and statistically significant determinants of pay, while batting average shows a negative relationship. Results suggest that while performance metrics like OPS are strong predictors of compensation, career longevity plays equally substantial roles, underscoring how reputation and statistical achievement in determining MLB player salaries. |
| [Pitch Classifications Project](https://github.com/malcolmhsu17/Malcolm-Hsu-Technical-Portfolio/blob/main/Kinetic%20Performance%20Institute/Pitch%20Classifications) | Dec 2023 - May 2025 | R | This project builds an framework for identifying, categorizing, and evaluating pitch types and characteristics using Trackman pitch data. Using R, the analysis processes large datasets of pitch metrics: velocity, spin rate, horizontal/vertical movement, release metrics, and pitch outcomes, to classify pitches into distinct clusters. The project computes percentile summaries for each pitch type, visualizes pitch variation, and generates insights into how pitchers’ repertoires align with professional benchmarks. |
| [Visualizations Project](https://github.com/malcolmhsu17/Malcolm-Hsu-Technical-Portfolio/blob/main/Kinetic%20Performance%20Institute/Visualizations) | Dec 2023 - May 2025 | R | Description |
| [Percentiles Project](https://github.com/malcolmhsu17/Malcolm-Hsu-Technical-Portfolio/blob/main/Kinetic%20Performance%20Institute/Percentiles%20Project) | Dec 2023 - May 2025 | R | This project constructs normative benchmarks for players by aggregating and analyzing multiple KPIs across platforms such as ArmCare, Trackman, Blast, Hawkins Jump, Proteus, and HitTrax. Using R for data integration and analysis, the project cleans and merges datasets for pitchers and hitters, calculates individualized percentile rankings across strength, velocity, and power metrics, and visualizes player performance distributions relative to population averages. These percentiles enable comparative profiling across multiple dimensions, and offers coaches a quantitative foundation for individualized player development and training optimization. |

***

# R

| Project & Link | Completion Date | Tools | Project Description | 
|---|---|---|---|
| [Project](link here) | Dec 2023 - May 2025 | R | Description |

***

# SQL

| Project & Link | Completion Date | Tools | Project Description | 
|---|---|---|---|
| [Project](link here) | Date | Tools | Description |

***

# Python

| Project & Link | Completion Date | Tools | Project Description | 
|---|---|---|---|
| [Project](link here) | Date | Tools | Description |

***

# Tableau

| Project & Link | Completion Date | Tools | Project Description | Dashboard Link |
|---|---|---|---|---|
| [Project](link here) | Date | Tools | Description | Dashboard link |


***










