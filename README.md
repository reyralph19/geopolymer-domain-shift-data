# Dataset and Machine Learning Code for Domain Shift Analysis in Philippine Geopolymer Concrete

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)

## Overview
This repository contains the datasets and machine learning code used to analyze the phenomenon of domain shift in geopolymer concrete. The study compares standard geopolymer concrete mixtures synthesized from highly reactive, spherical Class F fly ash against indigenous and recycled Philippine waste streams (e.g., angular volcanic ash, iron-rich nickel-laterite mine waste, and gold-mine tailings). 

The repository consists of two distinct datasets:
1. **Global Training Dataset** ($n=657$): Aggregated from peer-reviewed literature predominantly comprising standard Class F fly ash geopolymers.
2. **Local Philippine Dataset** ($n=173$): Curated from local materials. *(Note: The raw collection contained 175 samples, but 2 invalid/incomplete rows were removed to ensure data integrity).*

## Repository Contents
* `geopol_data.xlsx` - The primary Global Training Dataset ($n=657$).
* `expanded_philippine_data.csv` - The novel Local Philippine Dataset testing domain shift ($n=173$).
* `geopolymerPH.ipynb` - The Jupyter Notebook containing the data preprocessing, machine learning models, and domain shift analysis.

## Data Dictionary
A total of 23 continuous numerical features (plus categorical identifiers) were extracted for each sample. The features are defined as follows:

### 1. General Info & Curing
* **Reference**: Author and Year of the source study.
* **Precursor_Type**: Specific material distinctions (e.g., Fly Ash, Volcanic Ash, Mine Waste, Slag).
* **Curing_Temp_C**: Oven curing temperature in Celsius (Ambient is recorded as 25).
* **Curing_Time_h**: Oven curing time in hours (Ambient is recorded as 0).
* **Age_Days**: Age of the sample at testing (e.g., 7, 28, 90).

### 2. Absolute Mix Weights
* **Precursor_kg_m3**: Mass of the base precursor/binder material in kg/m³.
* **Fine_Agg_kg_m3**: Mass of fine aggregates (e.g., sand) in kg/m³ (recorded as 0 for pastes).
* **Coarse_Agg_kg_m3**: Mass of coarse aggregates (e.g., gravel/crushed stone) in kg/m³ (recorded as 0 for pastes/mortars).
* **NaOH_kg_m3**: Mass of the Sodium Hydroxide solution used in the mixture in kg/m³.
* **Na2SiO3_kg_m3**: Mass of the Sodium Silicate solution used in the mixture in kg/m³.

### 3. Mix Ratios
* **Molarity_NaOH**: Molarity of the NaOH solution.
* **SS_SH_Ratio**: Mass ratio of Sodium Silicate to Sodium Hydroxide.
* **l_b_Ratio**: Liquid-to-binder mass ratio (or Water-to-binder ratio).
* **Sand_Binder_Ratio**: Mass ratio of fine aggregates to precursor binder (recorded as 0 for pastes).
* **Si_Al_Ratio**: Calculated mass ratio of Silicon Dioxide (SiO2) to Aluminum Oxide (Al2O3) based on the precursor's XRF chemistry.

### 4. Full XRF Chemistry
* **SiO2_%**: Total Silica
* **Al2O3_%**: Total Alumina
* **Fe2O3_%**: Total Iron Oxide
* **CaO_%**: Total Calcium Oxide
* **MgO_%**: Total Magnesium Oxide
* **Na2O_%**: Total Sodium Oxide
* **K2O_%**: Total Potassium Oxide

### 5. Physical & Microstructural Properties
* **D50_um**: Median particle size of the precursor in micrometers.
* **SSA_m2_kg**: Specific Surface Area / Blaine fineness in m²/kg.
* **Amorphous_Phase_%**: Percentage of amorphous/glassy content vs crystalline content (derived from XRD/Rietveld analysis; recorded as NaN if not reported).

### 6. Target Variable
* **Strength_MPa**: The final compressive strength in MPa.

## Usage Instructions (Google Colab)
The machine learning pipeline was designed to be run in Google Colab. To execute the code:

1. Download `geopol_data.xlsx`, `expanded_philippine_data.csv`, and `geopolymerPH.ipynb` to your local machine.
2. Open Google Colab and upload the `geopolymerPH.ipynb` notebook.
3. In the Colab environment, open the left-hand sidebar and click on the "Files" folder icon.
4. Upload both dataset files (`geopol_data.xlsx` and `expanded_philippine_data.csv`) directly into the Colab session storage.
5. Run the notebook cells sequentially. Ensure that the file paths in the `pandas.read_csv()` and `pandas.read_excel()` functions match the uploaded file names.

## Citation
If you use this dataset or code in your research, please cite the DOI provided at the top of this document.
