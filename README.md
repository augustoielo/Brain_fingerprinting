# Brain_fingerprinting

Sample code for computing **brain connectome fingerprinting metrics**
and **reliability measures** from functional connectomes.

This repository is derived from the original project:

https://github.com/eamico/Clinical_fingerprinting

which accompanied the work reported in Sorrentino et al., *Clinical
connectome fingerprints of cognitive decline*, NeuroImage 2021.

The present repository focuses on **connectome fingerprinting metrics
and reliability analysis**, and **does not include the clinical
fingerprinting components (Iclinical)** from the original
implementation.

------------------------------------------------------------------------

## Overview

The code compares two functional connectome (FC) acquisitions/sessions
for each subject (defined as **test** and **retest**) and produces an
**identifiability matrix** (Amico & Goñi, Scientific Reports 2018).

Its main diagonal (top left to bottom right) highlights the
**self-identifiability (Iself)** of the sample, i.e. the similarity
between the test and retest FC of the same subject.\
The remaining elements consist of comparisons between test and retest FC
of different subjects (**Iothers**).

Additionally, this repository provides tools to estimate the
**Intraclass Correlation Coefficient (ICC)** of connectome edges using a
**resampling strategy based on 80% subsampling of subjects**.

The repository implements the following fingerprinting metrics:

- **Iself** – similarity between test and retest connectomes of the same subject  
- **Iothers** – similarity between connectomes of different subjects  
- **Idiff** – differential identifiability (Iself − Iothers)  
- **Idiff-norm** – normalized differential identifiability (Cohen's d style)  
- **Success Rate (SR)** – proportion of correct identifications  
- **Edgewise ICC** – reliability of connectome edges estimated with resampling

------------------------------------------------------------------------

## Repository structure

The repository contains a minimal example for computing connectome
fingerprinting metrics.

Typical workflow:

1. Load functional connectomes (test and retest sessions)
2. Compute the **identifiability matrix**
3. Compute fingerprinting metrics (**Iself, Iothers, Idiff, Idiff-norm**)
4. Estimate **ICC reliability** using resampling

Main components:

- `data_test_FC.mat` – example functional connectome dataset  
- main script – example implementation of the fingerprinting analysis  
- `f_load_mat` – function to vectorize FC matrices  
- `f_ICC_edgewise` – function to compute edgewise ICC

Example usage:

1. Load the example dataset
2. Run the main script
3. The script outputs the identifiability matrix, fingerprinting metrics,
   and ICC reliability estimates.

------------------------------------------------------------------------

## Data

The example dataset included in the repository contains functional
connectomes used for demonstration purposes.

*PLEASE NOTE: For privacy reasons, the same data used in Sorrentino et
al. are not included.*\
The example results reported here are therefore **illustrative of the
methodology** and do not correspond to the original manuscript.

Example connectomes come from **healthy MEG datasets derived from the
Human Connectome Project** (see Sareen et al., NeuroImage 2021 for
details).

------------------------------------------------------------------------

## Authors of the original repository

Emahnuel TROISI LOPEZ\
Pierpaolo SORRENTINO\
Enrico AMICO

Version 1.0 -- July 01, 2021

------------------------------------------------------------------------

## Differences from the original repository

Compared to the original repository (Clinical_fingerprinting), this
version introduces several modifications:

- the **clinical fingerprinting analysis (Iclinical)** has been removed
  in order to focus on general connectome fingerprinting metrics;
- the **normalized differential identifiability (Idiff-norm)** is
  computed as a standardized effect size (Cohen's *d* style);
- **bootstrap confidence intervals** for Idiff-norm are estimated via
  subject-level resampling;
- **edgewise Intraclass Correlation Coefficient (ICC)** is estimated
  using repeated **80% subsampling of subjects** in order to stabilize
  reliability estimates.

------------------------------------------------------------------------

## PLEASE CITE

If you are using the fingerprinting methodology implemented in this code
for your research, please kindly cite:

Authors: Sorrentino P, Rucco R, Lardone A, Liparoti M, Lopez ET,
Cavaliere C, Soricelli A, Jirsa V, Sorrentino G, Amico E.\
Title: Clinical connectome fingerprints of cognitive decline.\
Published on: NeuroImage - 2021 Jun 9, p. 118253.\
Doi: doi.org/10.1016/j.neuroimage.2021.118253

Authors: Ielo A, Genovese D, Falcó-Roget J, Amico E, Di Rocco A, Norcini
M, Quartarone A, Ghilardi MF, Cacciola A.\
Title: Brain connectivity fingerprinting as a predictive biomarker of
art therapy outcomes in Parkinson's disease.\
Published on: Research Square - 2026 Jan 29.\
Doi: doi.org/10.21203/rs.3.rs-8475840/v1
