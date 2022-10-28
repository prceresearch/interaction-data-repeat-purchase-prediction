# Effect of low-level interaction data in repeat purchase prediction task

## About

This is the official repository for the *Effect of low-level interaction data in repeat purchase prediction task* research paper. The work concerns the task of repeat purchase prediction in the ecommerce domain. The repository contains basic information about the three anonymized datasets, which were collected as part of our work, alongside used Python scripts, enabling the reproduction of the data preprocessing as well as model evaluation steps. Figures containing extended evaluation results are also included. The authors may be contacted using the [contact information below](#a-authors) or prce.research([AT])gmail.com.

#### Table of Contents
* [Paper Citation](#a-citation)
* [Datasets](#a-datasets)
* [User Model - Full List of Features](#a-um-features)
* [Scripts](#a-scripts)
* [Results](#a-results)
* [Authors](#a-authors)
* [Licence](#a-licence)

## <a name="a-citation"> Paper Citation
[Place for a bibtex-format paper citation]

## <a name="a-datasets"> Dataset
As part of our work, we collected three new datasets containing interaction and non-interaction data from three real-world ecommerce stores - Dataset H ([Herbatica](https://www.herbatica.sk)), Dataset P ([Particle Peptides](https://particlepeptides.com/sk/)) and Dataset B ([Barefootky](https://www.barefootky.sk)). The data were collected using the [UXtweak](https://www.uxtweak.com) tool within one year and range from June 2nd, 2020 to June 1st, 2021. The collected data is organized into user sessions, comprising of low-level interaction events (such as mouse clicks and movements), non-interaction data (such as geolocation and temporal data) as well as the raw representation of the website's DOM. Each session belongs to a specific user and contains an anonymous identifier, which makes it possible to track repeat purchases for a user over a sequence of sessions.

### Detailed statistics for Dataset H, Dataset P and Dataset B
<p align="center">
  <a href="figures/Dataset%20Statistics.png"><img style="width: 100%; height: 100%;" src="figures/Dataset%20Statistics.png" alt="Detailed statistics for Dataset H, Dataset P and Dataset B"/></a>
</p>

<p align="center">Detailed statistics for Dataset H, Dataset P and Dataset B. <a href="figures/Dataset%20Statistics.html">Source Table in HTML.</a></p>  
  
### Dataset Access  
**To access the dataset, please contact the authors at prce.research([AT])gmail.com**.

## <a name="a-um-features"> User Model - Full List of Features
<p align="center">
  <a href="figures/List%20of%20constructed%20features.png"><img style="width: 100%; height: 100%;" src="figures/List%20of%20constructed%20features.png" alt="List of constructed features belonging to categories of Generic interaction (Ig), Ecommerce-related interaction (Ie) and Non-interaction (N) features"/></a>
</p>

<p align="center">List of constructed features belonging to categories of Generic interaction (Ig), Ecommerce-related interaction (Ie) and Non-interaction (N) features, respectively. <a href="figures/List%20of%20constructed%20features.html">Source Table in HTML.</a></p>
  
## <a name="a-scripts"> Scripts

The scripts are provided as Jupyter notebooks and describe individual steps of the solution workflow. Below is a complete list of the scripts, alongside a brief explanation for each.

#### [1 - Load Data](scripts/1%20-%20Load%20Data.ipynb)

Loads all the data from a particular dataset (exported from the [UXtweak Session Recording tool](https://www.uxtweak.com/session-recording-tool)) and selects only files containing sessions with completed purchases.

#### [2 - Parsing](scripts/2%20-%20Parsing.ipynb)

Extracts interaction events and non-interaction data and processes them into Pandas dataframes.

#### [3 - Features](scripts/3%20-%20Features.ipynb)

Constructs features to be used for the user model.

#### [4 - Data Cleaning and Statistics](scripts/4%20-%20Data%20Cleaning%20and%20Statistics.ipynb)

Performs basic data clean-up and computes various statistics with visualizations.

#### [5 - DOM parsing](scripts/5%20-%20DOM%20parsing.ipynb)

Parses the Document Object Model (DOM) of the dataset's website and constructs additional features.

#### [6 - Correlation](scripts/6%20-%20Correlation.ipynb)

Evaluates correlation of constructed features.

#### [7 - Transformation](scripts/7%20-%20Transformation.ipynb)

Transforms the data into form suitable for model training.

#### [8 - Column Selection](scripts/8%20-%20Column%20Selection.ipynb)

Removes highly correlated features from the data.

#### [9 - Sampling, Normalization, Train-Test Set](scripts/9%20-%20Sampling%2C%20Normalization%2C%20Train-Test%20Set.ipynb)

Performs data sampling, normalization and splits the data into train and test sets.

#### [10 - Feature Selection](scripts/10%20-%20Feature%20Selection.ipynb)

Performs feature selection by means of several methods - ANOVA, ANOVA with Random Forest, LASSO.

#### [11 - Classification - with feature selection](scripts/11%20-%20Classification%20-%20feature%20sets.ipynb)

Trains and evaluates the model in the repeat purchase prediction task when used with different feature sets.

#### [12 - Classification - attributes sets](scripts/12%20-%20Classification%20-%20feature%20selection.ipynb)

Trains and evaluates the model in the repeat purchase prediction task when used alongside several feature selection methods.

#### [13 - Classification - different datasets](scripts/13%20-%20Classification%20-%20cross%20dataset.ipynb)

Evaluates the model's generalziation capabilities by means of a leave-one-out cross-validation (LOOCV) using the three datasets.

## <a name="a-results"> Results

The following figures contain extended evaluation results and belong to the Dataset and Results sections of the research paper, respectively.

#### Extended Table 1. - Comparison of baseline model’s performance with model variants, including different machine learning methods
  
<p align="center">
  <a href="figures/Extended%20Table%201.%20Comparison%20of%20features%20sets.png"><img style="width: 80%; height: 80%;" src="figures/Extended%20Table%201.%20Comparison%20of%20features%20sets.png" alt="Extended Table 1. Comparison of baseline model’s performance (N - non-interaction features) in the repeat purchase prediction task with
model variants utilizing new feature categories based on low-level interaction data. BM stands for baseline model, while N, Ig,
Ie reference the non-interaction, ecommerce-related interaction and generic interaction features, respectively."/></a>
</p>
  
<p align="center">Extended Table 1. Comparison of baseline model’s performance (N - non-interaction features) in the repeat purchase prediction task with model variants utilizing new feature categories based on low-level interaction data. BM stands for baseline model, while N, Ig,
Ie reference the non-interaction, ecommerce-related interaction and generic interaction features, respectively. <a href="figures/Extended%20Table%201.%20Comparison%20of%20features%20sets.html">Source Table in HTML.</a></p>


#### Extended Table 2. - Comparison of the ANOVA and LASSO feature selection methods’ performance with the full feature set, including different machine learning methods 
<p align="center">
  <a href="figures/Extended%20Table%202.%20Comparison%20of%20feature%20selection%20methods%20-%20ANOVA%2C%20LASSO.png"><img style="width: 80%; height: 80%;" src="figures/Extended%20Table%202.%20Comparison%20of%20feature%20selection%20methods%20-%20ANOVA%2C%20LASSO.png" alt="Extended Table 2. Comparison of the ANOVA and LASSO feature selection methods’ performance with the full feature set, including different machine learning methods."/></a></p>

<p align="center">Extended Table 2. Comparison of the ANOVA and LASSO feature selection methods’ performance with the full feature set and the Gradient Boosting classifier used for the repeat purchase prediction task. <a href="figures/Extended%20Table%202.%20Comparison%20of%20feature%20selection%20methods%20-%20ANOVA%2C%20LASSO.html">Source Table in HTML.</a></p>
  
#### List of features selected by feature selection methods ANOVA, ANOVA + RF and LASSO
<p align="center">
  <a href="figures/List%20of%20selected%20features.png"><img style="width: 100%; height: 100%;" src="figures/List%20of%20selected%20features.png" alt="List of features selected by feature selection methods ANOVA, ANOVA + RF and LASSO"/></a>
</p>

<p align="center">List of features selected by feature selection methods ANOVA, ANOVA + RF and LASSO. <a href="figures/List%20of%20selected%20features.html">Source Table in HTML.</a></p>

## <a name="a-authors"> Authors
  
### Eduard Kuric
He is a researcher and lecturer at [Faculty of Informatics and Information Technologies](https://www.fiit.stuba.sk/), [Slovak University of Technology in Bratislava](https://www.stuba.sk/). He is also a founder of [UXtweak](https://www.uxtweak.com). His research interests include user modeling, human-computer interaction, and machine learning.
- Email: eduard.kuric([AT])stuba.sk
- [LinkedIn](https://www.linkedin.com/in/eduard-kuric-b7141280/)
- [Google Scholar](https://scholar.google.com/citations?user=MwjpNoAAAAAJ&hl=en&oi=ao)

### Adam Puskas
He is a researcher and project manager at [UXtweak](https://www.uxtweak.com/). In his research, he currently focuses on application of deep learning methods in the field of human-computer interaction.
- Email: adam.puskas([AT])uxtweak.com
  
### Peter Demcak
He is a researcher at [UXtweak](https://www.uxtweak.com/). His current research topics of interest involve user behavior, UX research methods and design practices and machine learning.
- Email: peter.demcak([AT])uxtweak.com
  
### Denisa Mensatorisova
She is a machine learning engineer focusing on predictive modeling and data mining. In her work, she is addressing the challenges and problems in user modeling, machine learning and data science.
- Email: dmensatorisova([AT])gmail.com
  
### General Contact  
- Email: prce.research([AT])gmail.com

## <a name="a-licence"> Licence

This work is licensed under a
<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">
Creative Commons Attribution-NonCommercial 4.0 International License.
</a>

<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/" style="margin-left: 8rem">
<img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" />
</a>
