# Quantification of Nuclear Translocation of ERK1/2

## Overview

This project involves the quantification of nuclear translocation of ERK1/2 using image processing techniques. The analysis is performed on images of cells stained for ERK and nuclei, and involves segmenting the nuclei and quantifying the ERK signal within and around the nucleus.

## Requirements

To run the analysis, you need the following Python packages:

- `numpy`
- `pandas`
- `skimage`
- `scipy`
- `tqdm`
- `jupyterlab`

You can install these packages using pip:

```bash
pip install -r requirements.txt
```

### Python Version

Ensure you are using Python version 3.12.7 for compatibility with the code.

## Data Structure

- **Raw Data Folder**: `./data/raw/`
- **Processed Data Folder**: `./data/processed/`
- **Quantified Data Folder**: `./data/quantified/`

Ensure that the raw data folder contains images named according to the conditions specified in the script.

## Parameters

- **Image Dimensions**: 1024 x 1360
- **Conditions**: `Ctrl`, `Go`, `Go pma`, `Go pn`, `Pma`, `Pn`
- **Channels**: ERK channel (Green) = 1, Nucleus channel (Blue) = 2
- **Image Quantification Parameters**:
  - Region extension distances: 1 and 4
- **Data Post-processing / Filtering**:
  - Nucleus area: min = 250, max = 3000
  - Nucleus eccentricity: 0.7
  - Threshold: 4.0

## Functions

### Image Processing

- **load_image_pair**: Loads a pair of images for ERK and nucleus.
- **select_image_channel**: Selects a specific channel from an image.
- **convert_image_to_uint8**: Converts an image to uint8 format.
- **stretch_image_contrast**: Stretches the contrast of an image.
- **preprocess_image_pair**: Preprocesses a pair of images for analysis.

### Segmentation

- **segment_nuclei**: Segments nuclei from an image.
- **identify_nuclei**: Identifies nuclei and expands regions for analysis.
- **segment_ekr_staining**: Segments ERK staining from an image.

### Quantification

- **create_image_from_region**: Creates an image from a region.
- **create_nucleus_expansion_ring**: Creates a ring around the nucleus for quantification.

## Workflow

1. **Load Image Pairs**: Load ERK and nucleus images for each condition.
2. **Preprocess Images**: Convert images to uint8 and stretch contrast.
3. **Segment Images**: Segment nuclei and ERK staining.
4. **Identify Nuclei**: Identify and expand nuclei regions.
5. **Quantify ERK Signal**: Quantify ERK signal within and around the nucleus.
6. **Save Results**: Save processed images and quantified data.

## Output

- **Processed Images**: Saved as PNG files in the processed data folder.
- **Quantified Data**: Saved as Parquet files in the processed data folder.

## Usage

Run the script in a Jupyter Notebook or Python environment to perform the analysis. Ensure that the raw data folder is correctly set up with the required images.

## Notes

- The script suppresses warnings for cleaner output.

This README provides a comprehensive guide to understanding and executing the quantification of nuclear translocation of ERK1/2 using the provided Jupyter Notebook script.
