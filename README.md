# Sentinel 1 Data-Processing Pipeline with ESA SNAPPY

This repository provides a complete Sentinel-1 Synthetic Aperture Radar (SAR) preprocessing pipeline using ESA's SNAP and its Python API  SNAPPY. The pipeline includes operations such as orbital file correction, IW splitting, calibration, debursting, polarimetric matrix generation, speckle filtering, terrain correction, and polarimetric decomposition.

**Pipeline Overview**

The pipeline covers the following Sentinel-1 preprocessing steps:

- Apply Orbit File – Integrates precise orbital data.
- TOPSAR Split – Splits the SLC product into IW1, IW2, and IW3 swaths.
- Calibration – Radiometric calibration of VH and VV polarizations.
- Deburst – Merges bursts within each IW to create a seamless image.
- TOPSAR Merge – Combines all IW swaths into one product.
- Polarimetric Matrices (C2) – Computes covariance matrix for dual-pol data.
- Speckle Filtering – Applies a refined Lee filter.
- Terrain Correction – Geometrically corrects the image using WGS84 projection.
- Polarimetric Decomposition – Uses H-Alpha Dual Pol Decomposition.
- Write Output – Saves the processed product in BEAM-DIMAP format.

**Directory Structure**


   ```bash
   Sentinel-1-Data-Processing-Pipeline-with-ESA-SNAPPY/
│
├── main.py                  # Main script to execute the full pipeline
├── README.md                # Project documentation
└── requirements.txt         # Python dependencies (to be created)
   ```

**Getting Started**

Prerequisites
- SNAP Desktop
- Python 3.x
- ESA SNAPPY Python bindings
  
Make sure snappy is properly configured and its path is added in the script:

   ```bash
sys.path.append(r'C:\Users\YOUR_USERNAME\.snap\snap-python')

   ```

**How to Run**

   ```bash
python main.py --input_path "xxxxxx.zip" --output_path "yyyyyy.BEAM-DIMAP"

   ```

**References**

Checkout the original repo for more info

   ```bash
https://github.com/senbox-org/esa-snappy.git

   ```

