# Tobac Roadmap

## Overarching Goal
*tobac* is a scientific Python package for detecting, tracking, and analyzing atmospheric phenomena. In contrast to existing cloud tracking schemes which are commonly designed to be used with specific data types and applications, *tobac* aims to be simpler, modular, and a more general toolset for cloud tracking.


`tobac` aims to be:

* Open: open-source code with a permissive license, developed with an open, multi-institutional international community, and built from the ground up in support of open science
* Maintainable: easy to maintain and add new features
* Modular: abstracting the key steps of feature tracking
* Flexible: capable of using a broad range of heterogeneous data sources
* Multi-purpose: tracking phenomena evident in satellite and  radar observations and within output from climate, k-scale and LES models
* A framework: establishing a standard data model across identification and tracking methodologies
* Extensible: able to add new identification and tracking methodologies without a substantial revision to the core

## Structure of *tobac*
### Modular Framework

The modular framework of *tobac* was designed by Max Heikenfeld as part of the original release  (Heikenfeld et al., 2019; https://doi.org/10.5194/gmd-12-4551-2019). Essential extensions of *tobac* are documented in Sokolowsky, Freeman et al. (2023;  https://doi.org/10.5194/egusphere-2023-1722).  

The elements of tobac are laid out as the following:
* Data input and output
* Data filtering 
* Feature detection
* Segmentation of cloud areas and volumes
* Trajectory linking
* Object-based analysis and visualization

Many existing tracking methods can be described as 'grey-box' models, utilizing internal parameters whose effects may be unclear to the user. tobac aims to be a modular collection of ‘clear-box' methodologies whose operations are clear to the user and whose parameters are all user-set. As a result, tobac can support multiple data types, applications, and workflows through the mix and match of multiple modular components.

The modular components of tobac are not restricted to the elements listed above. Instead, they support a diverse range of applications and methodologies. Modules are defined not by their internal structure, but by the data structures through which they interface with other modules. This allows a variety of modules not necessarily confined to those listed above, for example, a module that carries out both feature detection and segmentation, or a refinement module that takes an existing linked trajectory and returns an extended trajectory.



## Development Goals and Future Vision
### 1-Year Goals [2024]
* Implement xarray throughout the package, sunsetting our use of Iris
* Improve the modularity of the package, moving more code to within function calls. 
* Re-integrate the tobac-tutorials repository (https://github.com/tobac-project/tobac-tutorials) into the main tobac repository
  - Add an example gallery with clear graphics to our read the docs page 
  - Add examples for global tracking 
* Basic Dask support
  - Example using Dask across time values in the documentation
* Sustained governance within the group, including the establishment of a steering committee with regular meetings
* Increase our developer group size


### 3 Year Goals [2026]
* Enable tracking on multiple variables simultaneously
* Inclusion of more methodologies and modules in each step of the process, with at least one new method in each step to demonstrate and exercise the flexibility of the modular architecture
* Build a framework to compare methodologies and modules within tobac
  - Have standardized data to compare methodologies
* Increase the sustainability of development
* Add in an initial framework and experiments into non-cartesian grids, including: 
  - The addition of Cube sphere grid support
* Implement a sustainable framework within tobac, including well-defined data models


### 5 Year Goals [2028]
* Full Dask support for all functions
* Ability to decompose the domain for feature detection and segmentation methodologies
* Full unstructured grid support
* Increased users



## References

Heikenfeld, M., P. J. Marinescu, M. Christensen, D. Watson-Parris, F. Senf, S. C. van den Heever, and P. Stier, 2019: tobac 1.2: towards a flexible framework for tracking and analysis of clouds in diverse datasets. Geosci. Model Dev., 12, 4551–4570, doi:10.5194/gmd-12-4551-2019.

Sokolowsky, G. A., Freeman, S. W., Jones, W., Kukulies, J., Senf, F., Marinescu, P. J., Heikenfeld, M., Brunner, K., Bruning, E., Collis, S., Jackson, R., Leung, G., Pfeifer, N., Raut, B., Saleeby, S., Stier, P., & van den Heever, S. C. (2023). tobac v1.5: Introducing Fast 3D Tracking, Splits and Mergers, and Other Enhancements for Identifying and Analysing Meteorological Phenomena, EGUsphere [preprint], https://doi.org/10.5194/egusphere-2023-1722

   

        



            
