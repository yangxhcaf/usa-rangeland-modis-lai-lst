# MODIS Processing for US Drylands

Calculate monthly and yearly mean, standard deviation, maximum, minimum, amplitude, and integral for MODIS time series of 4-day composite LAI (MCD15A3H) and daily daytime and nighttime LST from both Terra (MOD11A2) and Aqua (MYD11A2)

## Inputs
Inputs are netCDF4 format outputs from APPEEARS (https://lpdaacsvc.cr.usgs.gov/appeears/). Request the input data for this analysis using the following JSON strings:
4-day composite Leaf Area Index (and QC datasets from MCD15A3H

## Outputs
### CSV
### NetCDF
### GeoTIFF
**LST Terra:**
Day Monthly (12/year)
Day Yearly (1/year)
Night Monthly (12/year)
Night Yearly (1/year)
**LST Aqua:**
Day Monthly (12/year)
Day Yearly (1/year)
Night Monthly (12/year)
Night Yearly (1/year)
**LAI Combined:**
Monthly (12/year)
Yearly (1/year)

# Aridity index
[https://www.gdal.org/ogr2ogr.html]
```
$ ogr2ogr -t_srs "+proj=sinu +lon_0=0 +x_0=0 +y_0=0 +a=6371007.181 +b=6371007.181 +units=m +no_defs " ai-drylands-sinu.shp  ai-drylands.shp
```

# Testing
```
/<path_to_nco>/nco/ncks -d time,1,8 MCD15A3H.006_500m_aid0001.nc -O MCD15A3H.006_500m_aid0001_short.nc
/<path_to_nco>/nco/ncks -d time,1,29 MOD11A1.006_1km_aid0001.nc -O MOD11A1.006_1km_aid0001_short.nc
/<path_to_nco>/nco/ncks -d time,1,29 MYD11A1.006_1km_aid0001.nc -O MYD11A1.006_1km_aid0001_short.nc
```


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI0NjMwMjc2NywtMTYyMTg3MTQyNywtOT
A0NDM2NzU2XX0=
-->