# MNE-Preprocessing

EEG preprocessing is required to attenuate artifacts and improve signal quality for downstream analysis.

This **MNE preprocessing repository** is implemented using the [MNE-Python package](https://mne.tools/stable/index.html).

---

## Resting-state EEG preprocessing for PSD analysis

The script `rs_eeg_prep_for_psd_analysis` is designed for resting-state EEG preprocessing, specifically for power spectrum–based analyses, including 1/f (aperiodic) and oscillatory (periodic) components.

---

## Preprocessing pipeline

EEG signals were:

- Downsampled to **1000 Hz**
- Band-pass filtered between **0.1–45 Hz** or **0.1–95 Hz**, with stop filter arounf 5 and 100
- Visually inspected to identify noisy channels
- Noisy segments (e.g., muscle artifacts affecting multiple channels) were manually identified and excluded
- Bad channels (high-amplitude artifacts consistent across recordings) were removed and spherically interpolated
- Data were re-referenced to the average reference
- To enhance spatial specificity and reduce volume conduction effects at the sensor level, a **surface Laplacian (current source density, CSD)** transform was applied with the parameters ( Stiffness: *m = 5*, Legendre polynomial: *80*, Regularization parameter: *λ = 10⁻³*)
- Independent Component Analysis (ICA) using the **FastICA algorithm** was applied to identify and remove non-brain artifacts (e.g., eye blinks, and muscle activity).
  
### Citations
Bertino, S., Ghaderi-Kangavari, A., Meder, D., Vinding, M.C., Raaf, N., Christiansen, L., Thomsen, B.L.C., Løkkegaard, A., Quartarone, A., Beck, M.M. and Siebner, H.R. (2026). Increased aperiodic offset and heightened alpha power characterize resting-state EEG activity in Parkinson′ s disease. medRxiv, 2026-01.

Ghaderi-Kangavari, A., Rad, J. A., Parand, K., & Nunez, M. D.  (2022). Neuro-cognitive models of single-trial EEG measures describe latent effects of spatial attention during perceptual decision making, Journal of Mathematical Psychology, 111; doi: https://doi.org/10.1016/j.jmp.2022.102725 

## Prerequisites

- [mne](https://mne.tools/stable/install/mne_python.html)

- [numpy](https://numpy.org/install/)

- [pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/install.html)
