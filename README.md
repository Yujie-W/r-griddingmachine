# GriddingMachine for R

The package is a simplification of [GriddingMachine.jl](https://github.com/CliMA/GriddingMachine.jl), where a full suite of functions are available.

## Installation and Uninstallation
To install `griddingmachine`, do
```R
library(devtools);
install_github("Yujie-W/r-griddingmachine");
```

To uninstall `griddingmachine`, do
```R
remove.packages("griddingmachine");
```

## API
### update_GM
Update the GriddingMachine.jl artifact library.
```matlab
update_GM();
```

### query_collection
Query the dataset path; if the dataset does not exist, the dataset will be downloaded and unzipped automatically.
```matlab
file_path = query_collection('VCMAX_2X_1Y_V1');
```
The dataset is a NetCDF file with data labeled as `data` and error labeled as `std`.

### request_LUT
Request the data for a given latitude and longitude from the server without downloading the datasets.
```matlab
[vcmax,error] = request_LUT('VCMAX_2X_1Y_V1', 35.1, 115.2);
```
Note that the function also allows for other input variables, including `cyc`, `user`, `interpolation`, `server`, and `port`. For example, if `interpolation` is true, the dataset would be interpolated.
```matlab
[vcmax,error] = request_LUT('VCMAX_2X_1Y_V1', 35.1, 115.2, interpolation = true);
```
