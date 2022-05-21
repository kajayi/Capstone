# KA_Capstone
==============================

Capstone project for General Assembly DSI-Flex-1116

Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>




# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Capstone: Prediction Drug Cardiotoxicity

## Kehinde Ajayi, Ph.D.

## Contents:
- [Problem Statement](#Problem-Statement)
- [EXECUTIVE SUMMARY](#Summary)
- [Methods and Tools](#Methodology)
- [Findings and Observations](#Findings-and-Observations)

- [Best Models](#Best-Models)
- [Next Steps](#Next-Steps)
- [Conclusions](#Conclusions)
- [References](#References)




### Problem Statement
A pharmaceutical company (currently in stealth mode) wants to reduce the costs of new drugs by at least 25% over the next 3 years. To that end, I want to predict the cardiotoxicity of candidate compounds in advance of synthesizing them, thereby avoiding wasting resources on unproductive development.

### Introduction
Drug Discovery is a 
For patients, new medicines offer fewer side effects, fewer hospitalizations, improved quality of life, increased productivity, and importantly, extended lives. Developing medicines is a long, complex process. On average, it takes ___at least ten years___ for a new medicine to complete the journey from initial discovery to the marketplace, with clinical trials alone taking six to seven years on average. The average cost to research and develop each successful drug is estimated to be __$2.6 billion__[1]. This number incorporates the cost of failures – of the thousands and sometimes millions of compounds that may be screened and assessed early in the R&D process, only a few of which will ultimately receive approval. _The overall probability of clinical success (the likelihood that a drug entering clinical testing will eventually be approved) is estimated to be less than 12%_. 

One of the reasons drugs fail in the clinic is because they exhibit unwanted and often serious side effects.  For example, the unintended and often promiscous inhibition of the cardiac human Ether-à-go-go related gene (hERG) potassium channel is a common cause for either delay or removal of therapeutic compounds from development and withdrawal of marketed drugs.[2] The clinical manifestion is prolongation of the duration between QRS complex and T-wave measured by surface electrocardiogram (ECG)—hence Long QT Syndrome. Machine learning techniques may be useful for predicting the level of hERG activity of a compound before money is spent on its development into a drug.

### Dataset information

 The hERGCentral (www.hergcentral.org) is mainly based on experimental data obtained from a primary screen by electrophysiology against  300,000 structurally diverse compounds. The system is aimed to display and combine three resources: primary electrophysiological data, literature, as well as online reports and chemical library collections.


### Methods and Tools

- [Pandas](https://pandas.pydata.org/pandas-docs/stable/index.html)
- [Tensorflow]()
- [Rdkit](https://www.rdkit.org/docs/index.html) – for handling chemical structures and information
- [DeepChem](https://deepchem.readthedocs.io/en/latest/index.html) – for implementing ML models on chemical datasets 
- [Google Cloud Compute](https://cloud.google.com/compute) – for much-needed resources

Rdkit was used to 



### Findings and Observations

A dataset containing 


### Results

The results showed that 
|          Features          	| Validation MCC 	| Validation accuracy 	|
|--------------------	|----------------	|---------------------	|
| No Structure - calculated variables only       	| 0.0            	| 0.955               	|
| ECFP fingerprints[5]  	| 0.456          	| 0.962               	|
| Graph convolutions[6]	| 0.516          	| 0.959               	|


### Next Steps

- Run tokenized SMILES strings through MLP
- Combine embeddings from SMILES, fingerprints, and graph convolutions in transfer learning models
- Cluster compounds and evaluate performance on each cluster
- Use an explanation technique (e.g., LIME, SHAP, Grad-CAM) to update the conventional wisdom
- Explore 3-D representations
- Incorporate into a generative model

### Conclusions 
- Drug discovery is a massive multi-parameter optimization problem that lends itself to various machine learning techniques
- The representation of chemical compounds can greatly affect the performance of machine learning models - graphs are particularly attractive solutions
- The quality and quantity of (publicly available) data are still major sources of contention – GIGO is particularly applicable to drug discovery
- In silico drug discovery is very resource-intensive


### References

[1]http://phrma-docs.phrma.org/sites/default/files/pdf/rd_brochure_022307.pdf

[2]https://www.cambridgemedchemconsulting.com/resources/herg_activity.html

[2]https://www.nature.com/articles/aps2015143

[3]https://pubmed.ncbi.nlm.nih.gov/22149888/

[4]http://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py_ml/py_kmeans/py_kmeans_opencv/py_kmeans_opencv.html

[5]https://pubs.acs.org/doi/10.1021/ci100050t

[6]https://arxiv.org/abs/1509.09292


