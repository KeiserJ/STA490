# Shark Behavioral State Analysis with Hidden Markov Models

This repository contains the code, figures, and presentation materials for our project on **behavioral state analysis of Galápagos sharks** using **Hidden Markov Models (HMMs)**.

## Project Overview

We analyze biologging data from two Galápagos sharks to infer latent behavioral states from movement and activity signals. The main variables used in the analysis are:

- **Depth**
- **ODBA** (Overall Dynamic Body Acceleration; derived from acceleration)
- **Light** (used in the extended model)

The core goal of the project is to identify interpretable behavioral states, compare those states across the two sharks, and study how behavior changes across the day-night cycle.

## Main File

The primary analysis is contained in:

- `analysis_clean.ipynb`

This notebook is the main file for the project and includes the core workflow:
- data preprocessing
- feature construction
- HMM fitting
- state interpretation
- cross-shark comparison
- diel analysis
- light-based extension analysis
- figure generation for presentation

If you only open one file in this repository, open **`analysis_clean.ipynb`**.

## Repository Structure

### `analysis_clean.ipynb`
Main notebook containing the full cleaned analysis pipeline.

### `revised_hmm_output_managed.ipynb`
Notebook containing the revised analysis.

### `EDA/`
Exploratory analysis files and supporting materials used during early stages of the project.

### `pres_2var/`
Outputs and materials related to the **2-variable HMM** using:
- depth
- log(ODBA)

This is the main comparison framework used in the final presentation because it gives directly comparable behavioral states across both sharks.

### `pres_3var/`
Outputs and materials related to the **3-variable HMM** using:
- depth
- log(ODBA)
- light

This model improves statistical fit, but it changes the inferred state structure differently across individuals, so it is treated as an extension rather than the main comparison model.

### `pres_images/`
Presentation-ready figures exported from the notebook, including behavioral budgets, diel patterns, transition plots, and light-analysis figures.

### `README.md`
Project description and navigation guide.

### `revised_hmm_outputs`
Revised Project outputs.

## Analysis Summary

We fit Hidden Markov Models to classify shark behavior into latent states.

### 2-variable HMM
The 2-variable HMM uses:
- mean depth
- log(ODBA)

This model was used as the main comparison model because both sharks showed the same three interpretable state categories:

- **Cruising / Routine Swimming**
- **Deep Diving / Foraging**
- **Surface Active**

### 3-variable HMM
The 3-variable HMM adds:
- light intensity

Adding light improves model fit, but it also reorganizes the state structure differently for each shark. This makes it useful for interpretation, but less suitable for direct state-by-state comparison across sharks.

## Reproducing the Analysis

To reproduce the analysis:

1. Open `analysis_clean.ipynb`, `revised_hmm_output_managed.ipynb`
2. Run the notebook from top to bottom with the dataset.
