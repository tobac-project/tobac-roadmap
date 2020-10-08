# Tobac Roadmap

## Overarching goal
`tobac` is a scientific python package. It aims to help researchers in the identifications and tracking of clouds and precipitation areas. In contrast to existing nowcasting schemes which appear to very sophistcated and highly adjusted to certain data types, `tobac` implement a simpler, but more general approach.

`tobac` has the objectives to be an

* Open-Source python package for everybody without cumbersome licence restriction and commercial interests
* Easy-to-Use modular package system
* Flexible framework for exploratory data analysis in cloud and precipitation research
* Robust interface to existing modern Python tools (like `xarray`, `scipy`, `scikit-image`, `trackpy`)


## Research Applications
Using `tobac` in the following research applications might be beneficial:  

* Lagrangian analysis in a moving frame: Applicable to observations and simulations
  * Process-based assessment of cloud and precipitation formation in NWP (Numerical Weather Prediction) models
  * Object-based model evaluation – Distributions of cloud sizes and lifetimes
* Spatial and structural analysis of cloud and precipitation fields 
  * Climate impact of convective organization
* Tracking of cloud and precipitation cells for monitoring or nowcasting purposes


## Structure of `tobac`: Themes
Tobac themes: end-to-end processes to rapidly include new methods within tobac. E.g. tobac v1.

Themes could become submodules.

Note that we need to highlight that themes should not be completely separate from each other. Eventually themes should be worked into methods with common, defined interfaces, allowing users to “mix and match”.

**currently existing themes**
* Tobac_v1

**planned extensions**
* Fabian Senf’s subsegmentation work

* TINT

* Will Jones’ optical flow detection and tracking (tobac-flow, may be an external package)


## Definition of Data Interfaces

It is planned to build and extend `tobac` using a fully modular structure. Handling different modules (parts of the `tobac` workflow) in an exchangeble manner is only possible if data interfaces are well defined. `tobac` needs to be built common interfaces with common data formats, so that different methods can be used together.

### General Aspects

* data should be loaded and handled using xarray datasets/dataarrays

* netcdf should be the main output format, especially as future inclusion of zarr/memmap in netcdf standard should substantial improve performance

* all modules within `tobac` require a minimal set of input data

### Gridded Input Data

The `tobac` workflow starts with a set of gridded data that might be input from various sources. The input fields should be either loaded by `xarray` functionality or should be converted into `xarray.Dataset` after input.

**for feature detection**   
An `xarray.DataArray` should be supplied to the feature detection modules. This `DataArray` should hold information on time and geo-spatial reference.

Currently, the user is responsible to combine multi-variate fields (e.g. from several satellite channels) into one resulting field for which thresholding and feature detection is done. 

*Caveat*: Feature detection schemes of `tobac_v1` use `iris.Cube`s in their internal data handling. Conversion to from `xarray.DaraArray`s to  `iris.Cube`s is done internally, but fails if input data specifications do not fit with the `iris` requirements. This is too strick and these contrains need to be relaxed.

 
### Object and Trajectory Data

**detected and tracked features**   
Feature detections and tracking output data in a tabular form. These data should be stored in `xarray.Dataset`s. A consecutive numbering of features might be sufficient for a unique identification of each feature. Information on timing, location, magnitude, and association to tracks can be used for grouping of features and dedicated analysis.

*Split-and-Merge Morphology*: A new hierarchical data format, which captures non-linear relationships between sets of daughter and mother cells, needs to be tested for handling merging and splitting of tracked objects. A cf-compliant data structre would be a major advantage for tobac. It remains open how to best use cf-tree metadata  (Eric Bruning)

*Association with Networks*: In general, features might be interpreted as nodes of a network and tracks are a certain and unique realization of connections between nodes at different times. Interconnections between nodes (in time and space), the edges in the network, can build a rather complex web. A data format might be needed to store informations on these interconnection (e.g. the overlap between cells).

## Future Contributions

### Priorities
* a flexible input interface that allows to start feature detection and the rest of the `tobac` workflow with a minimum of requirements on the input data



### What feature requests should be within the scope of tobac?

Caution: need to be selective about what themes are included. Initially limit to specific packages:


        

   

        



            
