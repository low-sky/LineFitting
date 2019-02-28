# LineFitting
Tests of line fitting algorithms, with a focus on different strategies for multicomponent fitting. Description of key routines:

* `nh3_testcubes.py` -- Create a set of test cubes for running multicomponet fitting tests on (see "GAS Test Cubes" below for more details).


## GAS Test Cubes
A test set of 10,000 cubes are generated via `nh3_testcubes.py` for a benchmark comparison between different line-fitting algorithms. A synthetic ammonia spectrum modelled by either one or two velocity slabs is generated at the central pixel of each test cube. The remainder pixels in the cube are filled with models nearly identical to that of the center pixel, differ only by a small velocity offset for individual velocity slabs.

### Distributions of the Test Set Parameters
The physical parameters used to generate the test cubes are randomly drawn from the following distributions for each velocity slap:
* Velocity centroid:
  - First slab: uniformly distributed in the range of `[-2.5, 2.5)` km s<sup>-1</sup>.
  - Second slab: uniformly distributed in the range of `[-2.5, 2.5)` km s<sup>-1</sup>, **with respect to** velocity centroid of the first slab.
* Linewidth:
  - Quadrature-sum of the thermal and the non-thermal linewidths
  - Thermal linewidth: `0.08` km s<sup>-1</sup>
  - Non-thermal linewidth: uniformly distributed in the natural log space in the range of `[0.1, 1.6)` log(km s<sup>-1</sup>)
* Column Density:
  - Uniformly distributed in the log<sub>10</sub> space in the range of `[13, 14,5)` log(cm<sup>-2</sup>).
* Kinetic temperature:
  - Uniform distribution in the range of `[8, 25)` K

