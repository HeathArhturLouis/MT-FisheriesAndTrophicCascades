# Trophic cascade experiments 
[Introductory Sentance Linking to previous material 
and referencing position of section in finished paper]


## Problem Background 

To further validate our model, we attempted to reproduce a three species trophic cascade, where the sustained over-exploitation of an apex predator species indirectly lead to a sharp rise in the population density of a species lower down the food chain (in the literature this phenomenon is known as 'top-down forcing' [3]). Specifically, we attempted to emulate the trophic cascade observed in the Aleutian Archipelago between the years 1986 and 2000 [1]. In this scenario, a declining population of sea otters (due to human exploitation) had a radical effect on the population of sea urchins (their typical food-source) and indirectly effected the population density of kelp in the area (the primary food-source of the urchins). Although the study considers an additional trophic role, that of rock greenlings, there are several compelling factors that make it an appropriate choice for our purposes. Firstly, rock greenling were affected indirectly, as their only interaction with the other species is as a consumer of kelp. Secondly, the biodiveristy of the archipelago is relatively low (the total biomass of other fish species is only a fraction of that of the rock greenling), meaning the data is likely to contain far less noise than typical. Finally, this ecosystem has been well documented over the years, acting as a 'Drosophila' in the study of trophic cascades and ecosystem dynamics [4]. As a result we were able to draw on ample sources of additional data for parameter tuning.



## Parameter Tuning


The logistic caps for the populations of kelp (represented by algae), and sea urchins (sardines) were set to the ratio of the number of individuals per square meter in the vicinity of the Attu islands (computed from the original paper and typical sea urchin weights sourced from [2]). Behavioural parameters were determined through an search process based on the principles of "pattern oriented modelling" [Citation needed] ---. Although the final population of sea otters is proportionally higher than that of the archipelago [5], this was deemed acceptable due to their high real-life mobility compared to the other species (many sea otters are likely entering and leaving a specific area at any one time). The search process aimed to fulfill the following constraints:

  - All three populations should remain stable after 500 generations (no species rendered extinct).
  - Population levels should stabilize substantially below their respective logistic growth caps (to avoid constraining potential dynamic changes)
  - Agents' behaviours should resemble the patterns of their real world counterparts to the greatest degree possible (Sea otters should maintain a low growth rate and act as intelligent hunters, kelp growth rate should be kept high etc...)

The resulting parameters, (attached in appendix [TODO: Appendix]) were tested on a batch of 30 runs and were found to be stable 86.66666_% of the time. Notably, the ratio of stable populations of kelp and urchins was greater than that of their respective caps, and closely resembled that of the Amchika islands in 1986 [1].

[mvingaverage200.png](mvingaverage200.png) 

## Methodology & Results

To simulate increased exploitation of otters, the shark throwback rate parameter was decreased from 100% to 80% mid simulation. A constant unsustainable rate of exploitation was expected to produce an approximately linear decline in the average population of otters (reflective of that observed in [6]). Although possible, higher exploitation rates were found to have a significant detrimental impact to the stability of the simulation. An example of such a simulation can be seen in figure [fig] (the beginning of exploitation is denoted by the vertical red line). Populations are plotted as a moving average of 150 time steps to reduce noise and highlight general trends. The effects of the trophic cascade are clearly visible as increases in the average population of urchins and decreases in that of otters and kelp (in the latter these are somewhat harder to see). A relatively long simulation was chosen to showcase large fluctuations in population size typical of our model (around time-step 700 in [fig]).

Due to the large quantity of such noise, further experimentation was conducted at these parameters to determine the typical scope of the cascade and to prove the effect can be reproduced. A sample of 30 simulations 600 time-steps in length and with trophic cascades induced at the 300th time-step was conducted. Of these, two resulted in the collapse of the ecosystem and were subsequently discarded. Six measurements were taken from each of the remaining 28 samples corresponding to the stable population sizes before and after the cascade (calculated as the mean population of the first and last 300 simulations respectively). The measured changes in stable population rates are displayed in [Fig]. Notably, all three populations settled at stable rates significantly below their respective caps. The stable population rate of otters was found to have decreased by and average of 29.6%, of urchins to have increased by 11.3% and of kelp to have decreased by 2.5%. A student t-test was conduced on each pair of samples (corresponding to a species) to determined the significance of these results [Table].

## Conclusions

[Bad results and why]

The scope of the effect reproduced by our model differs greatly from that presented in the selected study (kelp populations decreased by as much as 10 times). Upon closer observation of our model's behaviour, it appears that the peturbations to stable population levels diminish as they move down the food chain. A likely cause for this is the logistic growth limit of our models agents, witch exhibits a tendency to keep populations at the extremes. Regrettably, attempts to correct this issue (by for example moving to a linear growth rate) proved largely unsucesfull. In light of this, our models numerous assumptions and the unavoidable discrepancies between model and real world parameters, it would appear our model has low predictive value when it comes to specific ratios of populations. Although the discrepancies observed in this regard were larger than initially expected, this is unsurprising for models of this sort [Citation needed]. In contrast to our model's low tactical value, it has been shown to be capable of producing predictable and consistent results on a more abstract level. This points towards it potential strategic value for modelling trophic relationships and predicting general trends. In this regard the validation process has proved successful. 



Paper on trophic cascades in Aelutian archipelago:

[1] https://link.springer.com/content/pdf/10.1007/s00442-005-0230-1.pdf

[6] General otter population changes:

https://www.researchgate.net/figure/Sea-otter-expansion-into-estuarine-habitats-Trends-in-sea-otter-densities-for-outer_fig1_324999795

[5] The sea otter in eastern pacific ocean:

https://books.google.co.uk/books?hl=sl&lr=&id=EpHY-DEpj50C&oi=fnd&pg=PR3&dq=pacific+sea+otter+population&ots=nPd3nanwAI&sig=de2VE0aI2oOo0P3QkNi4O2gsjCQ&redir_esc=y#v=onepage&q&f=false


Sea urchin weight:

[2] file:///home/chrome/Downloads/DeZoysaetal-2017-IJAB_LWR_S.v-6.pdf


[3] https://www.sciencedirect.com/science/article/pii/S0924796307002680?casa_token=7DxfQuNCUg0AAAAA:dQShUNakmOmN41IzMg62NdFGmLobFt3sBCzonNbUa0KWXqRciR-FcYZ_nsqbNqb7CzMkWsl2sPc 

[4] https://www.jstor.org/stable/44519796?seq=1
