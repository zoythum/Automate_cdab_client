# Benchmark it at home

## Background
The Copernicus Sentinels Data Access Worldwide Benchmark Test Suite has been developed from Exprivia and ESA in order to analyse the performances of different Copernicus Data Providers from the point of view of the end user. \
To do so a set of 10 Quality of Experience (QoE) Indicators have been theorized, the goal of these QoE is to measure in a deterministic approach different aspects of the user experience ranging from the Discoverability of the catalogue to the Service Support. 

## Non power user
During my internship at ESA I worked on developing plugins to simplify the usage of the CDAB Test Suite, while doing so I run the benchmarks multiple times and noticed that the results I was getting where consistently different from the official ones. Therefore I decided to organize a home benchmarking experience that could explore the differences between the results obtained from official sources and the ones obtained by non power users, equipped only with their laptops and home connections, to understand if it's feasible for them to produce meaningful results.

## Setup
To start the campaign I contacted various volunteers located in different cities around Europe, each one was asked to download the benchmarking SW Suite and to run an unspecified number of tests targeting the OpenHub provider. When this phase was completed the results were send back and analysed.

## Local conditions and their effects
The first step of the analysis was to observe the effects of local conditions that are a unique trait of non power users, in fact official results are not influenced by the bandwith workload or the hardware used since each run is executed on a dedicated machine with reserved band and fixed hardware. 
The first step was to create  a script that executes Test Case 201 multiple times and keeps track of the timings, then I created two different settings, one where the script was the only applicative running on my computer and the other where I also had multiple tabs opened on a browser and a streaming service in play. This procedure was aimed at determining if the load of the bandwith could influence the results, indeed the first set of runs was completed with a timing between 7 and 11 minutes while the second set of runs shown an increase of 10% with timings between 8 and 13 minutes. \
After this first test I decided to calculate QoE2 with metrics produced at different times of the day to understand if the same variability observed on raw data could be mirrored on the aggregation, the results instead didn't present any meaningful variation through the day for the indicator.

## Indicators and metrics
The results of the previous step of the analysis show that, despite having a great variability with respect to the basic metrics, the indicators are quite stable, this is due to how we produce these aggregators. Each metric is filtered and transposed into a value in the set [0, 0.5, 1] using two thresholds, this technique ensures that measurments of different types can be combined into a single value; however, at the same time, different values are translated into the same final output. A user interested in determining his ability to profitably use the Copernicus Data Providers should thus keep in mind that the information tracked by the indicators might not be the same as the ones extracted from the raw metrics.

## Conclusions
From the different tests I executed it is clear that any end user with proper knowledge of how the Benchmarking Software Suite works and what are the design decisions behind it can use it to understand the capabilities of its local connection. It might be required to apply some modifications such as using less strict thresholds during the filtering procedure or removing the randomization applied to some test cases.