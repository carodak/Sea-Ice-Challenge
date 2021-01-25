# Sea-Ice-Challenge
AILaunchLab Hackaton gave us the opportunity to quickly compile a model that could predict sea-ice movement

```
The data are not provided here since it is big and confidential! :P
```

## Challenge
Arctic sea ice drifts under the influence of winds and ocean currents. Ice motion is important - up to several kilometers a day. Tracking the movement of sea ice can be applied to different research questions, including the transition from older sea ice to a younger seasonal ice pack, the transport of ice-rafted sediments, or pollutants in the context of an oil spill, and the risk assessment associated with navigation and marine operations in the Arctic.

## Summary
Basically, we want to track the movement of the ice. To track the ice movement, we need the ice velocity. To predict ice velocity, we have information (features) related to winds and the environment. We are given a formula (free drift of sea ice) if we want to combine some features to have less features. 
And of course we cannot use the information at t+1 to predict the velocity at time t (in real life we don’t have information from the future).

## Data
year, month, day, doy, x_EASE, y_EASE, u_buoy, v_buoy, id_buoy, u_ERA5, v_ERA5, sic_CDR, h_cs2smos, h_piomas, d2c

- year: year
- month: month
- day: day in the month
- doy: day-of-year
- x_EASE: x_position of the daily buoy drift estimate
- y_EASE: y_position of the daily buoy drift estimate
- id_buoy : numerical buoy identifier
- u_buoy: u-component of the sea ice velocity (x direction in cm/s)
- v_buoy: v-component of the sea ice velocity (y direction in cm/s)
- u_ERA5: u-component of the wind (x direction in m/s) obtained from the ERA5 reanalysis dataset
- v_ERA5: v-component of the wind (x direction in m/s) obtained from the ERA5 reanalysis dataset
- sic_CDR: sea ice concentration in '%' obtained from NSIDCClDR
- h_piomas: sea ice thickness from PIOMAS
- h_CS2SMOS: sea ice thickness obtained from Cryosat-2 / SMOS
- d2c: distance to coast, warning: interaction of sea ice with coastlines is challenging to represent in models

### Constraints:
id_buoy: can not be used for the prediction

## Objective
Predict u_buoy, v_buoy with u_ERA5, v_ERA5 and any other feature we consider relevant

## Results
Best regressor model (RandomForest): 15 MSE with our CV method.
We submitted a prediction file for the test set.
