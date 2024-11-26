# MNE-Preprocessing

Scientists usually record EEG data as the continuous (Raw) signal which consists of irrelevant signal (brain signal) and irrelevant signal (artifact), therefore we need to attenuate the effects artifacts to make clear signals.

For preprocessing EEG data, the **MNE-Preprocessing repocitory** is implemented by the [**MNE-package**](https://mne.tools/stable/index.html) in python.

The preprocessing is performed as follows:

256 points as the **sampling rate**, **band-pass filter** in the range 1 Hz - 30 Hz, **re-referencing** with an average of sensors, **visual inspection** to remove abnormal frequency, **interpolation** fully corrupted signal, **discarding range** of -100 mV to +100 mV amplitude, **extracting Epochs** from - 100 ms (baseline) of cue’s onset to 600 ms after stimulus appearance (or any period time you want), running Independent Component Analysis (ICA) to remove manually irrelevant-task (e.g. eye movement, head motion, and muscular activity), detecting automatically eye-blinking **EOG** component and heartbeat peak **ECG** component.

### Citations
Ghaderi-Kangavari, A., Rad, J. A., Parand, K., & Nunez, M. D.  (2022). Neuro-cognitive models of single-trial EEG measures describe latent effects of spatial attention during perceptual decision making, Journal of Mathematical Psychology, 111; doi: https://doi.org/10.1016/j.jmp.2022.102725 

## Prerequisites

- [mne](https://mne.tools/stable/install/mne_python.html)

- [numpy](https://numpy.org/install/)

- [pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/install.html)
