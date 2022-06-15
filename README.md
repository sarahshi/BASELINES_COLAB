# BASELINES

PyBL is a Bayesian MCMC-founded Python algorithm for determining volatile concentrations and speciation for $H_2O_{T, 3550}$, $H_2O_{m, 1635}$, $CO_{3, 1515}^{2-}$, $CO_{3, 1430}^{2-}$, $H_2O_{m, 5200}$, and $OH_{4500}$ from rhyolitic-basaltic FTIR spectra. PyBL is written in the open-source language Python3 with the $MC^3$ package, created by Cubillos et al., 2017, allowing for the proper sampling of parameter space and the determination of volatile concentrations with uncertainties. 

This algorithm applies to samples for which devolatilized spectra and baselines are not available. We utilize spectra of natural, devolatilized melt inclusions from the Aleutians to determine the fundamental shapes and variability of the baseline in the mid-IR region, in which the $CO_3^{2-}$ doublets and $H_2O_{m, 1635}$ peaks are found. The shape of the baseline and that of the peaks varies across samples, dependent on the chemistry of samples and concentration of volatiles. Traditional FTIR baseline and peak fitting techniques involve splines, only fitting baselines to portions of the spectra without an assessment of uncertainty. PyBL instead fits all parameters—the average baseline, 4 principal components explaining variability in the baseline, the average $H_2O_{m, 1635}$ peak, 2 principal components explaining variability in the $H_2O_{m, 1635}$ peak, and the two Gaussian $CO_3^{2-}$ peaks (including the standard deviation, peak location, and amplitude)—simultaneously, allowing for a proper determination of uncertainties and the covarying uncertainties associated with each peak. We additionally update the last existing regressions, from Dixon and Pan, 1995 for the $CO_3^{2-}$ peaks and Mandeville et al., 2002 for $H_2O$ related peaks, for absorbance coefficients for each peak and generate a new regression for the $H_2O_{m, 1635}$ peak, which similar to the other $H_2O$ peaks, is dependent on the $\tau = X_{Si}+X_{Al}$ parameter. The regression is founded on an inversion technique, which accounts for uncertainty in both the chemical compositional parameters and the absorbance coefficients. This allows volatile concentrations for basaltic-rhyolitic samples spanning the data region to be determined. 

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/sarahshi/BASELINES/HEAD)