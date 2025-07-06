# Sentinel 1 Data-Processing Pipeline with ESA SNAPPY

This repository provides a complete Sentinel-1 Synthetic Aperture Radar (SAR) preprocessing pipeline using ESA's SNAP and its Python API  SNAPPY. The pipeline includes operations such as orbital file correction, IW splitting, calibration, debursting, polarimetric matrix generation, speckle filtering, terrain correction, and polarimetric decomposition.

----

**Pipeline Overview**

The pipeline covers the following Sentinel-1 preprocessing steps:

![image alt](https://github.com/AnandaKrishnan11/Sentinel-1-Data-Processing-Pipeline-with-ESA-SNAPPY/blob/133c45d031e6861d7e210a27050e42229bc423a6/Processing_pipeline.png)

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

----

**Directory Structure**


   ```bash
   Sentinel-1-Data-Processing-Pipeline-with-ESA-SNAPPY/
│
├── main.py                  # Main script to execute the full pipeline
├── README.md                # Project documentation
└──Processing_pipeline.png   # Workflow builder 
   ```
----

**Getting Started**

Prerequisites
- SNAP Desktop
- Python 2.7, 3.3 to 3.10
- ESA SNAPPY Python bindings
  
Make sure snappy is properly configured and its path is added in the script: 

   ```bash
sys.path.append(r'C:\Users\YOUR_USERNAME\.snap\snap-python')

   ```
----

**How to Run**

   ```bash
python main.py --input_path "xxxxxx.zip" --output_path "yyyyyy.BEAM-DIMAP"

   ```
----

**References**

Checkout the original repo for more info

   ```bash
https://github.com/senbox-org/esa-snappy.git

   ```
For configuration details
   ```bash
[https://github.com/senbox-org/esa-snappy.git](https://senbox.atlassian.net/wiki/spaces/SNAP/pages/2499051521/Configure+Python+to+use+the+SNAP-Python+esa_snappy+interface+SNAP+version+10)
   ```

