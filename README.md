# Use case of SWM for Zarr backend evaluation

## Run use cases
Change to the directory where the respective `model.namelist` file is located.
Start the model using its [docker image](https://hub.docker.com/r/martinclaus/swm):

```bash
docker run --rm --cpuset-cpus=0-3 -v $(pwd):/run martinclaus/swm
```

Note that the `--cpuset-cpus` option binds the container to a set of cores to ensure performance of shared memory computation.
The actual value depends on the machine you are using.

## Use case 1
Spin-up of a subtropical gyre. Input is the single dataset `tau_x.nc[34]` containing zonal wind stress.
The dataset is provided in `NETCDF4` and `NETCDF3_CLASSIC` format.
Output is monthly mean fields of interface displacement.