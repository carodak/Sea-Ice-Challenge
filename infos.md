## Challenge
Basically, we want to track the movement of the ice. To track the ice movement, we need the ice velocity. To predict ice velocity, we have information (features) related to winds and the environment. We are given a formula (free drift of sea ice​) if we want to combine some features to have less features. 
And of course we cannot use the information at t+1 to predict the velocity at time t (in real life we don’t have information from the future).

## Data
year, month, day, doy, x_EASE, y_EASE, u_buoy, v_buoy, id_buoy, u_ERA5, v_ERA5, sic_CDR, h_cs2smos, h_piomas, d2c

year: year
month: month
day: day in the month
doy: day-of-year
x_EASE: x_position of the daily buoy drift estimate
y_EASE: y_position of the daily buoy drift estimate
u_buoy: u-component of the sea ice velocity (x direction in cm/s)
v_buoy: v-component of the sea ice velocity (y direction in cm/s)
u_ERA5: u-component of the wind (x direction in m/s) obtained from the ERA5 reanalysis dataset (Reliability?)
v_ERA5: v-component of the wind (x direction in m/s) obtained from the ERA5 reanalysis dataset (Reliability?)
sic_CDR: sea ice concentration in '%' obtained from ​NSIDCClDR (Reliability?)
h_piomas: sea ice thickness from PIOMAS​ (Reliability?)

### Eliminated data
h_CS2SMOS ​: ​sea ice thickness obtained from Cryosat-2 / SMOS​ (Reliability?) (not continious data so eliminated)
id_buoy : ​numerical buoy identifier
d2c​: ​distance to coast, warning: interaction of sea ice with coastlines is challenging to represent in models

## Objective
Predict u_buoy, v_buoy with u_ERA5, v_ERA5 and any other relevant features we select?

## Features
x_EASE: x_position of the daily buoy drift estimate
y_EASE: y_position of the daily buoy drift estimate
u_ERA5: u-component of the wind (x direction in m/s) obtained from the ERA5 reanalysis dataset (Reliability?)
v_ERA5: v-component of the wind (x direction in m/s) obtained from the ERA5 reanalysis dataset (Reliability?)
sic_CDR: ​sea ice concentration in '%' obtained from ​NSIDCClDR (Reliability?)
h_piomas: ​sea ice thickness from PIOMAS​ (Reliability?)

d2c​: ​distance to coast, warning: interaction of sea ice with coastlines is challenging to represent in models
