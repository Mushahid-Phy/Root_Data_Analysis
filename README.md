# ROOT Fitting Macro for Particle Physics Analysis

This repository contains a ROOT-based macro for fitting particle physics data using the ROOT framework. The macro utilizes the Hegdrons function for fitting transverse momentum distributions.

## Overview

The macro `tut17.C` performs the following tasks:

1. **Reads Data**: Loads data from files (e.g., `PbPb0.dat`, `PbPb1.dat`, `PbPb2.dat`).
2. **Fits Data**: Applies the Hegdrons function to fit the data.
3. **Visualizes Results**: Plots the data with fitted curves and displays fit parameters and chi-squared values.

## Hegdrons Function

The Hegdrons function is used to model transverse momentum distributions in particle physics. The function is defined as:

\[ f(pt) = 2 \pi pt \cdot C \cdot \left(1 + \frac{\gamma_T}{n} \cdot \frac{(mt - pt \cdot \beta_T)}{T0}\right)^{-n} \]

where:
- \( C \) is the normalization constant.
- \( \beta_T \) is the transverse velocity parameter.
- \( n \) is the exponent.
- \( T0 \) is the temperature parameter.
- \( \gamma_T \) is related to \( \beta_T \) through the Lorentz factor: \( \gamma_T = \frac{1}{\sqrt{1 - \beta_T^2}} \).
- \( mt \) is the transverse mass: \( mt = \sqrt{pt^2 + m0^2} \), with \( m0 \) being a fixed mass parameter.

## Fitting Process

1. **Initialization**: The macro initializes ROOT and sets up a canvas for visualization. It then creates `TGraphErrors` objects for each dataset and defines the Hegdrons function using `TF1`.

2. **Parameter Setup**: Initial parameter values and limits are set for the fit. These include:
   - Normalization constant (`C`): Initial value 10.
   - Transverse velocity parameter (`beta_T`): Initial value 0.74.
   - Exponent (`n`): Initial value 10.3.
   - Temperature parameter (`T0`): Initial value 0.1 GeV.

   Parameter limits are also defined to constrain the fitting process to reasonable values.

3. **Fitting**: The macro performs the fit using the `Fit` method of `TGraphErrors`. Different options are used based on the iteration to control the fitting process.

4. **Visualization**: The macro generates a canvas displaying the data points and fitted curves. It also prints fit results, including chi-squared values and parameter uncertainties, for each dataset.

## Compilation and Execution

To compile and run the macro, follow these steps:

1. **Install ROOT**: Ensure ROOT is installed on your system. Follow the [ROOT installation guide](https://root.cern/install/) if needed.

2. **Compile the Macro**:
   Open a terminal and navigate to the directory containing `tut17.C`. Run the following command:
   ```bash
   root -l -b -q tut17.C

The macro will generate a canvas with fitted curves and data points. The output will be displayed in a ROOT canvas window.
![Photo 1](https://github.com/user-attachments/assets/920b4ab7-2efe-46d6-b3dc-022191559917)

