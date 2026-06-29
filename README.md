# Neoadjuvant Botensilimab/ Balstilimab for localized mismatch repair proficient  and deficient colon cancer: Results of the NEST phase 2 clinical trial

![](WCM_MB_LOGO_HZSS1L_CLR_RGB_new.png)

## DATA AVAILABILITY

## Samples

| Sample_name | ROI | Condition | MSI  | Naming in figures |
|-------------|-----|-----------|-----|-------------------|
| NEST2-06 | tumor_bed | Responder | Stable | NEST2-06_Resection |
| NEST1-06 | tumor_bed | Responder | High | NEST1-06_Resection |
| NEST1-11 | tumor | Responder | Stable | NEST1-11_Baseline |
| NEST1-04 | tumor | Baseline | Stable | NEST1-04_Baseline |
| NEST1-05 | tumor | Baseline | High | NEST1-05_Baseline |
| NEST1-05 | tumor_bed | Responder | High | NEST1-05_Resection |
| NEST2-04 | tumor | Baseline | Stable | NEST2-04_Baseline |
| NEST1-04 | tumor | Non-responder | Stable | NEST1-04_Resection |
| NEST1-01 | tumor_bed | Responder | Stable | NEST1-01_Resection |
| NEST2-03 | tumor_bed | Responder | Stable | NEST2-03_Resection |
| NEST1-08 | tumor_inner | Non-responder | Stable | NEST1-08_Resection |
| NEST1-11 | tumor_bed | Responder | Stable | NEST1-11_Resection |
| NEST2-06 | tumor | Responder | Stable | NEST2-06_Baseline |
| NEST2-08a | tumor | Responder | Stable | NEST2-08a_Baseline |
| NEST2-01 | tumor_bed | Responder | Stable | NEST2-01_Resection |
| NEST2-04 | tumor_inner | Non-responder | Stable | NEST2-04_Resection |
| NEST2-10 | tumor_inner | Non-responder | Stable | NEST2-10_Resection |



## DATA ANALYSIS

- **Step 1: QC, normalization and probes poisitivity assesment**. From single cell intensity values, exclude cells with the lowest 2% of Area and 2% of DAPI signal. Then for each ROI/probe, generate a binary expression matrix following the 6σ approach. [QC](https://github.com/abcwcm/shah_NEST2025/blob/main/scripts/qc_binary_NEST2-04_tumor_internal.ipynb). We will run this script for each slide/ROI of interest.
- **Step 2: cell annotation**. Using the binary matrix, annotate cells on the positivity of certain markers (probes), and the negativity of the rest of the markers. In a second round of annotation, use VIMENTIN, Podoplanin and SMA probes as neutral probes, so any of the cells can be positive for them. [cell_typing](https://github.com/abcwcm/shah_NEST2025/blob/main/scripts/annotation_NEST2-04_tumor_internal.Rmd).  We will run this script for each slide/ROI of interest.
- **Step 3: cell type characterization and niche identification**. Characterization of cell type composition in eah ROI and identification of cellular niches across all ROI. [ROI_characterization](https://github.com/abcwcm/shah_NEST2025/blob/main/scripts/nov_complete_combine_cell_types_ROIs.ipynb)
- **Step 4: cell type density differences**. With the cell type annotation, normalize cell type counts based on the area of each ROI and apply t-test for each cell type to identify cell type density differences between conditions. [abundances](https://github.com/abcwcm/shah_NEST2025/blob/main/scripts/review_pMMR_Neighborhood_analysis_only_immune_area_norm.ipynb)
- **Step 5: immune proportion differences**. Calculate immune proportions within each sample and apply t-test to identify immune differences between conditions. [immune_diff](https://github.com/abcwcm/shah_NEST2025/blob/main/scripts/review_pMMR_Neighborhood_analysis_only_immune_new.ipynb)
- **Step 6: neighborhood analysis**. Neighborhood analysis to look for differences in the proportion of the different cell types within 50 microns of each cell within the cell type of interest between condtions. [neighborhood](https://github.com/abcwcm/shah_NEST2025/blob/main/scripts/review_pMMR_Neighborhood_analysis_for_all_Celltypes.ipynb)
