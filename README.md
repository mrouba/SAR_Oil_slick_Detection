# Chasing Slicks from Space: SAR Oil Detection (Mauritius Incident)

This repository contains a Google Earth Engine (GEE) workflow that uses **Sentinel-1 SAR (Synthetic Aperture Radar)** satellite imagery to automatically detect, map, and filter marine oil spills. 

The pipeline is applied to the Mauritius oil spill incident to show how active radar can trace environmental disasters through changes in ocean surface texture.

---

## 📊 The Results

Below is the multi-temporal analysis showing how the algorithm processes the radar data from a baseline state to the final extracted oil slick mask.

![Multi-Temporal SAR Analysis and Algorithmic Mask](results.jpg)

### Key Findings from the Analysis:
* **Before the Spill (Baseline):** The ambient ocean surface shows normal wind roughness, creating a stable, textured gray radar backscatter ranging from **-10 dB to -15 dB**. This baseline proves the area is naturally rough.
* **During the Spill (Active Incident):** When oil leaks, it smooths the ocean surface and dampens the waves. The water acts like a mirror, reflecting the radar signal away from the satellite. This change in texture creates a sharp, dark anomaly footprint (**≤ -20.5 dB**).
* **Oil Detection (Algorithmic Mask):** By applying a sharp intensity threshold combined with a spatial pixel sieve, random ocean noise is filtered out. This isolates the continuous, connected pixels to accurately detect and map the true oil slick boundaries (**Area > 15 Pixels**).

---

## 🛠️ How the Algorithm Works

The script processes the radar data using a three-phase approach:
1. **Temporal Filtering:** Collects pre-spill and co-spill imagery using Sentinel-1 C-band VV polarization.
2. **Speckle Reduction:** Applies a 45-meter focal median filter to smooth out "salt-and-pepper" radar noise.
3. **Spatial Sieve (Topology Mask):** Uses a 4-connected neighbor analysis to ensure only true, connected bodies of oil are mapped, ignoring transient low-wind spots on the open ocean.

---

## 🚀 How to Use & Access the Code

### 💻 Open Directly in Google Earth Engine
You can view the active live script, change parameters, and run the visualization directly in your browser:
👉 **[Click here to open the GEE Workspace](https://code.earthengine.google.com/227b814e0ff555f9e7280b707adc9540)**

---
contact me on 
mariaroubam@gmail.com  

# Happy Coding!
