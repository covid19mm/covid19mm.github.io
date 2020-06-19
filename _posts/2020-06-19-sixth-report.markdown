---
layout: post
title:  "Sixth Report"
date:  2020-06-19 18:00:00
author: The COVID19 MM working group
categories: in-progress
#cover:  "assets/instacode.png"
---

# Mobility in Italy after the complete removal of travel restrictions

_Authors:_

_Emanuele Pepe (1), Paolo Bajardi (1), Laetitia Gauvin (1), Filippo Privitera (2), Brennan Lake (2), Ciro Cattuto (1,3), Michele Tizzoni (1)_

_1. ISI Foundation_

_2. Cuebiq Inc._

_3. University of Turin_

_**Notice**: this is preliminary analysis, has not yet been peer-reviewed and is updated daily as new data becomes available. This work is licensed under a  [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/)._


## Background
The mitigation measures enacted as part of the response to the unfolding COVID-19 pandemic are unprecedented in their breadth and societal burden.
A major challenge in this situation is to quantitatively assess the impact of non-pharmaceutical interventions like mobility restrictions and social distancing, to better understand the ensuing reduction of mobility flows, individual mobility changes, and impact on contact patterns.
Here, we report preliminary results on tackling the above challenges by using de-identified, large-scale data from a location intelligence company, Cuebiq, that has instrumented smartphone apps with high-accuracy location-data collection software.

Italy has been severely affected by the COVID-19 pandemic.
Following the identification of the first infections, on February 21, 2020, national authorities have put in place an increasing number of restrictions aimed at containing the outbreak and delaying the epidemic peak.
On March 12, the government imposed a national lockdown.
On May 4, the lockdown has been lifted and since May 18 most of business acitivities, especially in the retail sector, have restarted.
Since June 3, restrictions on the inter-regional mobility have been completely removed, thus restoring the freedom of movement across the country in full.

Here, we analyze how mobility and proximity patterns in Italy have changed during the week of June 6-12, at the sub-national scale.


