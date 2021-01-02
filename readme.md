# Evaluating Proxy Influence in Assimilated Paleoclimate Reconstructions—Testing the Exchangeability of Two Ensembles of Spatial Processes

# Author Contributions Checklist Form

## Data

### Abstract

The DA-based CFR that we analyze comes from the Paleo Hydrodynamics Data
Assimilation product (PHYDA), which is a global paleoclimate
reconstruction of both temperature and moisture variables, run over the
historical years 850 C.E. to 1850 C.E. The temperature modeled
temperature fields are processed from the native model output by annual
averages and spatially discretizing onto a 2 degree latitude and
longitude grid (144 x 96 grid points). Annual in this context is defined
as the interval between April and March of the following year, thus
yielding 998 such climatological years to be used for the background
ensemble. We only used a 100 member sub-ensemble, randomly drawn from
the original 998 member ensemble, for our analyses. The 998 analysis
states are derived from the background state by using DA to incorporate
temporally available proxy information during each year of
reconstruction. Each analysis state is also a 100 member ensemble of 2m
surface temperature fields discretized to the same 2 degree latitude and
longitude grid as the background ensemble.

### Availability

Publicly available

### Description 

Permissions:

Data is published in *Scientific Data* and has been made freely
available under the Creative Commons license

License:

Creative Commons Attribution 4.0 International

Link:

Publicly available here:
<http://clifford.ldeo.columbia.edu/nsteiger/recon_output/extremal_depth/>

The data files used are

Analysis: tas_ens_da_hydro_r.1000-2000_d.16-Feb-2018.nc

Background: tas_prior_da_hydro_r.1000-2000_d.16-Feb-2018.nc

Data provenance:

Original publication

Steiger, N. J., Smerdon, J. E., Cook, E. R., and Cook, B. I., [A
reconstruction of global hydroclimate and dynamical variables over the
Common Era](https://www.nature.com/articles/sdata201886), *Scientific
Data*, 5:180086, doi: 10.1038/sdata.2018.86.

Original dataset

10.5281/zenodo.1198817

Our data is a subsample (described in the above data abstract) of the
original PHYDA dataset.

File format:

These files are stored in the NetCDF (Network Common Data Form) format,
which can be read into R with the ncdf4 library.

### Optional Information

DOI: 10.5281/zenodo.1198817

## Code

### Abstract

Code consists all R scripts used to create each table and figure in the
paper and online supplement. The submit folder in the repository is
broken down into subsections for each part of the paper. For instance,
the conv folder contains all code related to convergence simulations,
maps creates all of the map figures, etc.

### Description

The code is freely available under the MIT License on the current master
branch of <https://github.com/trevor-harris/assimilation-cfr>

Use the submit folder to create anything in the paper or supplement. The
two data files will need to be added to the submit/data folder before
any data-based results can be reproduced.

### Optional Information

Convergence, power, and size simulations were run on a cluster in
parallel. They have been each rolled into loops for local processing,
but this would take a very long time to run in full.

Requires R 3.5+ and the following R libraries

ncdf4 1.16
fields 9.6
dplyr 0.7.8
reshape2 1.4.3
ggplot2 3.1.0
mvtnorm 1.0-8
future.apply 1.0.1
latex2exp 0.4.0
refund 0.1-17
roahd 1.4.1
cowplot 1.0.0
gridExtra 2.3
mapproj 1.2.7
raster 3.0-7
rgdal 1.4-8

## Instructions for Use


### Reproducibility

All tables and figures from the paper and online supplement, except for
the map of proxy locations (right panel of Figure 8) and the correlation
maps (Figure 11). The right panel of Figure 8 and Figure 11 are not
generated based on our statistical analysis.

1.  First set your working directory to **/submitted_code**

2.  Then download the two data files and place them in
    **/submitted_code/data/**

3.  For the simulations (conv, size, power) run sim_xxxx.R to run the
    simulations under the given setting. Then run the plot_xxxx.R or
    table_xxxx.R file to create the associated plot or table. These can
    all be found in the respective conv, size, and power directories.
    These files are used to generate Figures 3, 4, 5, 6 and Table 1.

4.  To create Figures 1, 2, the left panel of 8, and 12 run
    temporal_distribution.R, background_analysis_example.R,
    region_map.R, and arctic_tree_rings.R respectively in the maps
    directory.

5.  To create Figure 7 run global.R and to create Figures 9 and 10 run
    regional.R in the results directory.

6.  The misc folder contains two files for creating Figures 7 and 8 in
    the supplement; FAD_global.R will generate the left panel of Figure
    8 and mean_var_over_time.R will generate all of Figure 7. The
    right panel of Figure 8 is Figure 7 from the main manuscript.

### Replication

1.  Each script, except for the simulations, was tested on a 2017
    MacBook Pro laptop with an Intel Core i5 processor and 8GB of RAM.
    Simulations were run on a cluster running CentOS Linux, but could be
    run on the same laptop.

2.  The analysis and background data files are together 14GB. Each is
    processed sequentially which only requires 30 MB of memory. Expected
    run time of the analysis files is about 5 hours for the global and 5
    hours for the regional.

3.  The upper bound run time of any simulation (size, power,
    convergence) is 4 hours times the total number of parameter
    settings. For most parameter settings the run time is about 2 hours,
    so 4 hours is expected to be the ceiling of the estimated time. It
    is highly recommended that each parameter setting is run in
    parallel, as was done originally on a cluster.


