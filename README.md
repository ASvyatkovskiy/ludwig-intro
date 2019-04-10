# Ludwig? Who is Ludwig 

Hands-on introduction to Ludwig: materials for the reading group presentation. 

Ludwig is a Python tool for code-free deep learning. More details can be found on [Ludwig GitHub](https://github.com/uber/ludwig) and the [official Ludwig website](https://uber.github.io/ludwig/user_guide)

# Getting started
To follow the tutorial exercises, one needs a laptop with Miniconda (a minimal version of Anaconda) and Ludwig installed.

## Download and install Miniconda
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

## Check-out the git repository with the exercise
Once Miniconda is ready, checkout the tutorial repo and proceed with setting up the environment:
```bash
git clone https://github.com/ASvyatkovskiy/ludwig-intro
```

## Create isolated Miniconda environment

Copy following into a file named `environment.yaml`:

```yaml
name: hello-ludwig
channels:
  - conda-forge
dependencies:
  - python=3.6
  - ludwig
  - jupyter
```

Change into the course folder, then type:

```bash
#cd pytorch-intro
conda env create -f environment.yml
source activate hello-ludwig
```

## Enable anaconda kernel in Jupyter
To make newly created miniconda environment visible in the Jupyter, you might need to install `ipykernel`:

```bash
#source activate hello-pytorch
python -m ipykernel install --user --name hello-ludwig --display-name "Hello, Ludwig!"
```

## Start jupyter notebook
If working on a laptop, start from terminal as usual:

```bash
jupyter notebook
```
In the upper rigt corner, check that you are indeed using the "Hello, Ludwig!" kernel. If not, change to it from the dropdown menu under "Kernels"
