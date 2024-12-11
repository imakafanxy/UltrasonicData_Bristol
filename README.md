# Ultrasonic Guided Wave Dataset for Delamination Damage Identification

This repository contains the ultrasonic guided wave dataset used for identifying delamination damage in composite structures. The dataset is derived from the publication:

> **Deep learning uncertainty quantification for ultrasonic damage identification in composite structures**  
> Houyu Lu, Sergio Cantero Chinchilla, Xin Yang, Konstantinos Gryllias, Dimitrios Chronopoulos  
> *Composite Structures, 2024*  
> [DOI: 10.1016/j.compstruct.2024.118087](https://doi.org/10.1016/j.compstruct.2024.118087)

## Dataset Overview

The dataset includes raw ultrasonic guided-wave signals with consistent excitation components removed, leaving only the sections exhibiting significant variations. The dataset has been normalized for amplitude and damage location to avoid scale-related biases.

### Key Features
1. **Amplitude Normalization**:
   - All waveform signals are normalized to the range of [-1, 1].
2. **Damage Location Normalization**:
   - Damage locations are normalized to [0, 1], representing the range of 30cm to 70cm, in 5mm increments.
3. **Categorized Data**:
   - Includes both Out-of-Distribution (OOD) and In-Distribution (ID) datasets with varying noise levels and experimental conditions.

---

## Dataset Structure

### Files and Descriptions

1. **`Averaged 10dB normalized delamination damage position at 0 to 1.csv`**
   - **Description**: Averaged signals for each damage location with SNR = 10dB.
   - **Details**:
     - Damage location: Full range ([0, 1]).
     - Signals are averaged over 30 measurements at each location, simulating real-world experimental de-noising.
   - **Use Case**: Ideal for testing machine learning models under averaged conditions.

2. **`10dB normalized delamination damage position at 0.2 to 0.3 and 5dB at 0.7 to 0.8.csv`**
   - **Description**: Signals for specific damage locations under varying noise conditions.
   - **Details**:
     - Damage location: [0.2, 0.3] (SNR = 10dB) and [0.7, 0.8] (SNR = 5dB).
     - Represents out-of-distribution (OOD) data for robustness testing.
   - **Use Case**: Evaluating model performance under challenging noise levels.

3. **`Noise-free normalized delamination damage position at 0 to 1.csv`**
   - **Description**: Ideal signals with no noise interference.
   - **Details**:
     - Damage location: Full range ([0, 1]).
     - Baseline dataset for comparison with noisy signals.
   - **Use Case**: Benchmarking and baseline comparisons.

---

## Usage

The dataset is preprocessed and ready for use in signal processing, machine learning, and uncertainty quantification studies. Below are potential applications:

1. **Signal Processing**:
   - Analyzing normalized signals to detect delamination damage.
2. **Machine Learning**:
   - Training and evaluating models for damage localization and prediction.
3. **Noise Analysis**:
   - Studying the effect of varying noise levels on damage detection accuracy.

---

## Experimental Setup

The data was generated using a transient ultrasonic guided wave propagation model and validated with finite element method (FEM) simulations. Details include:

- **Wave Propagation Model**:
  - FEM simulations performed in Abaqus.
  - Solid elements (C3D8R) with dimensions 0.5mm × 0.5mm × 0.2mm.
- **Ultrasonic Signal**:
  - Excitation: 6-cycle Hanning-windowed sinusoid at 100kHz.
  - Sensor: Positioned 0.2m from the excitation point, measuring for 720μs.
  - Mode: First antisymmetric mode (A0).
- **Composite Structure**:
  - Cross-ply carbon fibre beam with [0_{2}/90]_s stacking sequence.
  - Dimensions: 1m × 3mm × 2mm.
  - Delamination: 5mm long, located at L mm from the excitation point.

---



Ultrasound Signal Generator: A 6-cycle Hanning-windowed sinusoidal waveform centered at 100 kHz was used to excite the beam in the vertical direction at one end.

Sensor Location and Measurement Time: A sensor was positioned 0.2 m away from the excitation point, and data was collected for a duration of 720 μs.

Wave Mode: The first antisymmetric mode (A0) was excited.

Composite Beam Specifications: A cross-ply carbon fiber composite beam with dimensions of 1 m × 3 mm × 2 mm was utilized, with a stacking sequence of [0₂/90]ₛ.

Damage Modeling: Delamination damage, measuring 5 mm in length, was modeled at a specific location (L mm) within the beam.

