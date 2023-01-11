# Template Repo for ML Project

This template repo will give you a good starting point for your second project. Besides the files used for creating a virtual environment, you will find a simple example of how to build a simple model in a python script. This is maybe the simplest way to do it. We train a simple model in the jupyter notebook, where we select only some features and do minimal cleaning. The output is then stored in simple python scripts.

The data used for this is: [coffee quality dataset](https://github.com/jldbc/coffee-quality-database).

---
## Requirements and Environment

Requirements:
- pyenv with Python: 3.9.8

Environment: 

We have to install hdf5 for DNN:

```BASH
 brew install hdf5
 brew install graphviz
```

For installing the virtual environment you can either use the Makefile and run `make setup` or install it manually with the following commands: 

```Bash
pyenv local 3.9.8
python -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

## Usage

In order to train the model and store test data in the data folder and the model in models run:

```bash
#activate env
source .venv/bin/activate

python example_files/train.py  
```

In order to test that predict works on a test set you created run:

```bash
python example_files/predict.py models/linear_regression_model.sav data/X_test.csv data/y_test.csv
```
If you already have hdf5
```BASH
export HDF5_DIR=/opt/homebrew/Cellar/hdf5/1.12.2
```
otherwise, if you have just installed hdf5 with brew, then
```BASH
export HDF5_DIR=/opt/homebrew/Cellar/hdf5/1.12.2_2
```

```BASH
pip install -U pip
pip install --no-binary=h5py h5py
pip install -r requirements.txt
```

## Limitations

Development libraries are part of the production environment, normally these would be separate as the production code should be as slim as possible.
