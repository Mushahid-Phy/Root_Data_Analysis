# Root_Data_Analysis
Data Anylysis in High Energry Physics Using Root Framework 
# ROOT Fitting Macro for Particle Physics Analysis

This repository contains a ROOT-based macro for fitting particle physics data using the ROOT framework. The macro is designed to analyze and fit transverse momentum distributions with a specific model, making use of the ROOT libraries for data analysis and visualization.

## Overview

The macro `tut17.C` performs the following tasks:

1. **Reads Data**: Loads data from files (e.g., `PbPb0.dat`, `PbPb1.dat`, `PbPb2.dat`).
2. **Fits Data**: Fits the data using a customized function defined in the `fEqn` method.
3. **Visualizes Results**: Plots the data with fitted curves and displays fit parameters and chi-squared values.

## Function Definitions

### `fEqn(const Double_t *x, const Double_t *p)`

Defines the fitting function based on the following parameters:
- `C`: Normalization constant
- `beta_T`: Transverse velocity parameter
- `n`: Exponent
- `T0`: Temperature parameter

The function uses these parameters to compute a theoretical fit to the transverse momentum (`pt`) distribution.

## Compilation and Execution

To compile and run the macro, follow these steps:

1. **Install ROOT**: Ensure ROOT is installed on your system. Follow the [ROOT installation guide](https://root.cern/install/) if needed.

2. **Compile the Macro**:
   Open a terminal and navigate to the directory containing `tut17.C`. Run the following command:
   ```bash
   root -l -b -q tut17.C
    The macro will generate a canvas with fitted curves and data points. The output will be displayed in a ROOT canvas window.
   
