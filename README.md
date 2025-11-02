# Design and Analysis of a Custom Optimizer Using Signal Processing Principles

## PROJECT OVERVIEW:

This project applies **Signals and Communication Systems (SCS)** concepts to analyze and redesign the internal behavior of machine learning optimizers.
Instead of viewing the optimizer as a purely mathematical routine, we interpret it as a **signal processing system** that filters a time-varying input — the gradient signal — into stable weight updates.

By treating optimizer updates as **time-domain signals**, we can use classical SCS tools such as Fourier Transform, Power Spectral Density, and filtering theory to understand how noise and useful learning information propagate through the system.
Building on this understanding, we design a **custom optimizer** that behaves like an adaptive low-pass filter, reducing high-frequency noise (unstable updates) while preserving low-frequency learning trends.
This bridges the gap between signal-processing theory and machine-learning optimization.

---

## OBJECTIVES:

1. Model the **gradient update process** in a neural network as a **discrete-time signal**.
2. Use **signal-processing principles** (Fourier Transform, Convolution, Filtering, Modulation) to analyze how optimizers process that signal.
3. Identify high-frequency noise patterns in optimizer updates using **Power Spectral Density (PSD)** analysis.
4. Design a **frequency-aware optimizer** that adaptively filters out noise and stabilizes training.
5. Validate the proposed optimizer through **time-domain and frequency-domain simulations** on benchmark datasets (MNIST).

---

## SCS CONCEPTS USED:

This project builds directly on core concepts from the **Signals and Communication Systems** course:

1. **Signal Representation:**
   The sequence of gradients generated during training is treated as a discrete-time signal ( g(t) ). Each gradient update represents a sample in time.

2. **LTI System Modeling:**
   The optimizer is modeled as a **Linear Time-Invariant system** that takes gradient signals as input and outputs smoother weight updates. The update rule of the optimizer can be interpreted as a convolution operation.

3. **Fourier Transform and Frequency Response:**
   Fourier analysis is used to transform the gradient signal from the time domain to the frequency domain, helping us identify the frequency components (smooth vs. noisy parts) of the learning process.

4. **Power Spectral Density (PSD):**
   PSD is computed to measure how much “energy” (variance) is present at different frequency components of the gradient signal. High PSD at high frequencies indicates jittery or unstable learning.

5. **Filtering Concept:**
   The custom optimizer acts as an **adaptive low-pass filter**, which passes stable, low-frequency learning signals and suppresses high-frequency noise that causes overfitting or instability.

6. **Stationarity and Stability:**
   By analyzing whether the statistical properties of gradient signals remain consistent over time, we study the optimizer’s stability and stationarity — essential conditions for reliable convergence.

7. **Correlation Analysis:**
   Autocorrelation is used to check if the optimizer retains memory of past updates (temporal dependency), while cross-correlation compares signals from different layers or epochs to measure synchronization.

---

## MODELING ASSUMPTIONS

* The gradient sequence ( g_t ) behaves as a **discrete-time signal** that can be analyzed in both time and frequency domains.
* Within small training intervals, the gradient process is **Wide-Sense Stationary (WSS)**, meaning its mean and autocorrelation remain locally constant.
* The optimizer behaves approximately as an **LTI system** for small weight perturbations, allowing convolution and frequency-domain analysis.
* Gradient updates can be decomposed into **signal (useful learning direction)** and **noise (random oscillations)**.
* The **training process** can be interpreted as transmitting a signal (learning information) through a noisy communication channel (gradient noise).

---

## CONNECTION TO COMMUNICATION THEORY

| Communication Theory Concept    | Optimizer Analogy                                         |
| ------------------------------- | --------------------------------------------------------- |
| **Input signal**                | Sequence of gradients ( g(t) )                            |
| **Channel noise**               | Random fluctuations due to mini-batches and data variance |
| **Filter / Equalizer**          | The optimizer (e.g., Adam or our custom one)              |
| **Output signal**               | Weight updates ( w(t) )                                   |
| **SNR (Signal-to-Noise Ratio)** | Ratio of stable gradient energy to noise energy           |
| **Low-pass filter**             | Suppresses noisy high-frequency components in updates     |
| **Modulation**                  | Varying learning rate and momentum parameters over time   |

By using this analogy, the project demonstrates how communication and signal-processing methods can describe and improve machine-learning optimization.

---

## RESULTS AND VALIDATION:

1. **Time-Domain Observation:**
   Gradient signals before and after optimization show reduced oscillation amplitude and smoother convergence.

2. **Frequency-Domain Observation:**
   The PSD of gradients under the custom optimizer exhibits lower high-frequency energy compared to standard Adam, confirming effective noise suppression.

3. **Training Performance:**
   The proposed optimizer achieves comparable accuracy to Adam but with smoother and more stable learning curves — resembling a well-designed communication filter that maximizes signal clarity.

---

## FUTURE EXTENSION:

* Extend to **adaptive spectral filtering**, where the optimizer dynamically adjusts its frequency cutoff during training.
* Study **phase response** to understand how delay in weight updates affects learning speed.
* Integrate **modulation-inspired techniques** (like varying learning rate analogous to AM/FM) for dynamic control of learning speed.

---

## SUMMARY:

This project unifies **machine learning optimization** and **signal processing theory** by treating the optimizer as a system that processes gradient signals over time.
Using SCS concepts such as Fourier Transform, PSD, correlation, and filtering, the project develops a frequency-domain understanding of learning dynamics and designs a custom optimizer that filters out noise for smoother and more efficient convergence.

---

Would you like me to format this into a **ready-to-submit README.md** file (Markdown syntax, proper math formatting for GitHub/VS Code), or a **PDF version** for documentation submission?
