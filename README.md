# Title to be defined

![](WCM_MB_LOGO_HZSS1L_CLR_RGB_new.png)

## DATA AVAILABILITY


## DATA ANALYSIS

- **Step 1: QC, normalization and probes poisitivity assesment**. From single cell intensity values, exclude cells with the lowest 2% of Area and 2% of DAPI signal. Then for each ROI/probe, generate a binary expression matrix following the 6σ approach. [QC]()
- **Step 2: cell type annotation**. Using the binary matrix, annotate cells on the positivity of certain markers (probes), and the negativity of the rest of the markers. In a second round, use VIMENTIN, Podoplanin and SMA probes as neutral probes, so any of the cells can be positive for them. [cell_typing]()
- **Step 3: cell type abundance differences**. With the cell type annotation, normalize cell type counts based on the area of each ROI and apply t-test for each cell type to identify cell type abundance differences between conditions . [abundances]()
- **Step 4: neighborhood analysis**. Neighborhood analysis to look for differences in the proportion of the different cell types within 50 microns of each cell within the cell type of interest between condtions. [neighborhood]()
