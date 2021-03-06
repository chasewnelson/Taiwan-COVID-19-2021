<img src="https://github.com/chasewnelson/SARS-CoV-2-ORF3d/blob/master/images/cover_image.png?raw=true" title="SARS-CoV-2 alignment montage" alt="SARS-CoV-2 alignment montage" align="left" size="small">

# Taiwan COVID-19 Analyses (2021)
Data, methods, and results of analyses tracking the 2021 COVID-19 outbreak in Taiwan.


## <a name="contents"></a>Contents

* [Description](#description)
* [Data Sources](#data-sources)
* [Methods](#methods)
* [Results](#results)
	* [Backlogging](#backlogging)
	* [Time-Lapse of Cases](#time)
	* [Cases By Date Added](#cases)
	* [Seven-Day Average of Total Reported Cases](#seven)
	* [Backlog Time Distribution](#backlog)
	* [Projected Totals After Revision](#projected)
* [Notes and Clarifications](#notes)
* [Acknowledgments](#acknowledgments)
* [Contact](#contact)


## <a name="description"></a>Description

These charts depict the ongoing case numbers in Taiwan since an outbreak began in early May 2021, with Taipei declaring a Level 3 Alert on May 15. Data are recorded as they are announced by the [Ministry of Health and Welfare](https://www.facebook.com/mohw.gov.tw) (MOHW) each day at 2pm (14:00) Taipei Time. 

This repository collects the data shown each day and the analysis methods used. Specifically:

* The `data` folder contains data displayed on each date
* The `visualizations` folder contains visualizations by date
* The R script `Taiwan_COVID19_data.R` contains the code used to produce numerical results and visualizations

I focus on a few key metrics, and make no attempt to be thorough. For example, I do not currently track deaths or *R*<sub>t</sub>, which are [metrics that lag far behind cases](https://www.nature.com/articles/d41586-020-02009-w/). My purpose is not to provide a complete picture, but rather clear ways of understanding the case counts as they are revised, and what they might tell us about the trajectory of the outbreak. All opinions are my own.


## <a name="data-sources"></a>Data Sources

Raw data were retrieved from the following sources:

1. Taiwan CDC 

`https://data.cdc.gov.tw/dataset/daily-cases-suspected-sars-cov-2-infection_tested`
`https://data.cdc.gov.tw/en/dataset/covid19_tw__stats`
`https://data.gov.tw/dataset/120451`
`https://data.cdc.gov.tw/dataset/daily-cases-suspected-sars-cov-2-infection_tested`
`https://data.cdc.gov.tw/en/dataset/agsdctable-day-19cov`

2. Taiwan Ministry of Health and Welfare (MOHW)

`https://www.facebook.com/mohw.gov.tw`
`https://twitter.com/MOHW_Taiwan`

3. ?????? (Commonwealth)

`https://web.cw.com.tw/covid-live-updates-2021-en/index.html`

4. Open Data Public Collaborations (g0v, etc.)

`https://docs.google.com/spreadsheets/d/1qh20J-5rGVIEjLcGKJnfj7huAp-nCxsd-fJdmh3yZKY/htmlview#`
`https://docs.google.com/spreadsheets/d/12tQKCRuaiBZfc9yDd6tmlOdsm62ke_4AcKmNJ6q4gdU/htmlview#`

4. NHCH (death data)

`https://covid-19.nchc.org.tw/deathstatistics.php?dt_name=1&downloadall=yes`


## <a name="methods"></a>Methods

Data were downloaded or manually recorded from the aforemenetioned sources. All statistical analyses were performed in Microsoft Excel and R version 3.5.2 (2018-12-20) "Eggshell Igloo" (<a target="_blank" href="https://www.R-project.org/">R Development Core Team</a>). Specifically, the R script `Taiwan_COVID19_data.R` was used to analyze data and produce raw visualizations, which were then modified in Microsoft PowerPoint. GIFs were created using [GIFMaker.me](https://gifmaker.me/). Note that the R script is meant to be run manually, line-by-line in an interactive program such as RStudio. This forces the user (e.g., me!) to inspect the results as they are analyzed, check for errors, and make any changes necessary due to peculiarities in each day's new results.


## <a name="results"></a>Results

I here provide demonstrations of the results produced for the date of June 5, 2021 (20210605). The charts will not be regularly updated; instead, updates will be posted to <a target="_blank" href="https://twitter.com/chasewnelson">Twitter</a> and <a target="_blank" href="https://www.facebook.com/chasewnelson">Facebook</a>. 

### <a name="backlogging"></a>Backlogging

Because of an initially limited testing capacity, tests have been delayed and results routinely assigned to previous days, a method referred to as 'backlogging'. Backlogging achieves increasingly accurate counts for individual days. However, it also introduces difficulties for comparing *between* different days. Specifically, while results are still unfinished, it can create the illusion of a downward trend (drop in case numbers) as an artifact, because recent days will be disproportionately underestimated. This has been brilliantly explained by [Linc_tw](https://twitter.com/Linc_tw/status/1397207338059276297).

The visualizations below demonstrate the effect backlogging may be having on perceived trends, and to clarify the meaning of the revised data being reported. Finally, we provide a projection of finalized counts as a function of the current backlog and its known time distribution.


### <a name="time"></a>Time-Lapse of Cases

Results below are depicted by **days late** (shade of red). Late additions to previous days (backlogging) can create the illusion of a downward trend, because recent days will be disproportionately underestimated, having had fewer chances (days) to 'score points' from backlogging. Put another way, many more tests are 1-day-late than 10-days-late. Thus, these lighter bar portions grow larger closer to the present (right) because they are predicted to be less complete: future revisions should change today???s total a lot more than totals from a week ago. Based on the backlogging pattern observed thus far, we considered dates >9 days in the past relatively ???locked in??? (unlikely to change substantially).

<img src="https://github.com/chasewnelson/Taiwan-COVID-19-2021/blob/main/visualizations/time_lapse_20210605.gif?raw=true" title="Time-lapse of Cases" alt="Time-lapse of Cases" align="left" size="small">

<img src="https://github.com/chasewnelson/Taiwan-COVID-19-2021/blob/main/visualizations/cases_by_days_late_20210605.png?raw=true" title="Cases by days late" alt="Cases by days late" align="left" size="small">


### <a name="cases"></a>Cases by Date Added

Results below are instead depicted by **date added** (shade of orange) during backlogging. This is helpful because the original same-day values (blue bars, following the MOHW color scheme), a better metric of trend than the revised values, can be clearly seen.

<img src="https://github.com/chasewnelson/Taiwan-COVID-19-2021/blob/main/visualizations/cases_by_date_added_20210605.png?raw=true" title="Cases by date added" alt="Cases by date added" align="left" size="small">


### <a name="seven"></a>Seven-Day Average of Total Reported

Results below are shown as 7-day averages (red line) using non-backlogged TOTALS REPORTED each day (gray bars). Each day is the mean of itself and the previous 6 days. This provides a decent measure of trend when outstanding tests remain unfinished and the extent of possible revisions to previous dates is uncertain.

<img src="https://github.com/chasewnelson/Taiwan-COVID-19-2021/blob/main/visualizations/cases_reported_7dayWindow_20210605.png?raw=true" title="Seven-Day Average of Total Reported" alt="Seven-Day Average of Total Reported" align="left" size="small">


### <a name="backlog"></a>Backlog Time Distribution

On the day shown (June 5, 2021) the backlog was ~10k tests. To that point, 24% of tests had been assigned to the previous day; 19% to the day before that; and so on. This allowed a projection of how the current backlog would be distributed (next section).

<img src="https://github.com/chasewnelson/Taiwan-COVID-19-2021/blob/main/visualizations/backlog_time_distribution_20210605.png?raw=true" title="Backlog Time Distribution" alt="Backlog Time Distribution" align="left" size="small">


### <a name="projected"></a>Projected Totals After Revision

For this date (June 5, 2021), 1.8% of recent targeted tests (likely cases) had been positive. Given this, a simple estimate was that 1.8% of the ~10k backlog would test positive and be distributed to previous dates in the same manner (distribution) observed up to that point in time. Based on this reasoning, Albert Lin ????????? and I made the projection below, which is an estimate of the final counts if the full current backlog were completed the next day. Conceptually, it simply takes the projected backlog numbers implied by the [backlog time distribution](#backlog) (above) and places it on top of the current revised counts.

<img src="https://github.com/chasewnelson/Taiwan-COVID-19-2021/blob/main/visualizations/projected_total_20210605.png?raw=true" title="Projected Totals After Revision" alt="Projected Totals After Revision" align="left" size="small">


## <a name="notes"></a>Notes and Clarifications

1. For the date of May 30, 2021 (20210530), the MOHW retracted the backlogged numbers provided at press time. The analyses for that day use their [updated values](https://twitter.com/MOHW_Taiwan/status/1398166785363349505), released later that day shortly before 5pm (17:00) Taipei Time.


## <a name="acknowledgments"></a>Acknowledgments

Mitch (Ming-Hsueh) Lin ????????? was critical for conceiving visualizations. Albert Lin ?????????, Mitch (Ming-Hsueh) Lin ?????????, and Alexis (surname unknown) provided critical insights and feedback. The Taiwan CDC and MOHW, as well as the open source data sharing community in Taiwan (including Samuel Liu and g0v) were essential for openly sharing and compiling data. Finally, a big thanks to the government, medical, and science workers who have made Taiwan ??? still ??? the Safest Place On Earth. We're lucky to live in this country. <a target="_blank" href="https://www.nature.com/articles/d41586-020-00693-2">It should be part of the World Health Organization (WHO)</a>.


## <a name="contact"></a>Contact and troubleshooting

If you have questions about the methods or results, please first thoroughly read the description and in-line comments relevant to the analysis of interest. If these do not answer your question, please click on the <a target="_blank" href="https://github.com/chasewnelson/Taiwan-COVID-19-2021/issues">Issues</a> tab at the top of this page and search to see if your question has already been answered; if not, please begin a new issue, so that others might benefit from the discussion.

Other queries should be addressed to the author: 

*  Chase W. Nelson, cnelson <**AT**> gate <**DOT**> sinica <**DOT**> edu <**DOT**> tw
