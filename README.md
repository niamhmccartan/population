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

-------------------------------------------------------------------------
