# OHUE-Pycnocline-relationship

This project explores the relationship between ocean stratification and Ocean Heat Uptake Efficiency. The results are described in *Global Pycnocline depth constrains Ocean Heat Uptake Efficiency*.


## How to use codes

Three notebooks are currently included. 

The first two are included to show you how I cleaned up and saved the variables needed for plotting scatter plots of metrics. Specifically: 

**Density_stratifacation_slope.ipynb** reads in and uses temperature and salinity CMIP5 and CMIP6 data to calculate the interior fields used to calculate our metrics. Those are the time-averaged preindustrial: density, buoyancy frequency, and drho/dx and drho/dy gradients used to define the isopycnal slopes. Output is saved as: density_cmip5.nc, density_cmip6.nc, N2_cmip5.nc, N2_cmip6.nc, and drhody_cmip5.nc, drhody_cmip6.nc, drhodz_cmip5.nc, drhodz_cmip6.nc, which are read in and used to plot scatter plots in Plot_metrics.ipynb. 

**heatflux_SST_TAS.ipynb** reads in and calculates all surface fields used to calculate our metrics. Those are the time-averaged ocean heat flux anomaly, sea-surface temperature anomaly, and surface temperature anomaly (currently not used in the paper nor available in MITGCM I think)? Output is saved as OHU_change_cmip5.nc, OHU_change_cmip6.nc, SST_change_cmip5.nc, SST_change_cmip6.nc, and TAS_change_cmip5.nc, TAS_change_cmip6.nc

The above codes use a large amount of raw cmip data that I haven't uploaded because it's so much data. I have instead included the outputs, but can upload raw data if needed. I also expect that the above codes will have to differ for the MITGCM data since you aren't reading in data from different models. They are instead meant to show you how all fields are calculated from the raw interior and surface fields.

Lastly, **Plot_metrics.ipynb** reads in all data reduced in the above codes to calculate all metrics used in the scatter plots of figures 2 and 3 in the paper. To do so, we calculate the global and regional OHUE values, the normalized density metric, and the Southern-Ocean averaged N2 and isopycnal slope.



