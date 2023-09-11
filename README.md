# autocalibration
 parameter estimation and automatic calibration

## dependencies

* optuna: for optimization
* modelskill: for evaluation of model skill
* mikeio: for altering roughness map and pfs

dependencies are included in the autocalibration environment.

 ## structure

* data: folder where model data and observations to calibrate to reside. 
    * Example_Corner: data for simple test case from MIKE FM HD examples "BedResistance". Added 
* notebooks: folder with jupyter notebooks 
    * example_corner: simple test case for FM HD where bed resistance map with two zones is modified 


## workflow for modification of roughness map

* run simulation with "base" roughness
* evaluate model vs. observation (modelskill)
    * objective: optimize water level at two points
    * metric: RMSE, CC
* adjust roughness map (mikeio)
    * read template roughness map
    * identify zones based on values in template
    * alter roughness in zones
* start from beginning with altered roughness map and repeat
 