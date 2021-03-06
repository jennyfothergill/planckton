# PlanckTon
[![test](https://github.com/cmelab/planckton/workflows/pytest/badge.svg)](https://github.com/cmelab/planckton/actions?query=workflow%3Apytest)
[![build_cpu](https://github.com/cmelab/planckton/workflows/build_cpu/badge.svg)](https://github.com/cmelab/planckton/actions?query=workflow%3Abuild_cpu)
[![build_gpu](https://github.com/cmelab/planckton/workflows/build_gpu/badge.svg)](https://github.com/cmelab/planckton/actions?query=workflow%3Abuild_gpu)
[![codecov](https://codecov.io/gh/cmelab/planckton/branch/master/graph/badge.svg?token=5KYVHWMT28)](https://codecov.io/gh/cmelab/planckton/)
[![License](https://img.shields.io/badge/license-GPLv3-green.svg)](LICENSE.md)
[![Contributors](https://img.shields.io/github/contributors-anon/cmelab/planckton.svg?style=flat)](https://github.com/cmelab/planckton/graphs/contributors)

PlanckTon enables exploration of the self-assembly of organic photovoltaic (OPV) compound mixtures under various conditions.
Multiple simulation tools are tied together to reproducibly and accurately generate these structures.
For managing large parameter spaces and submitting jobs to clusters, we recommend [PlanckTon-flow](https://github.com/cmelab/planckton-flow) which leverages the [Signac](https://docs.signac.io/en/latest/) framework.

The simulation tools used by PlanckTon are:

* [**mBuild**](https://github.com/mosdef-hub/mbuild) - builds compounds and initializes simulations

* [**foyer**](https://foyer.mosdef.org/en/stable/) - manages force-field information

* [**HOOMD-blue**](https://hoomd-blue.readthedocs.io/en/latest/) - runs the simulations


## How to use

### Install
#### Using a container
PlanckTon provides containers with HOOMD compiled for cpu or gpu. If your system allows, we recommend gpu.

To use PlanckTon in a prebuilt container (using [Singularity](https://singularity.lbl.gov/)), run:
```bash
singularity pull docker://cmelab/planckton_gpu:latest
singularity exec planckton_gpu_latest.sif bash
```

**Or** using [Docker](https://docs.docker.com/), run:
```bash
docker pull cmelab/planckton_gpu:latest
docker run -it cmelab/planckton_gpu:latest
```

#### Custom install
To create a local environment with [conda](https://docs.conda.io/en/latest/miniconda.html), run:
```bash
conda env create -f environment.yml
conda activate planckton
```
And to test your installation, run:
```
pytest
```

### Run simulations

See example in `planckton/tests/test_sim.py`

## How to Contribute

see [Contributing guide](.github/CONTRIBUTING.md)
