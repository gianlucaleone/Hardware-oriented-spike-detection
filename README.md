# **Spike Detection Pipeline – Simulation & Hardware-Oriented Implementation**

This notebook implements a complete spike-detection pipeline for simulated extracellular recordings.  
It is designed both for algorithm exploration and for preparing hardware-compatible test vectors.

---

## **Overview**

1. **Dataset loading**  
   Import of the Quiroga simulated dataset and extraction of ground-truth spikes.

2. **(Optional) Synthetic LFP generation**  
   Addition of low-frequency LFP components to improve the quality of the testing intracortical signals.

3. **Quantization (8-bit)**  
   Signal normalization and conversion to int8 to match ADC behavior.

4. **Filtering**  
   High-pass filtering using hardware-friendly methods: difference filter, moving average difference filter, or finite impulse response filter.

5. **Spike emphasis**  
   Enhancement using absolute value, non-linear energy operator (NEO/TEO), or amplitude slope operator (ASO) to make spikes easier to detect.

6. **Thresholding & detection**  
   Window-based threshold computation and spike extraction, both mean-value and RMS-value based.

7. **Refractory period**  
Ignore detections for a few samples after each spike.

8. **Accuracy evaluation**  
   True Positive, False Positive, and False Negative computation within a certain tolerance window.

9. **Hardware test export**  
   Generation of text files containing input, output, and internal signals for FPGA/ASIC tests.

---

Use this notebook as a compact reference for developing real-time spike detection algorithms and validating hardware implementations.

Please, cite this work referring to my PhD thesis:

@article{leone2023integrating,  
  title={Integrating biological and artificial neural networks processing on fpgas},  
  author={Leone, Gianluca},  
  year={2023},  
  publisher={Università degli Studi di Cagliari}  
}
