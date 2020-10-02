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

Define what should be within an individual package, vs what should be external packages

### Formats

* Need to build tobac around common interfaces with common data formats, so that different methods can be used together

* Data should be loaded and handled using xarray datasets/dataarrays

* Netcdf likely to be main save format, especially as future inclusion of zarr/memmap in netcdf standard should substantial improve performance

* Eric Bruning’s new hierarchical data format to be used to handle merging and splitting of tracked objects -- this would be a major advantage for tobac. Need to work out how to best use cf-tree metadata

## Future Contributions

### What feature requests should be within the scope of tobac?

Caution: need to be selective about what themes are included. Initially limit to specific packages:


        

   

        



            
