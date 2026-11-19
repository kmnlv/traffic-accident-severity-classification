# Traffic Accident Analysis and Severity Classification in Hermosillo

> Final project · Programming for Descriptive and Predictive Analytics · Semester 1

## Overview

End-to-end descriptive analytics and classification project built on Mexico's public **ATUS 2024** traffic-accident dataset (INEGI). The first part compares Hermosillo with the national picture: accident counts, monthly/hourly/weekly patterns, accident types, vehicles involved, casualties and reported causes. The second part preprocesses the data and trains a classifier for accident severity (`CLASACC`: *Solo daños*, *No fatal*, *Fatal*).

## Repository structure

- `notebooks/traffic-accidents-hermosillo.ipynb` - full analysis with executed outputs.

## Methods

- Data quality: no missing values; 1,678 duplicate rows removed; categorical dtype conversion.
- Descriptive analysis with frequency tables and visualization across 390,627 national records, including 11,991 from Hermosillo.
- Feature selection: Cramer's V for categorical association, Pearson correlation for numeric variables, VIF for multicollinearity, removal of constant columns and post-outcome variables.
- Preprocessing: one-hot encoding, train/test split, numeric scaling.
- Class imbalance handled with class weighting, SMOTE and random-search hyperparameter tuning.

## Results

The descriptive phase finds that Hermosillo is among the municipalities with the highest accident counts in Mexico, with afternoon peaks and Friday as the busiest day. The classification phase honestly reports a limitation: the *Fatal* class is only ~0.32% of the data (8 test cases) and none of the attempted strategies - class weights, SMOTE or random search - achieved non-zero precision/recall/F1 for that class. The notebook documents this negative result and its cause rather than hiding it.

## Data

The source is INEGI's **Accidentes de Tránsito Terrestre en Zonas Urbanas y Suburbanas (ATUS) 2024**, publicly downloadable as CSV. The raw file is not redistributed here; download it from INEGI and place it where the notebook expects it.

## Requirements

`pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `imbalanced-learn` and `jupyter`.

## How to run

```bash
pip install -r requirements.txt
jupyter notebook notebooks/traffic-accidents-hermosillo.ipynb
```

---
Author: Karla Maria Monroy Alvarez