## Data
Mobility data is provided by Cuebiq, a location intelligence, and measurement platform. Through its [Data for Good program](https://www.cuebiq.com/about/data-for-good/), Cuebiq provides access to aggregated and privacy-safe mobility data for academic research and humanitarian initiatives. This first-party data is collected from anonymized users who have opted-in to provide access to their location data anonymously, through a GDPR-compliant framework.

Location is collected anonymously from opted in users through smartphone applications. At the device level, iOS and Android operating systems combine various location data sources (e.g. GPS, wifi, beacons, network) and provide geographical coordinates with a given level of accuracy. Location accuracy is determined by the device and is variable, but can be as accurate as 10 meters.

Temporal sampling of anonymized users’ location is also variable and dependent on app/OS characteristics and on user behavioral patterns, but it has a high-frequency overall. We remove short-time dynamics by aggregating the data over 5-minute windows. The basic unit of information we process is an event of the form (anonymous hashed user id, time, latitude, longitude), plus additional non-personal metadata and location accuracy.

For a more detailed description of the underlying data, please see the page [Data](https://covid19mm.github.io/data.html).


## Methods
From the original location data, we derive three epidemiologically relevant metrics of mobility and proximity that capture both long-range and short-range mobility patterns:
1. the weekly origin-destination matrices measuring users' movements between Italian provinces;
2. the weekly users' average radius of gyration by province, capturing the extent of individual movements;
3. the daily average degree of users' proximity network, capturing the level of social distancing by province.

All these metrics are computed by aggregating the original data sources in space and time in order to comply with privacy principles that ensure users cannot be re-identified, even indirectly, from the data.

A more detailed description of how these metrics have been generated can be found in the preprint:

_Pepe, E., Bajardi, P., Gauvin, L., Privitera, F., Lake, B., Cattuto, C., & Tizzoni, M. (2020).<br/>
[COVID-19 outbreak response: a first assessment of mobility changes in Italy following national lockdown](https://www.medrxiv.org/content/10.1101/2020.03.22.20039933v1).<br/>
medRxiv: [https://www.medrxiv.org/content/10.1101/2020.03.22.20039933v1](https://www.medrxiv.org/content/10.1101/2020.03.22.20039933v1)_


## Summary of results

At the national level, mobility patterns have continued increasing across the whole country, but still remain below the baseline levels (we consider the period from January 18 to February 21 as our baseline) although there are no mobility restrictions in place, anymore.

Users' movements between different provinces are now at **-3%**, on average, with respect to the baseline.
Outgoing mobility from some provinces has increased above the baseline levels, especially in Center and Southern Italy.
During the lockdown, the largest average reduction observed was **-71%** at the national level.

The median radius of gyration has increased in all provinces but remains everywhere below the baseline levels.

The average degree of the proximity network, at the national level, has reached levels equal to **-14%** with respect to the baseline.
Such values are similar to those observed during the week of May 15-22, thus indicating that spatial proximity has not substantially increased in the past month.


## Movements between provinces

The figure below shows the relative change in the weekly fraction of users traveling out of the Italian provinces during the week of June 6-12, with respect to baseline levels.

Movements have further increased, since the removal of the restrictions.
In several provinces, outgoing movements have reached volumes that are above the baseline, especially in the Center and Southern Italy, such as in Grosseto (+6%), Potenza (+6%), Crotone (+11%), Campobasso (+14%).
On the other hand, outgoing movements from large urban areas remained generally below the baseline, between **-11%** (Turin) and **-6%** (Naples).


<p align="center">
  <img src="{{ site.url }}/assets/map_outgoing_phase2_june12.png">
</p>


## Radius of gyration

The figure below shows the median weekly radius of gyration of our users by province, as a percentage of the baseline levels.
Provinces are ranked by the relative increase of the radius of gyration during Phase 2, from the largest (top) to the smallest (bottom).

The median radius of gyration has further increased since the first week of Phase 2, but still remains on average at **-28%** below the baseline values.

The median radius of gyration of users who live in large urban areas still remains between 40% (Milan) and 60% (Rome) of the values observed before the outbreak.

<p align="center">
  <img src="{{ site.url }}/assets/radius_lockdown_june12.png">
</p>

## Proximity network

The increasing trend of the average degree of the proximity network, *&lt;k&gt;*, has slowed down.  
Overall, the values of *&lt;k&gt;* are still below the baseline levels and did not increase much with respect to the week of May 15-22.
In the week of June 6-12, the average degree has increased to **-15%** below baseline in the North, **-15%** in the Center and **-12%** in the South, remaining [almost stable in a month](https://covid19mm.github.io/in-progress/2020/05/27/fifth-report.html).

Our results suggest the presence of a residual social distancing, quite uniform across the country, which might be ascribed to the current recommendations of adopting a self-protective behavior in public spaces.

<p align="center">
  <img src="{{ site.url }}/assets/prox_network_density_1206.png">
</p>


The heatmaps below show the time evolution of the average degree of the proximity network by province.

### Northern Italy

<p align="center">
  <img src="{{ site.url }}/assets/density_relnord_june12.png">
</p>

### Central Italy


<p align="center">
  <img src="{{ site.url }}/assets/density_relcenter_june12.png">
</p>

### Southern Italy

<p align="center">
  <img src="{{ site.url }}/assets/density_relsud_june12.png">
</p>


## Data Protection

This research was solely based on data from anonymized users who have opted-in to provide access to their location data anonymously, through a GDPR-compliant framework. The analysis never singled out identifiable individuals and no attempts were made to link these data to third party data about an individual.
In order to preserve privacy, residential areas are inferred at an aggregated geohash level, thereby allowing for demographic analysis while obfuscating the true home location of anonymous users and prohibiting misuse of data.


## Acknowledgments and Partnerships

This preliminary analysis is a collaboration between the [ISI Foundation](https://www.isi.it/en/home) and [Cuebiq Inc](https://www.cuebiq.com/).
Authors at ISI Foundation acknowledge support from the Lagrange Project funded by CRT Foundation and thank Cuebiq for access to a de-identified sample of its mobility data. In response to the COVID-19 crisis, [Cuebiq is providing insights to academic and humanitarian groups](https://www.cuebiq.com/about/data-for-good/) through a multi-stakeholder data collaborative for timely and ethical analysis of aggregate human mobility patterns.
