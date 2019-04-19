# Getting to know Ludwig

Ludwig is a Python tool for code-free deep learning. 

1. [Official Ludwig GitHub](https://github.com/uber/ludwig)
1. [Official Ludwig website](https://uber.github.io/ludwig/)

# Getting started
To follow, one needs a laptop with Miniconda (a minimal version of Anaconda) and Ludwig installed.

## Downloading and installing Miniconda
Please go to the [Anaconda website](https://conda.io/miniconda.html).
Download and install *the latest* Miniconda version for *Python* 3.6 for your operating system.

```bash
wget <http:// link to miniconda>
sh <miniconda .sh>
```

After that, type:
```bash
conda --help
```


## Create isolated Miniconda environment

Copy following into a file named `environment.yaml`:

```yaml
name: hello-ludwig
channels:
  - conda-forge
dependencies:
  - python=3.6
  - pip:
    - ludwig
    - jupyter
```

then do:

```bash
conda env create -f environment.yml
source activate hello-ludwig
```

### Enable Miniconda kernel in Jupyter

To make newly created miniconda environment visible in the Jupyter, install ipykernel:

```bash
python -m ipykernel install --user --name hello-ludwig --display-name "Hello, Ludwig"
```

## Read official Ludwig user guide

https://uber.github.io/ludwig/user_guide/

We will be looking into *text classification* and *time series forecasting* examples closely 
following https://uber.github.io/ludwig/examples/

#export KMP_DUPLICATE_LIB_OK=True
