# The Price of a Meal: Exploring Grocery Affordability Across Canada Over the Past Decade
Madiha Waqar
2026-11-09

- [1: Project Overview](#1-project-overview)
- [2: Data Sources](#2-data-sources)
  - [2.1 Summary of sources](#21-summary-of-sources)
  - [2.2.1: Monthly Average Retail Prices for Selected Products:
    Food](#221-monthly-average-retail-prices-for-selected-products-food)
  - [2.2.2 Historical Minimum Wage Rates in
    Canada](#222-historical-minimum-wage-rates-in-canada)
  - [2.3: Investigated and rejected
    sources](#23-investigated-and-rejected-sources)
  - [2.4: What I could not find](#24-what-i-could-not-find)
- [3: Licensing and permissions](#3-licensing-and-permissions)
  - [3.1: Licence by source](#31-licence-by-source)
  - [3.3: Downstream permissions](#33-downstream-permissions)
- [4: Consent and identifiability](#4-consent-and-identifiability)
- [5: Exclusions and harms](#5-exclusions-and-harms)
  - [5.1: Excluded data from the
    audit](#51-excluded-data-from-the-audit)
  - [5.2: Who could be harmed](#52-who-could-be-harmed)
  - [5.3: Unreleased working data](#53-unreleased-working-data)
- [6: Data Stewardship](#6-data-stewardship)
- [7: Use of AI](#7-use-of-ai)
- [8: Session information](#8-session-information)

<!--  another version of markdown elements, this works for html-style documents
&#10;[FP Part 2: HOW TO USE THIS TEMPLATE FOR YOUR SUBMISSION
&#10;Replace every bracketed prompt with your own writing (remove the brackets themselves, they're part of the placeholder here), and delete the prompt. 
&#10;Delete any sections that are not relevant for project, but note in commit message notes (not commit titles!) why you chose to delete them. That way I know that you've been thinking through what will be relevant as you begin the coding portion of this project.
&#10;Render, commit and push the markdown AND the .Rmd to your final project folder. 
&#10;This document will live in your final project folder in your repository alongside the AI-LOG.md, your code, and your raw data. Remember to commit it as you work on it, so that it doesn't get mixed up in your class or assignment commit messages.]
-->

# 1: Project Overview

With grocery prices continuing to rise across Canada and the world
affording basic necessities has become an increasing challenge for many
households. According to Statistics Canada, approximately **9.8 million
Canadians (24% of the population)** experienced some form of food
insecurity in 2024. In this project, I will analyze grocery prices and
minimum wages across all 10 Canadian provinces over the past decade
(2016–2026) to estimate how many hours a person earning minimum wage
would need to work to be able to afford a basic basket of groceries. I
will be focusing on how affordability has changed since the COVID 19 and
whether minimum wages have kept up with the rising cost of food.

------------------------------------------------------------------------

# 2: Data Sources

## 2.1 Summary of sources

For this project, I identified two main data sources that will help
me investigate grocery affordability across Canada. The first is
Statistics Canada’s monthly average retail food prices dataset, which
provides grocery price information across provinces. The second is the
Government of Canada’s historical minimum wage dataset, which provides
minimum hourly wage rates across provinces over time. I will combine
these datasets to compare the cost of basic groceries with minimum
wages and calculate how much time someone earning minimum wage would
need to work to afford them over the years. I will also look at how this
has changed since COVID19.

| Source | Producer | Format | Coverage | Using |
|:---|:---|:---|:---|:---|
| Monthly Average Retail Prices for Selected Products: Food | Statistics Canada | CSV | Canada; past decade data | Yes |
| Historical Minimum Wage Rates in Canada | Employment and Social Development Canada | CSV | Canada in past decade | Yes |

## 2.2.1: Monthly Average Retail Prices for Selected Products: Food

Source:https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=1810024502

**Producer and authority.** This dataset is published by Statistics
Canada, Canada’s national statistical agency. Statistics Canada collects
and publishes economic and social data to help Canadians understand
changes in the country’s economy and population. The dataset is part of
its consumer price and food price stats.

**Original Dataset Purpose.** The original purpose of this dataset was
to provide information about average prices for commonly purchased food
products across Canada. It allows people to examine food prices across
different provinces and time. Although it wasn’t specifically created to
measure affordability for minimum-wage workers it provides the grocery
price information i needed for my project.

**Collection method.** According to Statistics Canada’s documentation,
average retail food prices are calculated using transaction data
obtained directly from Canadian grocery retailers. This information
comes from retailers’ systems and includes details about products,
quantities sold, and transaction prices.

**Coverage and resolution.** The dataset covers Canada, individual
provinces and territories, and selected population centres. It is
updated monthly and reports average retail prices for different food
products in Canadian dollars. For my project, I will focus on the ten
Canadian provinces and investigate the historical data available for the
past decade (2016–2026). I will use the monthly prices to calculate
annual averages where appropriate.

**Licence.** Open Government Licence – Canada. The dataset is available
for public use, subject to the terms of the licence

**Access.** I accessed the dataset through the Statistics Canada website
using Table 18-10-0245-02. The data can be downloaded in CSV format
directly from the website. I accessed the source on November 5th 2026.

**Known problems.** One limitation is that the products and their
categories may change over time, which can make direct price comparisons
difficult. Statistics Canada also notes that the composition of product
categories can change because of differences in consumer preferences,
product availability, quality, and quantity. In addition, the retailer
data coverage was expanded in January 2024, which may affect comparisons
between earlier and later years. Some products may also have missing
prices for certain provinces or months.

    Rows: 115
    Columns: 86
    $ Products         <chr> NA, "Beef stewing cuts, per kilogram 5", "Beef stripl…
    $ `September 2019` <chr> "Dollars", "13.63", "18.39", "15.60", "19.17", "9.30"…
    $ `October 2019`   <dbl> NA, 12.69, 28.89, 14.77, 19.67, 9.21, 9.33, 7.93, 4.6…
    $ `November 2019`  <dbl> NA, 14.50, 21.22, 18.15, 23.37, 10.37, 7.98, 9.68, 7.…
    $ `December 2019`  <dbl> NA, 14.04, 20.27, 16.57, 20.90, 10.41, 9.23, 8.99, 9.…
    $ `January 2020`   <dbl> NA, 14.13, 25.10, 15.35, 25.55, 10.21, 9.31, 9.95, 8.…
    $ `February 2020`  <dbl> NA, 13.86, 19.21, 15.86, 24.82, 10.11, 9.44, 9.79, 4.…
    $ `March 2020`     <dbl> NA, 15.20, 27.62, 16.72, 25.51, 10.85, 9.77, 9.52, 8.…
    $ `April 2020`     <dbl> NA, 13.98, 18.87, 18.32, 23.70, 10.93, 9.18, 11.00, 8…
    $ `May 2020`       <dbl> NA, 17.49, 30.42, 24.11, 22.01, 11.09, 10.97, 9.16, 5…
    $ `June 2020`      <dbl> NA, 19.54, 32.82, 20.38, 27.75, 11.22, 11.91, 11.71, …
    $ `July 2020`      <dbl> NA, 17.40, 29.93, 16.99, 26.61, 10.20, 9.36, 10.71, 5…
    $ `August 2020`    <dbl> NA, 16.72, 27.16, 16.07, 27.40, 8.92, 10.63, 9.53, 4.…
    $ `September 2020` <dbl> NA, 15.36, 23.52, 19.68, 18.28, 9.21, 9.44, 10.84, 4.…
    $ `October 2020`   <dbl> NA, 14.42, 26.71, 18.09, 20.05, 9.46, 8.63, 10.94, 4.…
    $ `November 2020`  <dbl> NA, 15.49, 22.91, 18.36, 24.95, 10.83, 9.11, 10.04, 5…
    $ `December 2020`  <dbl> NA, 13.88, 20.29, 14.79, 25.56, 10.20, 8.97, 10.72, 6…
    $ `January 2021`   <dbl> NA, 15.38, 25.90, 17.69, 24.73, 9.96, 9.24, 9.89, 7.1…
    $ `February 2021`  <dbl> NA, 14.98, 21.84, 15.68, 23.09, 9.95, 9.47, 7.83, 4.8…
    $ `March 2021`     <dbl> NA, 15.09, 24.43, 16.35, 23.91, 9.85, 8.67, 9.49, 7.4…
    $ `April 2021`     <dbl> NA, 15.36, 23.55, 16.15, 26.91, 9.90, 9.48, 10.09, 6.…
    $ `May 2021`       <dbl> NA, 15.91, 23.13, 15.56, 28.93, 9.46, 9.49, 10.76, 6.…
    $ `June 2021`      <dbl> NA, 16.57, 27.34, 16.60, 25.42, 9.66, 10.72, 12.35, 5…
    $ `July 2021`      <dbl> NA, 16.45, 29.43, 17.49, 26.43, 9.63, 9.94, 11.62, 5.…
    $ `August 2021`    <dbl> NA, 16.86, 27.79, 16.46, 25.17, 10.10, 9.61, 13.01, 5…
    $ `September 2021` <dbl> NA, 15.78, 26.94, 17.04, 31.84, 10.56, 10.00, 10.84, …
    $ `October 2021`   <dbl> NA, 16.79, 25.01, 19.49, 23.84, 10.30, 10.63, 11.65, …
    $ `November 2021`  <dbl> NA, 16.99, 25.49, 21.11, 30.47, 11.98, 10.53, 10.54, …
    $ `December 2021`  <dbl> NA, 17.61, 23.54, 17.48, 25.10, 10.56, 9.66, 11.93, 5…
    $ `January 2022`   <dbl> NA, 17.00, 25.32, 21.59, 30.03, 11.00, 9.47, 10.47, 7…
    $ `February 2022`  <dbl> NA, 16.22, 27.17, 21.09, 32.71, 10.47, 9.20, 10.23, 7…
    $ `March 2022`     <dbl> NA, 17.37, 32.31, 21.56, 31.27, 10.28, 9.26, 11.21, 6…
    $ `April 2022`     <dbl> NA, 18.59, 25.83, 23.10, 29.33, 10.56, 10.52, 11.46, …
    $ `May 2022`       <dbl> NA, 18.78, 26.42, 22.24, 23.87, 10.55, 9.96, 12.28, 7…
    $ `June 2022`      <dbl> NA, 18.57, 29.38, 17.71, 28.87, 10.32, 9.94, 12.13, 7…
    $ `July 2022`      <dbl> NA, 18.58, 23.84, 22.39, 25.01, 10.77, 9.86, 12.72, 6…
    $ `August 2022`    <dbl> NA, 18.19, 22.42, 17.63, 30.36, 10.70, 9.30, 11.91, 6…
    $ `September 2022` <dbl> NA, 15.54, 24.72, 24.53, 28.75, 11.81, 9.09, 11.07, 6…
    $ `October 2022`   <dbl> NA, 16.65, 23.55, 16.59, 28.26, 10.03, 8.72, 10.99, 8…
    $ `November 2022`  <dbl> NA, 19.43, 28.58, 17.48, 27.99, 11.02, 9.27, 9.62, 7.…
    $ `December 2022`  <dbl> NA, 19.56, 17.96, 17.20, 24.83, 11.40, 8.45, 10.38, 6…
    $ `January 2023`   <dbl> NA, 17.21, 25.57, 18.67, 28.22, 10.78, 9.88, 9.38, 5.…
    $ `February 2023`  <dbl> NA, 15.60, 22.61, 18.58, 32.16, 10.29, 8.11, 10.24, 6…
    $ `March 2023`     <dbl> NA, 17.74, 26.09, 23.87, 30.14, 10.70, 8.54, 10.19, 8…
    $ `April 2023`     <dbl> NA, 19.82, 25.82, 17.33, 25.06, 11.04, 10.47, 9.79, 7…
    $ `May 2023`       <dbl> NA, 19.07, 32.05, 18.05, 25.95, 11.25, 8.55, 11.05, 8…
    $ `June 2023`      <dbl> NA, 19.90, 28.43, 19.02, 28.01, 12.38, 10.31, 8.97, 8…
    $ `July 2023`      <dbl> NA, 19.47, 35.43, 20.31, 27.66, 11.06, 10.72, 9.36, 6…
    $ `August 2023`    <dbl> NA, 20.45, 25.49, 25.11, 31.86, 10.98, 10.12, 10.14, …
    $ `September 2023` <dbl> NA, 17.80, 28.07, 27.47, 27.99, 12.67, 9.29, 9.87, 6.…
    $ `October 2023`   <dbl> NA, 16.28, 26.35, 17.10, 25.43, 11.26, 9.04, 11.03, 1…
    $ `November 2023`  <dbl> NA, 20.01, 30.28, 20.07, 29.43, 11.92, 9.90, 9.15, 8.…
    $ `December 2023`  <dbl> NA, 20.25, 22.66, 26.84, 27.55, 12.18, 9.46, 9.71, 6.…
    $ `January 2024`   <dbl> NA, 18.64, 29.46, 18.44, 33.11, 11.72, 10.77, 9.16, 6…
    $ `February 2024`  <dbl> NA, 18.14, 27.65, 24.64, 34.96, 11.63, 9.01, 9.57, 9.…
    $ `March 2024`     <dbl> NA, 17.77, 27.14, 16.50, 27.09, 11.90, 10.57, 10.54, …
    $ `April 2024`     <dbl> NA, 20.30, 25.70, 25.50, 33.79, 12.24, 8.90, 10.17, 9…
    $ `May 2024`       <dbl> NA, 21.10, 32.79, 25.77, 29.56, 13.97, 9.12, 9.14, 10…
    $ `June 2024`      <dbl> NA, 20.50, 29.09, 25.97, 29.45, 13.52, 10.40, 9.91, 1…
    $ `July 2024`      <dbl> NA, 19.13, 30.83, 25.86, 35.62, 12.85, 9.66, 9.32, 7.…
    $ `August 2024`    <dbl> NA, 20.06, 29.96, 22.48, 29.95, 14.24, 10.24, 9.22, 7…
    $ `September 2024` <dbl> NA, 18.85, 34.03, 27.26, 35.08, 14.12, 9.87, 9.32, 6.…
    $ `October 2024`   <dbl> NA, 21.28, 27.64, 24.11, 28.12, 14.68, 9.63, 9.96, 8.…
    $ `November 2024`  <dbl> NA, 19.52, 28.41, 21.19, 33.11, 14.53, 9.69, 9.73, 9.…
    $ `December 2024`  <dbl> NA, 21.03, 27.82, 20.15, 29.35, 14.99, 9.18, 9.53, 9.…
    $ `January 2025`   <dbl> NA, 18.91, 29.81, 22.32, 32.67, 14.05, 10.08, 9.41, 6…
    $ `February 2025`  <dbl> NA, 19.80, 28.17, 27.86, 35.41, 15.09, 10.02, 8.64, 9…
    $ `March 2025`     <dbl> NA, 18.36, 40.20, 23.25, 37.41, 14.62, 9.07, 9.83, 8.…
    $ `April 2025`     <dbl> NA, 21.40, 45.70, 24.24, 31.11, 14.98, 10.05, 9.50, 1…
    $ `May 2025`       <dbl> NA, 21.46, 34.18, 27.58, 33.30, 16.12, 9.56, 9.86, 10…
    $ `June 2025`      <dbl> NA, 23.27, 27.22, 24.00, 35.08, 15.89, 9.85, 9.37, 9.…
    $ `July 2025`      <dbl> NA, 24.32, 30.80, 27.74, 37.28, 15.76, 9.62, 9.13, 7.…
    $ `August 2025`    <dbl> NA, 23.21, 33.84, 26.05, 33.41, 16.37, 10.33, 9.35, 9…
    $ `September 2025` <dbl> NA, 22.48, 31.96, 33.04, 42.60, 15.26, 9.52, 9.87, 6.…
    $ `October 2025`   <dbl> NA, 23.22, 31.92, 27.44, 32.33, 16.88, 10.56, 10.12, …
    $ `November 2025`  <dbl> NA, 22.92, 42.25, 32.25, 42.23, 16.93, 10.24, 10.06, …
    $ `December 2025`  <dbl> NA, 25.80, 34.41, 31.74, 31.87, 16.22, 10.20, 10.05, …
    $ `January 2026`   <dbl> NA, 22.41, 45.61, 31.40, 38.48, 16.41, 9.76, 10.14, 7…
    $ `February 2026`  <dbl> NA, 25.47, 33.14, 25.94, 41.04, 16.65, 9.90, 9.61, 7.…
    $ `March 2026`     <dbl> NA, 23.78, 40.19, 34.70, 37.61, 16.75, 10.05, 9.58, 8…
    $ `April 2026`     <dbl> NA, 25.04, 42.06, 28.22, 33.52, 17.43, 10.36, 9.77, 9…
    $ `May 2026`       <dbl> NA, 24.56, 35.49, 30.91, 31.78, 17.27, 10.06, 9.78, 9…
    $ `June 2026`      <dbl> NA, 25.77, 41.34, 31.97, 35.96, 18.32, 9.63, 11.00, 1…
    $ `July 2026`      <dbl> NA, 26.67, 43.24, 36.25, 34.13, 17.71, 9.98, 10.14, 9…
    $ `August 2026`    <dbl> NA, 23.99, 48.11, 26.71, 38.71, 18.19, 9.58, 10.65, 9…
    $ `September 2026` <dbl> NA, 26.59, 43.87, 31.59, 33.80, 17.76, 10.18, 10.30, …

The output shows that the Alberta dataset contains 115 rows and 86
columns. It includes grocery products in the first column and monthly
average retail prices in the remaining columns, covering September 2019
to September 2026. The prices are recorded in dollars and the dataset
includes information for different grocery items across each month. One
thing I noticed is that the first row contains the unit of measurement
(“Dollars”) rather than an actual grocery product.

## 2.2.2 Historical Minimum Wage Rates in Canada

Source:
<https://open.canada.ca/data/en/dataset/390ee890-59bb-4f34-a37c-9732781ef8a0>

**Producer and authority.** This dataset is published by Employment and
Social Development Canada. The department publishes historical minimum
wage information as part of its labour market and employment related
statistics.

**Original Dataset Purpose.** The purpose of this dataset is to provide
historical information about minimum wage rates in Canada. The dataset
makes it possible to examine how minimum wages have changed over time.
For my project, I will use these rates to compare wage increases with
changes in grocery prices.

**Collection method.** The dataset provides historical minimum wage
rates. However, the dataset description does not clearly explain the
original collection process or how the historical rates were verified.

**Coverage and resolution.** The dataset covers Canadian provinces and
territories. The information is organized by geographic area and
applicable wage rate. Unlike the grocery price dataset, which is updated
monthly, minimum wage rates change when new wage adjustments come into
effect. For my analysis, I will use the rates applicable during each
year from 2016 to 2026 and account for changes that occurred within a
year.

**Licence.** Open Government Licence – Canada. The dataset is publicly
available and can be downloaded in CSV format

**Access.** I accessed this dataset through the Government of Canada’s
Open Government Portal. It provides downloadable CSV files in English
and French. Other researchers can access the same dataset through the
portal. I accessed the source on November 5th 2026.

**Known problems.** One challenge is that minimum wage rates change at
different times and frequencies across provinces. I must use the exact
rate for each specific period rather than assuming it stays the same all
year.

    Rows: 597
    Columns: 4
    $ jurisdiction   <chr> "Federal", "Federal", "Federal", "Federal", "Federal", …
    $ effective_date <date> 1965-07-01, 1970-07-01, 1971-07-01, 1972-11-01, 1974-0…
    $ wage           <chr> "$1.25", "$1.65", "$1.75", "$1.90", "$2.20", "$2.60", "…
    $ note           <chr> "First legislated rate for federal jurisdiction.", NA, …

The dataset contains 597 rows and 4 columns, including jurisdiction,
effective date, minimum wage, and additional notes. The wage values
are stored as character data because they include dollar signs, so I
will need to convert them to numeric values before analysis.

## 2.3: Investigated and rejected sources

So far, I have not selected any alternative datasets to reject. My
research has mainly focused on finding grocery price and minimum wage
data that cover all Canadian provinces.

## 2.4: What I could not find

I could not find one dataset that directly compares grocery prices with
minimum wages across Canada. Instead, I found two separate datasets that
I will combine for my analysis.

I also found that the grocery price data only goes back to September
2019 for some provinces, rather than covering the full ten years I
originally planned.

------------------------------------------------------------------------

# 3: Licensing and permissions

## 3.1: Licence by source

| Source | Licence | Attribution_required | Attribution_given |
|:---|:---|:---|:---|
| Monthly Average Retail Prices for Selected Products: Food | Statistics Canada Open Licence | Yes | Yes, see below |
| Historical Minimum Wage Rates in Canada | Open Government Licence - Canada | Yes | Yes |

**Attribution statements.**

1\. Statistics Canada

> Adapted from Statistics Canada, Monthly Average Retail Prices for
> Selected Products: Food, Table 18-10-0245-02, reference date September
> 2019 to September 2026. This does not constitute an endorsement by
> Statistics Canada of this product.

Source: [Statistics Canada Open
Licence](https://www.statcan.gc.ca/en/terms-conditions/open-licence)

2\. Government of Canada

> Contains information licensed under the Open Government Licence –
> Canada.

Source: [Open Government Licence –
Canada](https://open.canada.ca/en/open-government-licence-canada)

## 3.3: Downstream permissions

Both datasets are available under open licences that allow people to
reuse, modify, and share the information. This means others can use the
data and the results from my project, provided they follow the
conditions of the original licences. Anyone reusing my project must give
credit to Statistics Canada and the Government of Canada using the
required attribution statements. They must also make sure their use does
not suggest that either organization endorses their work. I will keep
the original sources and their licence information clearly identified in
my project.

------------------------------------------------------------------------

# 4: Consent and identifiability

Neither dataset contains information about individual people. The
grocery dataset reports average food prices by province and month, while
the minimum wage dataset reports wage rates. Datasets contains economic
information rather than personal records, names, or other identifying
details.

**Consent.** I did not collect any information directly from
participants or conduct surveys or interviews. Both datasets were
collected and published by government organizations for public use.

**Identifiability.** The datasets do not identify individuals. The
smallest level of information used in my analysis is based on a
province, product, and month for grocery prices, or a jurisdiction and
effective date for minimum wages. Since the data is reported at these
levels rather than for individual people, there is no risk of
identifying someone through my analysis.

**How sensitive data will be used.** Neither dataset contains sensitive
personal information. I will not be collecting or publishing names,
addresses, financial records, or other personal details. My analysis
will focus on provincial averages and minimum wage rates, so no
additional steps to hide individual identities are needed.

------------------------------------------------------------------------

# 5: Exclusions and harms

## 5.1: Excluded data from the audit

In the grocery datasets, the first row after importing the CSV contains
the word “Dollars” to describe the units of measurement rather than an
actual grocery product. I will remove this row because it is not useful
for the analysis. I will also exclude any columns or rows that are not
needed for comparing grocery prices over time. For the minimum wage
dataset, I will focus on provincial minimum wage rates and exclude
federal rates.

One limitation is that the grocery price data only goes back to
September 2019, so I cannot include the years before that in my
comparison.

## 5.2: Who could be harmed

Someone could misuse my results to suggest that minimum-wage workers can
easily afford groceries. However, my project only looks at selected food
prices and does not include other costs like rent, transportation, and
bills. This could give people the wrong idea about how affordable life
really is for minimum-wage workers. I will make these limitations clear
when presenting my results.

## 5.3: Unreleased working data

I do not have any working data that needs to be kept private. Both
datasets are publicly available and contain grocery prices and minimum
wage information, not personal details. I am comfortable sharing the
original data, cleaned datasets, and code so others can review and
reproduce my work.

------------------------------------------------------------------------

# 6: Data Stewardship

**Where it lives.** The project files will be stored in my GitHub
repository. This includes the original CSV files, cleaned datasets, R
Markdown document, and analysis code.

**Who maintains it.** I will maintain the project during the course. I
do not currently plan to update it regularly after the course ends
though.

**Formats and dependencies.** The data is saved in CSV files, and my
project is written in R Markdown. I use packages
like `tidyverse` and `knitr`. In the future, updates to these
packages/changes to the data links might affect my project.

**Lifespan.** The project will remain useful as a historical comparison
of grocery prices and minimum wages from 2019 to 2026. However, it may
become less useful for understanding current affordability as prices and
wages change. 

------------------------------------------------------------------------

# 7: Use of AI

I used Claude to help with issues when importing the Statistics Canada
datasets into R. In particular, it helped me understand why I needed to
use `skip = 9` in `read_csv()` to skip the extra information at the
beginning of the CSV files and properly load the data.

------------------------------------------------------------------------

# 8: Session information

    R version 4.6.1 (2026-06-24)
    Platform: aarch64-apple-darwin23
    Running under: macOS Tahoe 26.6.2

    Matrix products: default
    BLAS:   /Library/Frameworks/R.framework/Versions/4.6/Resources/lib/libRblas.0.dylib 
    LAPACK: /Library/Frameworks/R.framework/Versions/4.6/Resources/lib/libRlapack.dylib;  LAPACK version 3.12.1

    locale:
    [1] en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8

    time zone: America/Moncton
    tzcode source: internal

    attached base packages:
    [1] stats     graphics  grDevices utils     datasets  methods   base     

    other attached packages:
     [1] lubridate_1.9.5 forcats_1.0.1   stringr_1.6.0   dplyr_1.2.1    
     [5] purrr_1.2.2     readr_2.2.0     tidyr_1.3.2     tibble_3.3.1   
     [9] ggplot2_4.0.3   tidyverse_2.0.0

    loaded via a namespace (and not attached):
     [1] bit_4.6.0          gtable_0.3.6       jsonlite_2.0.0     crayon_1.5.3      
     [5] compiler_4.6.1     tidyselect_1.2.1   parallel_4.6.1     scales_1.4.0      
     [9] yaml_2.3.12        fastmap_1.2.0      R6_2.6.1           generics_0.1.4    
    [13] knitr_1.52         pillar_1.11.1      RColorBrewer_1.1-3 tzdb_0.5.0        
    [17] rlang_1.3.0        stringi_1.8.9      xfun_0.60          S7_0.2.2          
    [21] bit64_4.8.6        otel_0.2.0         timechange_0.4.0   cli_3.6.6         
    [25] withr_3.0.3        magrittr_2.0.5     digest_0.6.39      grid_4.6.1        
    [29] vroom_1.7.1        rstudioapi_0.19.0  hms_1.1.4          lifecycle_1.0.5   
    [33] vctrs_0.7.3        evaluate_1.0.5     glue_1.8.1         farver_2.1.2      
    [37] rmarkdown_2.32     tools_4.6.1        pkgconfig_2.0.3    htmltools_0.5.9   

<!--
BEFORE YOU SUBMIT
&#10;- Does your file render from a clean session (wiping the environment and history with no errors?
- Are all paths relative? No setwd(), no C:/Users/yourname/
- Is every package you used declared in the setup chunk?
- Is AI-LOG.md committed and current?
- Could a stranger read this and know what you are hoping to do in your project, what your data is, where it came
  from, and what others are allowed to do with it?
- Have you deleted every bracketed prompt including this comment block?
-->
