**Heatwaves and cold snaps alter host-parasite population dynamics in the Daphnia magna-Ordospora colligata system**


Niamh McCartan1 (corresponding author), Louise Bezborodko1,2, Joseph Strawbridge1, Floriane O’Keeffe1,  Sadie DiCarlo1,3, and Pepijn Luijckx1.


1 Discipline of Zoology, School of Natural Sciences, Trinity College Dublin, Dublin 2, Ireland.

2 L’Institut Agro Rennes-Angers, Campus de Rennes, 65 rue de Saint-Brieuc, 35042, Rennes, France.

3 Carleton College, Sayles Hill Campus Center, North College Street, Northfield, MN 55057, USA.


This dataset contains infection prevalence and burden observations collected from _Daphnia magna_ infected with its microsporidian parasite _Ordospora colligata_ at the School of Natural Sciences in Trinity College Dublin. The main experiment was a population-level experiment carried out in summer/autumn 2024. Additional data was extrapolated from two individual-level experiments (heatwave experiment occurred in spring 2022, cold snap experiment occurred in summer 2022). This study looked at the effect of heatwaves and cold snaps on parasite and host fitness. Here, a heatwave meant a increase in baseline temperature (constant mean temperature) by 6 degrees and a cold snap meant a decrease by 6 degrees. 


Two main response variables were considered:

* Burden — the number of _Ordospora_ spore clusters per host, including zeros for uninfected but exposed individuals.

* Population size — the mean number of adult _Daphnia_ in experimental populations.

A Before–After–Control–Impact (BACI) framework was used, with the factor period representing experimental phases: constant treatment, before pulse (weeks 1–4), during pulse (week 5), just after pulse (week 6), and after pulse (weeks 7–9).

Generalised Linear Mixed Models (GLMMs) were fitted using the glmmTMB package with a negative binomial link to account for overdispersion. Mesocosm was included as a random effect to control for batch-level variability.

For burden, predictor variables included baseline temperature (quadratic), period, and population size (centred).
For population size, predictor variables included baseline temperature (cubic), period, and burden (scaled).

Custom contrasts were performed with the emmeans package, adjusting p-values with the Benjamini–Hochberg method for multiple comparisons. Results were compared to individual-level findings from previous studies to link host-level responses with population-level outcomes.

-----------------------------------------------------------------------------------------

**R scripts for analysis**

_Pop_Analysis.Rmd_: analysis and graphing for the the whole manuscript including populaiton-level and individual-level analysis.

_________________________________________________________________________________________

**List of datasets used for analysis**_

_Pop_full.csv_: observations of burden and population size

```
Rep: Sample number for the _Daphnia_ being observed that week (6 replicated for burden, 2 replicates for populaiton)
Temp: target baseline tempetature 
Real_Temp: the true temperature per bath read from the HOBO loggers at the end of the experiment 
Treat: If the treatment was control (C), or given a heatwave (HW) or cold snap (CS)
Pulse: If the treatment was given a thermal pulse, either yes (Y) or no (N)
Bucket: Number of the bucket per treatment (1 to 5)
Bath: Which bath the bucket was in (A, B, or C). 
Date: Date of observation 
Week: The week that the observation was taken (1 to 9)
BACIplus: Which period the week fell into, before, during, just after, after, constant 
BACIplus_CC: Same as back but compartmentalising the constants into periods too 
Infection: If the host was infected, presence (1) or absence (0)
Spores: Number of spores present, 0 if nothing 
Adults: number of adults in the population
Notes: Any important noted given when measurements were taken 
Include: Yes if included in analyssi, no if excluded
```

_Exp_comp.csv_: observations for burden in the individual level (heatwave and cold snap) experiment and relevant population data (from during the thermal variation

```
Exp: Which experiment the data came from, population (POP), heatwave (HW) or cold snap (CS) experiemnts
Period: Which period the measuement fell into, before, during, just after, after, constant 
A_Temp: target baseline tempetature 
Real_Avg:the true temperature per bath read from the HOBO loggers at the end of the experiment 
Treat: If the treatment was control (C), or given a heatwave (HW) or cold snap (CS)
Rep: Sample number for the _Daphnia_ being observed
Bath: Which bath the bucket _Daphnia_ was in (A, B, or C)
Day: The day of the measurement
Infection: If the host was infected, presence (1) or absence (0)
Spores: Number of spores present if infected, if exposed but uninfected NA entered
Exposed: Number of spores present, 0 if nothing 
```

_HOBO_temps.xlsx_: temperature data per bath per hour, also with overall mean temperature

```
#: Time point recording ID
Date Time, GMT+00:00: Date and time of time point recording 	
Temp, °C: Temperature recorded					
Average Temp: Average temperature only including temperature points ±2 degrees
Logger ID: Logger ID used for the specific bath
```
