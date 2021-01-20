# PlanckTon
[![CI](https://github.com/cmelab/planckton/workflows/CI/badge.svg?branch=master)](https://github.com/cmelab/planckton/actions?query=workflow%3ACI) 
[![codecov](https://codecov.io/gh/cmelab/planckton/branch/master/graph/badge.svg?token=5KYVHWMT28)](https://codecov.io/gh/cmelab/planckton/)
[![License](https://img.shields.io/badge/license-GPLv3-green.svg)](LICENSE.md)
[![Contributors](https://img.shields.io/github/contributors-anon/cmelab/planckton.svg?style=flat)](https://github.com/cmelab/planckton/graphs/contributors)

PlanckTon enables exploration of the self-assembly and charge transport for mixtures of organic photovoltaic compounds under various conditions.
To conduct these parameter sweeps, multiple simulation tools are tied together to reproducibly and accurately generate these structures.

The simulation tools used by PlanckTon are:

* [**mBuild**](https://github.com/mosdef-hub/mbuild) - builds compounds and initializes simulations

* [**foyer**](https://foyer.mosdef.org/en/stable/) - manages force-field information

* [**HOOMD-blue**](https://hoomd-blue.readthedocs.io/en/latest/) - runs the simulations

* [**signac**](https://signac.io/) - manages and organizes the many variables that are run

* [**signac-flow**](https://docs.signac.io/projects/flow/en/stable/) - manages workflows

## How to use

### Install
#### Using a container
To use PlanckTon in a prebuilt container (using [Singularity](https://singularity.lbl.gov/)), run:
```
singularity pull docker://cmelab/planckton_cpu:0.1.4
singularity exec planckton_cpu_0.1.4.sif bash
```
You may need to also run:
```
conda init bash
conda activate planckton
```

**Or** using [Docker](https://docs.docker.com/), run:
```
docker pull cmelab/planckton_cpu:0.1.4
docker run -it cmelab/planckton_cpu:0.1.4
```

#### Custom install
To create a local environment with [conda](https://docs.conda.io/en/latest/miniconda.html), run:
```
conda env create -f environment.yml
conda activate planckton
pytest
```

### Run simulations

See example in `tests/test_sim.py`

Also see [planckton-flow](https://github.com/cmelab/planckton-flow)

## How to develop

* Fork and clone this repo ([how to make a fork](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/fork-a-repo))
* Add this repository as upstream `git remote add upstream git@github.com:cmelab/planckton.git`
* Modify the code and push to your fork
* Submit a pull request (PR) ([how to create a PR](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork))
