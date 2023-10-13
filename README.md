# qmc_hydrogen
This repository documents the procedure of converting the hydrogen dataset into the HDF5 format.

## Environment Set Up
Before executing the script from this repository, ensure you've installed the following packages. Also, note that the script has only been run on Python 3.12.0
```
ase == 3.22.1
h5py == 3.10.0
numpy == 1.26.0
matplotlib == 3.8.0
ipywidgets == 8.1.1
pythreejs == 2.4.2
```
## Dataset Download
You can obtain the dataset from yt-hub at [this link](https://girder.hub.yt/#folder/5e6d2a7168085e00018c9088). The complete dataset comprises 1594 files.

## HDF5 Structure
This represents the current structure of the HDF5 file generated by the script, and it will evolve as additional data is incorporated.
```
.
.
├── /
├── /f54-hs1
│   ├── pbe-n096-ts0005-p050-t1000.pbe.traj.dmc.traj Dataset {6, 96, 3}
│   ├── pbe-n096-ts0005-p050-t1200.pbe.traj.dmc.traj Dataset {1, 96, 3}
│   ├── pbe-n096-ts0005-p050-t1400.pbe.traj.dmc.traj Dataset {3, 96, 3}
│   ├── ... 
├── /f54-ipc 
│   ├── npt-p175-t1000-b0.dmc_mean.traj Dataset {6, 96, 3}
│   ├── npt-p175-t1200-b0.dmc_mean.traj Dataset {13, 96, 3}
│   ├── npt-p175-t1400-b0.dmc_mean.traj Dataset {21, 96, 3}
│   ├── ... 

```
Note: In each `traj` file, there's a dataset that captures all atomic details. The format, such as (6,93,3), represents the structure of this dataset. Specifically, the first number (6 in this instance) indicates the number of atoms, the subsequent dimensions provide additional atomic data such as: **Atom Positions**

 update: Oct 11, 2023