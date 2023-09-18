# OHUE-Pycnocline-relationship

This project explores the relationship between ocean stratification and Ocean Heat Uptake Efficiency. The results are described in *Global Pycnocline depth constrains Ocean Heat Uptake Efficiency*.


## How to use codes

Three notebooks are currently included to be ammended to include data from the MITGCM and add it to the scatter plots in Figs. 2-3. 

The first two notebooks are included to show you how I cleaned up and saved the variables needed for plotting scatter plots of metrics. Specifically: 

**Density_stratifacation_slope.ipynb** reads in and uses raw temperature and salinity CMIP5 and CMIP6 data to calculate the interior fields used to calculate our metrics. Those are the time-averaged preindustrial: density, buoyancy frequency, and drho/dx and drho/dy gradients used to define the isopycnal slopes. Output is saved as: density_cmip5.nc, density_cmip6.nc, N2_cmip5.nc, N2_cmip6.nc, and drhody_cmip5.nc, drhody_cmip6.nc, drhodz_cmip5.nc, drhodz_cmip6.nc, which are read in and used to plot scatter plots in Plot_metrics.ipynb. 

**heatflux_SST_TAS.ipynb** reads in and calculates all surface fields used to calculate our metrics. Those are the time-averaged ocean heat flux anomaly, sea-surface temperature anomaly, and surface temperature anomaly (currently not used in the paper nor available in MITGCM I think)? Output is saved as OHU_change_cmip5.nc, OHU_change_cmip6.nc, SST_change_cmip5.nc, SST_change_cmip6.nc, and TAS_change_cmip5.nc, TAS_change_cmip6.nc

Raw CMIP data (used in the Density_stratifacation_slope.ipynb, heatflux_SST_TAS.ipynb) is available for download at https://esgf-node.llnl.gov/search/cmip6/ and https://esgf-node.llnl.gov/search/cmip5/, respectively

Lastly, **Plot_metrics_GRL.ipynb** reads in all output from the above two notebooks to calculate all the metrics cited in the paper. To do so, we calculate the global and regional OHUE values, the normalized density metric, and the Southern-Ocean averaged N2 and isopycnal slope. Included is also code to test the sentitivity of the OHUE-pycnocline relationship for several other pycnocline metrics.



