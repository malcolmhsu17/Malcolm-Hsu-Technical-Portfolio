# Malcolm Hsu Technical Portfolio

Welcome to my technical portfolio! I am a first year Master of Science in Business Analytics candidate at Brandeis University, concentrating in Artificial Intelligence. As an undergraduate at Wesleyan University I double majored in Mathematics and Economics and was also a captain on the varsity baseball team. I am extremely passionate about using time series analysis and AI/ML methods to leverage metrics and big data to provide actionable insights for companies and their clients to enhance performance and business decisions. I have advanced proficiencies in R, Python, SQL, Tableau, Stata, and Excel.


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

| Project & Link | Completion Date | Tools | Project Description | 
|---|---|---|---|
| [Forecasting Firearm Innovation: A Time Series Analysis of U.S. Patent Trends and Macroeconomic Influencers, 1820-2025](https://github.com/malcolmhsu17/Malcolm-Hsu-Technical-Portfolio/blob/main/Patent%20Project) | June 2025 - Present | R, Python, SQL | This project examines over two centuries of firearm innovation in the U.S. using patent data from the USPTO. Through time series modeling (Naive, ARIMA, ARIMAX, TAR) and count regressions (Poisson, Negative Binomial), I explore how wars, economic fluctuations, and government/military spending have influenced patterns of firearm innovation. Cross validation and model comparison identify TAR and ARIMAX models as the most effective at capturing long run and regime dependent behavior. A focused case study on safety arrangement patents (F41A17) highlights declining innovation in this area, with GDP, military expenditure, and arms imports emerging as key drivers. |
| [Trade Policy Shocks and Market Reactions: An Event Study with LLM-Derived Measures of USTR Tariff Announcements](https://github.com/malcolmhsu17/Malcolm-Hsu-Technical-Portfolio/blob/main/Semiconductor%20Industry%20&%20Tariff%20Actions) | August 2025 - Present | Python | In this project, I studied how U.S. trade policy shocks ripple through the semiconductor supply chain by measuring equity market reactions to USTR Section 301 tariff announcements—focusing on TSMC and a curated universe of semiconductor, downstream tech, energy/chemicals, and renewables firms. Technically, I built an end-to-end empirical finance + NLP pipeline: (1) assembled a corpus of USTR Section 301 documents and engineered event-level features (event date, list/type, cleaned text, direction/action labels) using automated parsing and text cleaning; (2) pulled daily price data (2010–present) via yfinance, computed returns as percent changes, and used the S&P 500 as the market benchmark; (3) implemented a standard market-model event study with a pre-event estimation window (−120 to −20) and an event window (−5 to +5) to compute abnormal returns (AR) and cumulative abnormal returns (CAR); and (4) layered in Generative AI by running Ollama 3.2 to convert unstructured policy text into structured JSON outputs—severity (0–3), surprise (0–1), direction, and rationale—then compared manual vs LLM labels and their combined use. To explain cross-firm and cross-sector variation, I estimated CAR regressions with clustered standard errors at the event-date level (to account for correlated reactions across firms to the same announcement), plus sector fixed effects in extended specifications, and I constructed a numeric “severity index” to reduce dimensionality in the policy-intensity measures. Results-wise, the consistent signal was that “relief” announcements tend to produce positive abnormal returns, while severity/surprise were weaker predictors—suggesting markets respond more to information resolution/uncertainty than to the raw “intensity” of policy text. |
| [Identifying the Relationship Between Macroeconomic Signals and the California Housing Market Surrounding Economic Downturns in the 21st Century](https://github.com/malcolmhsu17/Malcolm-Hsu-Technical-Portfolio/blob/main/California%20Housing%20Market) | January 2025 - May 2025 | R | This project analyzes how major economic downturns, the 2008 Financial Crisis and the COVID-19 Pandemic, affected California’s housing market using monthly data from Zillow from 2004 to 2024. Using housing data and U.S. macroeconomic indicators such as GDP, CPI, mortgage rates, consumer confidence, population, and unemployment, this paper utilzes advanced time series and econometric models including ARIMA, SARIMAX, TAR, VAR, and Markov Switching models, as well as linear, polynomial, Fourier, and spline regressions to capture cyclical and nonlinear dynamics. Via county level clustering, cross county VAR analysis, and rolling window cross validation, the project identifies how housing markets respond to macroeconomic shocks, revealing that inflation, mortgage rates, and unemployment are key drivers of housing price fluctuations. Overall, the results demonstrate a strong link between national economic conditions and California’s housing market performance, providing an interpretable, data driven foundation for forecasting future market trends. |
| [The Effect of Remote Work on Wage Dispersion: The Repercussions of the Pandemic on Job Industries](https://github.com/malcolmhsu17/Malcolm-Hsu-Technical-Portfolio/blob/main/Remote%20Work%20Wage%20Dispersion) | August 2024 - December 2024 | Stata | This project examines how the COVID-19 pandemic reshaped wage structures across U.S. industries through the rise of remote work. Using American Community Survey (ACS) data from IPUMS (2018–2022), the study compares income differences between remote and onsite workers, focusing on four representative sectors: finance, professional services, construction, and agriculture, to capture variation between technology and labor intensive industries. Through a series of OLS regressions, interaction models, and instrumental variable estimation, the paper measures how telework influenced wage dispersion. Results show that remote workers earned higher wages in technology intensive industries, while effects were ambiguous in labor intensive sectors. Overall, the findings reveal that remote work amplified existing wage inequalities across industries, highlighting how technological capacity and job characteristics shape the post pandemic labor market. |

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










