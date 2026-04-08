# 🌊 Aquaculture Impacts in Lake Titicaca

This repository contains the data, code, and analytical workflow supporting the study:

**"Assessment of aquaculture impact on Lake Titicaca: Combining Bayesian modelling and C and N stable isotopes to support sustainable strategies"**

---

## 📌 Overview

Aquaculture provides over half of the global fish supply for human consumption, yet its rapid expansion raises critical environmental concerns, particularly in freshwater ecosystems.

This study evaluates the ecological impact of **cage-based rainbow trout (Oncorhynchus mykiss) farming** in **Lake Titicaca**, a high-altitude and ecologically sensitive system. The analysis focuses on:

- Nutrient enrichment processes  
- Water quality alterations  
- Effectiveness of faecal waste collectors  
- Spatial and seasonal variability  
- Carbon and nitrogen stable isotope dynamics  

We adopt an integrative framework combining **physicochemical variables**, **eutrophication indicators**, and **stable isotope analysis**, modelled through a **Bayesian multivariate approach**.

---

## 🎯 Objectives

- Quantify the impact of trout cages on water quality  
- Assess the effectiveness of faecal waste collectors as mitigation tools  
- Disentangle treatment effects from spatial and seasonal variability  
- Provide an integrated, multi-indicator assessment of aquaculture impacts  

---

## 🗂 Repository Structure
```
.
├── Final_Df/              # Final processed datasets used for modelling
├── Lago Titicaca/        # Raw and site-specific data
├── Pictures/             # Figures, plots, and graphical outputs
├── Utils/                # Helper functions and utility scripts
│
├── EDA.R                 # Exploratory Data Analysis
├── Preprocessing.R       # Data cleaning and preprocessing pipeline
├── Models.R              # Bayesian multivariate modelling
│
├── README.md             # Project documentation
├── LICENSE               # MIT License
└── .gitignore
```

---

## 🔬 Methodology

### 📍 Study Area

Lake Titicaca (Peru–Bolivia), located at 3,814 m a.s.l., was investigated across two contrasting environments:

- **Puno Bay (Barco-Chuquito)** → shallow, semi-enclosed, high sedimentation  
- **Chucasuyo** → deeper, exposed, higher water exchange  

### 🧪 Sampling Design

- Monthly sampling: **March – August 2024**  
- Three treatment conditions:
  1. Cages with faecal waste collectors  
  2. Cages without collectors  
  3. Control sites (no cages)  

### 📊 Variables

**Physicochemical variables**
- Temperature, pH, Dissolved Oxygen (DO), Electrical Conductivity (EC), Transparency  

**Eutrophication-related variables**
- Chlorophyll-a, NO₂, NO₃, Total Nitrogen (TN), PO₄, Total Phosphorus (TP)  

**Biogeochemical tracers**
- δ¹³C and δ¹⁵N in sediments and particulate organic matter (POM)  

---

## 📈 Modelling Approach

A **Bayesian multivariate regression framework** was implemented to jointly model correlated response variables.

- Implemented in **R (brms interface to Stan)**
- All variables standardised prior to modelling  
- Covariance structure explicitly modelled  

### Model Specifications

- **Baseline model** → fixed effects (location, treatment, time)  
- **Random effects model** → sampling point heterogeneity  
- **Nested model** → interaction (location × treatment)  

### Model Evaluation

- WAIC (Watanabe–Akaike Information Criterion)  
- LOOIC (Leave-One-Out Cross-Validation)  

---

## ⚙️ Workflow

The analysis follows a structured pipeline:

### 1. Data Preprocessing
- Data cleaning  
- Variable transformation  
- Dataset integration  

source("Preprocessing.R")

### 2. Exploratory Data Analysis
- Distribution checks
- Correlation structure
- Preliminary statistical tests

source("EDA.R")

### 3. Model Estimation
- Bayesian multivariate models
- Posterior inference
- Model comparison

## 📊 Outputs

The repository produces:

- Posterior estimates and credible intervals  
- Model diagnostics (R-hat, ESS, convergence checks)  
- Figures for publication (stored in `Pictures/`)  
- Cleaned datasets (`Final_Df/`)  
- Correlation structures and exploratory plots  