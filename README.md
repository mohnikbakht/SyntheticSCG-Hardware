# Synthetic ECG SCG Generator Demo

Seismocardiogram (SCG) is the measure of the thoracic vibrations produced by the heart’s contraction and the ejection of blood from the ventricles into the vascular tree. Today, the SCG can readily be detected by placing a low-noise accelerometer on the chest. 

Electrocardiogram (ECG) signal reflects the electrical activity of the heart observed from the strategic points of the human body and represented by quasi-periodic voltage signal.

These signals fiducial points correspond to characteristic events in the cardiac cycle. For the SCG, the labels correspond to the physiological event they are believed to represent: MC, mitral valve closure; IVC, isovolumetric contraction; AO, aortic valve opening; RE, rapid ejection; AC, aortic valve closure; MO, mitral valve open- ing; and RF, rapid filling.


However, SCG signals are small signal, and they can get distorted easily by motion artifacts. Therefore exploring denoising methods is of great importance for SCG signals. Clearing out the noise enables extraction of physiologically relevant information from SCG. To study denoising methods, we need to collect SCG signals in noisy environments, but it is unsafe to use human subjects for such data collection in some high motion environments (medical transport helicopters). To address this, here we designed a phantom that can generate SCG and ECG signals synthetically. This enables us to collect data in those noisy environmnets without human subject involvement.

## The Hardware 

The hardware consists of a Raspberry Pi 4 and an actuator.

<img src="https://github.com/mohnikbakht/Synthetic_ECG_SCG_Generator_Hardware/blob/main/figures/figure2.png" alt="Image of The ECG/SCG Patch" width="800"/>


<img src="https://github.com/mohnikbakht/Synthetic_ECG_SCG_Generator_Hardware/blob/main/figures/figure1.png" alt="Image of The ECG/SCG Patch" width="800"/>



<!-- <img src="https://github.com/mohnikbakht/Synthetic_ECG_SCG_Generator_Demo/blob/main/Images/Actuator2.png" alt="Image of The ECG/SCG Patch" width="300"/> -->


The actuator is non-linear in low frequency and needs calibration to make sure it replicates the input signal to the output in form of acceleration.
The code is written in Python and in a way that you have two options:

1) Calibration mode: Calibrate the system (in a new environment):
```console
python3 Synthetic_SCG.py calibrate
```

<img src="https://github.com/mohnikbakht/Synthetic_ECG_SCG_Generator_Demo/blob/main/Images/calibrate_1.png" alt="Image of The ECG/SCG Patch" width="400"/>


2) Generation mode: Generate SCG waveforms:

```console
python3 Synthetic_SCG.py generate signal1.wav
```

<img src="https://github.com/mohnikbakht/Synthetic_ECG_SCG_Generator_Demo/blob/main/Images/generate_1.png" alt="Image of The ECG/SCG Patch" width="400"/>



## Use

Depending on the type of the connection to the RPi, there are 2 options:
1) If a display is connected to the RPi (or have X11 forwarding enabled), the plots will be shown in separate windows. Use this command (this mode is default):
```console
python3 Synthetic_SCG.py generate signal1.wav desktop
```
2) If communication is through a terminal only, the plots will be plotted in the terminal (lower quality). Use this command:
```console
python3 Synthetic_SCG.py generate signal1.wav terminal
```
## Output Recording Samples

A 10s generated ECG and SCG with a heart-rate of 60 bpm:

<img src="https://github.com/mohnikbakht/figures/blob/main/figures/figure3.png" alt="Image of The ECG/SCG Patch" width="600"/>
<img src="https://github.com/mohnikbakht/figures/blob/main/figures/bland-altman.png" alt="Image of The ECG/SCG Patch" width="600"/>

<!-- Zoomed in:

<img src="https://github.com/mohnikbakht/Synthetic_ECG_SCG_Generator_Demo/blob/main/Images/sample_2.png" alt="Image of The ECG/SCG Patch" width="600"/>

 -->

