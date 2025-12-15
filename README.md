# Installation environnement python

We highly recommend you to follow these steps, it will allow every student to work in an environment as similar as possible to the one used during testing.

## 1. Uv installation


https://docs.astral.sh/uv/getting-started/installation/


`curl -LsSf https://astral.sh/uv/install.sh | sh`

Python version 3.12 installation (highly recommended)
`uv python install 3.12`

## 2. R installation (needed for data download/pre-processing from TD2)

In the command `Rscript` says 'command not found'

`sudo apt install r-base-core`

## 3. Python env creation

```
mkdir TD_bias_mitigation
cd TD_bias_mitigation
uv python pin 3.12
uv init
uv venv
uv pip install numpy fairlearn plotly nbformat ipykernel aif360["inFairness"] aif360['AdversarialDebiasing'] causal-learn BlackBoxAuditing cvxpy dice-ml lime shapkit
```

## 4. Download MEPS dataset

```
cd .venv/lib/python3.12/site-packages/aif360/data/raw/meps/
Rscript generate_data.R
```