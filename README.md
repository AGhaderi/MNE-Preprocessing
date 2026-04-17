# MNE-Preprocessing

EEG preprocessing is required to attenuate artifacts and improve signal quality for downstream analysis.

This **MNE preprocessing repository** is implemented using the [MNE-Python package](https://mne.tools/stable/index.html).

---

## Resting-state EEG preprocessing for PSD analysis

The script `rs_eeg_prep_for_psd_analysis` is designed for resting-state EEG preprocessing, specifically for power spectrum–based analyses, including 1/f (aperiodic) and oscillatory (periodic) components.

- Downsampled to **1000 Hz**
- Band-pass filtered between **0.1–45 Hz** or **0.1–95 Hz** using FIR filtering, followed by notch filtering at **50 Hz** and its harmonic (**100 Hz**)
- Visually inspected to identify noisy segments (e.g., muscle artifacts affecting multiple channels), which were manually labeled as `bad_artifact`
- Bad channels (high-amplitude artifacts consistent across recordings) were removed and spherically interpolated
- Data were re-referenced to the average reference
- To enhance spatial specificity and reduce volume conduction at the sensor level, a **surface Laplacian (current source density, CSD)** transform was applied with parameters (Stiffness= 4, Legendre polynomial= 80, Regularization parameter= 10⁻³)
- Independent Component Analysis (ICA) using the **FastICA algorithm** was applied to identify and remove non-brain artifacts (e.g., eye blinks and muscle activity)

---

### Citations
1. Bertino, S., Ghaderi-Kangavari, A., Meder, D., Vinding, M.C., Raaf, N., Christiansen, L., Thomsen, B.L.C., Løkkegaard, A., Quartarone, A., Beck, M.M. and Siebner, H.R. (2026). Increased aperiodic offset and heightened alpha power characterize resting-state EEG activity in Parkinson′ s disease. medRxiv, 2026-01. doi: https://doi.org/10.64898/2026.01.20.26343832

2. Ghaderi-Kangavari, A., Rad, J. A., Parand, K., & Nunez, M. D.  (2022). Neuro-cognitive models of single-trial EEG measures describe latent effects of spatial attention during perceptual decision making, Journal of Mathematical Psychology, 111. doi: https://doi.org/10.1016/j.jmp.2022.102725 
