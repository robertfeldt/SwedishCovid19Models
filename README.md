# SwedishCovid19Models

We collect data, papers, and models for modeling/prediction in relation to COVID-19. Focus is on epidemiological modeling, typically with a statistical/stochastic flavor. We also try to track predictions (mainly point estimates) that have been done in public fora.

Our focus is on Sweden but our aim in the modeling is generality and modularity so that others can apply to their context. We also track international models that include Sweden or that can be used as comparison points for Swedish models.

Our goal is not to point out one, "best" model but to get strength in numbers, i.e. by seeing a number of different models and approaches and their predictions this can, taken together, help inform policy and decisions.

We also point to some good, external sites below that can give a general, graphical overview of the current state of the pandemic. Our focus is on models and predictions, though.

We invite everyone to contribute by building on or helping improve our models and information.

## Graphs and overviews

The current best graphical overview of the COVID-19 pandemic can, in our view, be found in the graphs and analysis from OurWorldInData so we [refer you there](https://flip.it/h.wzvd). A similar, graphical "tracker" for key data for Sweden was also recently added [here](https://c19.se/) and the more "official" one from Folkhälsomyndigheten [can be found here](https://experience.arcgis.com/experience/09f821667ce64bf7be6f9f87457ed9aa).

## Models

### Point estimates: Number of dead, final in total

Point predictions of the final number of total deaths in Sweden.

| Estimate         | Num. dead  | Date | Comment |
| ---------------- |:----------:|:----:|:--------|
| [Björkman200330](point_estimates/20200330_Bjorkman_DN_debatt.txt) | 1000 | 2020-03-30 | in near-time, for 2020 |

### EU Infected and R0 Models

| Model            | % Infected | R0 | Date |
| ---------------- |:----------:|:--:|:----:| 
| [Flaxman200330](papers/localpdfs/flaxman2020.pdf) - Sweden | 3.1% [0.85%-8.4%] | 2.64 [1.40-4.18] | 2020-03-30 |
| [Flaxman200330](papers/localpdfs/flaxman2020.pdf) - Norway | 0.41% [0.09%-1.2%] | 0.97 [0.14-2.14] | 2020-03-30 |
| [Flaxman200330](papers/localpdfs/flaxman2020.pdf) - Italy | 9.8% [3.2%-26%] | |2020-03-30 |

- [Flaxman200330](papers/localpdfs/flaxman2020.pdf) is a hierarchical Bayesian model comparing 11 European countries. They note that uncertainties are high though and that Sweden's R0 estimate might be higher since we have not ordered a lockdown; this might be a modeling artefact. The report will be updated weekly. The model is only fit on the number of reported deaths from ECDC data, no case data is used. The (Stan) [code for this model is available](https://github.com/ImperialCollegeLondon/covid19model).

### International CFR (Case Fatality Rate) Models

| Model            | COVID-19 CFR  | CI 95% | WHO CFR (at the time) | crude CFR |Date |
| ---------------- |:-------------:|:------:|:---------------------:|:---------:|:----:| 
| [Angelopoulos2020](https://arxiv.org/abs/2003.08592) - Global | 2.4% | | 3.4% |  4.4% | 2020-03-26 |
| [Hauser2020v2](https://github.com/jriou/covid_adjusted_cfr) - China | 3.0% | 2.6-3.4% | 3.4% | | 2020-03-22 |
| [Hauser2020v2](https://github.com/jriou/covid_adjusted_cfr) - Italy | 3.3% | 2.0-4.7% | 3.4% | | 2020-03-22 |

The CI column lists the confidence interval for frequentist analyses and credible interval for bayesian analysis when applicable / available. WHO CFR is their global estimate regardless of country listed above and "crude CFR" refers to the naïve estimator.

Further links and details:
- [Angelopoulos2020](https://arxiv.org/abs/2003.08592) - Better estimation techniques for CFR based on Expectation Maximization. Recommends that crude CFR shouldn't be used as it is unreliable.
  * 2020-03-19: Estimates a global corrected CFR of 2.4% for COVID-19, in contrast to WHO estimate of 3.4% and data indicating 4.4%.
  * [Code is available](https://github.com/aangelopoulos/cfr-covid-19) for applying this method.
- [Hauser2020v2](https://github.com/jriou/covid_adjusted_cfr), a Bayesian CFR model from Hauser et al at University of Bern. ([Latest PDF](https://github.com/jriou/covid_adjusted_cfr/blob/master/manuscript/manuscript_v2.pdf))
  * This underestimates the total deaths since it predicts deaths among people already infected during the period of interest, i.e. it does not model people that will be infected after the period for which you have data. This is since the goal is to get a better estimate of Case Fatality Rate, not to predict cases or deaths.

## Data

We collect raw as well as cleaned (pre-processed, filtered, and curated) data for people that want to build their own models.

### Raw data

### Cleaned Swedish data

[ECDC data](https://www.ecdc.europa.eu/en/publications-data/download-todays-data-geographic-distribution-covid-19-cases-worldwide) for Sweden:
- incidence data, all cases: [all_swedish_cases_incidence_20200328_1036.csv](data/clean/sweden/all_swedish_cases_incidence_20200328_1036.csv)
- incidence data, starting from 3 days before first case: [start_minus3_swedish_cases_incidence_20200328_1036.csv](data/clean/sweden/start_minus3_swedish_cases_incidence_20200328_1036.csv)

[Folkhälsomyndigheten](https://experience.arcgis.com/experience/09f821667ce64bf7be6f9f87457ed9aa):
- age distributed: [age_distributions_cases_and_deaths/20200328_1634.csv](data/raw/Folkhalsomyndigheten/age_distributions_cases_and_deaths/20200328_1634.csv)

## Papers

We collect relevant research papers and pre-prints on modeling in relation to COVID-19 and other, relevant epidemics. [See this file for links to all the papers](papers/Covid19ModelingPapers.md), below we just list the ones for Sweden:

- TBD
