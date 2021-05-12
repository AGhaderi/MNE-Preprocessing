# MNE-Preprocessing

Scientists usually record EEG data as the continuous (Raw) signal which consists of irrelevant signal (brain signal) and irrelevant signal (artifact), therefore we need to attenuate the effects artifacts to make clear signals.

For preprocessing EEG data, the **MNE-Preprocessing repocitory** is implemented by the [**MNE-package**](https://mne.tools/stable/index.html) in python.

The preprocessing was performed as follows:

256 points as the **sampling rate**, **band-pass filter** in the range 1 Hz - 30 Hz, **re-referencing**
with average of sensors, **visual inspection** to remove abnormal frequency, **interpolation** fully
corrupted signal, **discarding range** of -100 mV to +100 mV amplitude, **extracting Epochs**
from - 100 ms (baseline) of cue’s onset to 600 ms after stimulus appearance (or any period time you want), running Independent Component Analysis **(ICA)** to remove manually irrelevant-task
(e.g. eye movement, head motion and muscular activity), detecting automatically eyeblinking
**EOG** component and heartbeat peak **ECG** component.


## Prerequisites

- [mne](https://mne.tools/stable/install/mne_python.html)

- [numpy](https://numpy.org/install/)

- [pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/install.html)
