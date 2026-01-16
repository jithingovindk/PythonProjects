# Digital Signal Processing & Noise Filtering Tool

##  Overview
This project implements a **Fast Fourier Transform (FFT)** based algorithm to analyze spectral components of time-domain signals and perform noise reduction. While the current implementation demonstrates this capability using audio data (`.wav`), the underlying mathematical principles are applicable to analyzing signal-to-noise ratios (SNR) in **opto-electronic devices**, photodetector outputs, and other physical sensor data.

##  Key Features
* **Spectral Decomposition:** Converts time-domain signals into the frequency domain using 1D-FFT.
* **High-Frequency Noise Filtering:** Implements a "Brick-Wall" Low-Pass Filter logic to isolate fundamental frequencies.
* **Signal Reconstruction:** Uses Inverse FFT (IFFT) to reconstruct the cleaned time-domain signal.
* **Data Visualization:** Plots amplitude vs. time and frequency spectrums to visually inspect signal quality.

##  Technologies Used
* **Python 3.x**
* **NumPy:** For high-performance mathematical operations (FFT, Array slicing).
* **Matplotlib:** For visualizing waveforms and frequency spectrums.
* **Wave / SciPy:** For handling binary audio data streams.

##  The Physics
The core logic relies on the principle that noise often resides in high-frequency bands relative to the signal of interest.

1.  **Time-to-Frequency Conversion:** The signal $x(t)$ is transformed into $X(f)$ using the Discrete Fourier Transform.
2.  **Filtering:** A threshold frequency ($f_{cut}$) is defined. Coefficients where $f > f_{cut}$ are zeroed out (Low-Pass Filter).
3.  **reconstruction:** The modified spectrum is transformed back to the time domain using the Inverse Fourier Transform.

$$X_k = \sum_{n=0}^{N-1} x_n \cdot e^{-i 2 \pi k n / N}$$

##  Future Scope
* Implementation of **Butterworth** and **Chebyshev** filters for smoother frequency rolloff (reducing Gibbs phenomenon artifacts).
* Adaptation for **real-time photodetector signal analysis** to improve switching speed measurements in nanowire devices.

---
*Created by **Jithin Govind K** - Physicist & Nanoelectronics Engineer*
