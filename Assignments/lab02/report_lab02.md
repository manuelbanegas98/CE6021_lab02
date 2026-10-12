# Lab Report — Lab 02: MRI Noise Removal via Fourier Notch Filtering

## Overview

The goal of this lab was to remove periodic stripe noise from a corrupted MRI scan by identifying its interference spikes in k-space and applying a Fourier notch filter.

## Implementation

After inspecting the log-magnitude Fourier spectrum, we identified the two symmetric noise peaks at `(148, 147)` and `(108, 109)`. We constructed a notch mask setting circular discs of radius 2 around these frequencies to 0, multiplied the centred k-space data by the mask, and reconstructed the spatial domain image via inverse 2D FFT.

## Results

The notch-filtered image successfully removed the stripe artifact across the scan, matching the clean ground-truth reference with an SSIM of 0.9988 while significantly diverging from the corrupted scan (SSIM of 0.0934).
