# MNE-Preprocessing

EEG data routinely record as the continuous (Raw) signal which contains of the real source
of brain signal, artifact and noise.

For preprocessing EEG data, the **MNE-Preprocessing repocitory** was implemented by the **MNE-package in python**.

The preprocessing was performed as follows:

256 points as the **sampling rate**, **band-pass filter** in the range 1 Hz - 30 Hz, **re-referencing**
with average of sensors, **visual inspection** to remove abnormal frequency, **interpolation** fully
corrupted signal, **discarding range** of -100 mV to +100 mV amplitude, **extracting Epochs**
from - 100 ms (baseline) of cue’s onset to 600 ms after stimulus appearance (totally 1700
ms), running Independent Component Analysis **(ICA)** to remove manually irrelevant-task
(e.g. eye movement, head motion and muscular activity), detecting automatically eyeblinking
**EOG** component and heartbeat peak **ECG** component.


## Prerequisites

- [mne](https://mne.tools/stable/install/mne_python.html)

- [numpy](https://numpy.org/install/)

- [pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/install.html)
