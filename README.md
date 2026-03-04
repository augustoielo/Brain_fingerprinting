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

From the identifiability matrix it is possible to compute several
fingerprinting metrics, including:

-   **Iself**
-   **Iothers**
-   **Idiff**
-   **Idiff-norm**
-   **Success Rate (SR)**

Additionally, this repository provides tools to estimate the
**Intraclass Correlation Coefficient (ICC)** of connectome edges using a
**resampling strategy based on 80% subsampling of subjects**.

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
