# Ultrasonic Guided Wave Dataset

This repository contains the ultrasonic guided wave dataset used for damage identification in composite structures. The dataset is derived from the publication:

> **Deep learning uncertainty quantification for ultrasonic damage identification in composite structures**  
> Houyu Lu, Sergio Cantero Chinchilla, Xin Yang, Konstantinos Gryllias, Dimitrios Chronopoulos  
> *Composite Structures, 2024*  
> [DOI: 10.1016/j.compstruct.2024.118087](https://doi.org/10.1016/j.compstruct.2024.118087)

## Dataset Structure

### OOD (Out-of-Distribution) Data
- `10dB_normalized_damage_0.2_0.3.csv`: Signals with SNR 10 dB for damage range [0.2, 0.3].
- `5dB_normalized_damage_0.7_0.8.csv`: Signals with SNR 5 dB for damage range [0.7, 0.8].
- `Noise_free_damage_0_1.csv`: Noise-free signals for damage range [0, 1].

### ID (In-Distribution) Data
- `Averaged_10dB_damage_0_1.csv`: Averaged signals with SNR 10 dB for damage range [0, 1].

## Usage

The dataset is preprocessed and normalized for ease of analysis:
- Signal amplitudes are normalized to [-1, 1].
- Damage locations are normalized to [0, 1].

### How to Cite
If you use this dataset in your research, please cite the following paper:

