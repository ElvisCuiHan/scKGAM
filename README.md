[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg )](https://raw.githubusercontent.com/ljvmiranda921/pyswarms/master/LICENSE)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/ambv/black)

# scBCM: Single-cell Bell Shape Curve Model

**scBCM** is the abbreviation for *Single-cell Bell Shape Curve Model*. This is a Python package for modeling the statistical relationship between pseudotime and gene expression data.

It is intended for bioinformatic scientists, applied statisticians, and students who prefer using Metaheuristic algorithms in solving their own bioinformatic optimization problems. scBCM is able to provide various marginal gene distributions with interpretable regression functions. Check out more features!

* **Free software:** MIT license
* **Documentation:** https://test.pypi.org/project/scBCM/0.2/.
* **Python versions:** 3.5 and above

## Installation

To install scBCM, run this command in your terminal:

```shell
$ pip install -i https://test.pypi.org/simple/ scBCM==0.3
```

This is the preferred method to install scBCM. In case you want to install the bleeding-edge version, clone this repo:

```shell
$ git clone -b development https://github.com/ElvisCuiHan/scBCM.git
```
and then run

```shell
$ cd scBCM
$ python setup.py install
```

## Usage

scBCM provides a high-level implementation of various marginal distributions including Poisson, negative binomial (NB), zero-inflated Poisson (ZIP) and zero-inflatd negative binomial (ZINB). Further, it utilizes particle swarm optimization algorithm in the package ***pyswarms*** to optimize the objective function. Thus, it aims to be user-friendly and customizable.

You can import scBCM as any other Python module,

```python
import pyswarms as ps
```

The data should be a cell-by-gene matrix where the first column corresponding to the pseudotime:
```math
Index Pseudotime Gene1 Gene2 ...
1.    t1         y11   y12   ...
2.    t2         y21   y22   ... 
3.    t3         y31   y32   ...
4.    t4         y41   y42   ...
```

### All-in-one function

Suppose we want to regress Gene 1 on pseudotime using the Bell-shape Curve Model, simply we call the **main** function:

```python
 main(gene_index = 1, marginal="ZIP", iter=50, data_dir=YouDataPath, save_dir=YouTargetPath)
```

Note the data should be in *.csv* format. The **main** function will return a *.json* file and *.png* figure. 

### Example

The following figure has shown a typical output by the **main** function in `BellShapeModel.py`.

![plot](https://github.com/ElvisCuiHan/scBCM/blob/main/Figures/100ZIP.png?raw=true)
