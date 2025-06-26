HER2-IHC-40x: High-Resolution Histopathology Datasets for HER2 IHC Scoring
 

Overview
This dataset contains high-resolution histopathological images of HER2-stained breast cancer tissue sections. Designed for deep learning-based HER2 scoring, the dataset includes two variants:
HER2-IHC-40x: Patches extracted after splitting WSIs.
HER2-IHC-40x-WSI: Patches extracted before splitting.
Each image patch is categorized into one of four HER2 classes (0, 1+, 2+, 3+), based on staining intensity.
 

Dataset Contents
Dataset Variants
1. HER2-IHC-40x
WSI-based 80-20 split before patch extraction.
107 WSIs → 9940 patches (8093 train / 1847 test)
2. HER2-IHC-40x-WSI
Patch-based 80-20 split after patch extraction.
107 WSIs → 10,997 patches (8897 train / 2200 test)
 

Folder Structure
HER2-IHC-40x/
├── WSI/              # Original Whole Slide Images (.svs)
├── ROI/              # Expert-annotated tumor regions (.png)
├── Patches/       # 1024x1024 image patches, labeled 0, 1+, 2+, 3+
├── Train/           # 80% training set
└── Test/            # 20% test set
 

HER2-IHC-40x-WSI/
├── Patches/
├── Train/
└── Test/
 
 

HER2 Class Definitions
 

| HER2 Score | Description                                                                 
|----------|-----------------------------------------------------------------------------
| 0           | No observable staining                                                                      
| 1+         | Weak/incomplete membrane staining in ≤10% tumor cells                       
| 2+         | Moderate circumferential staining in >10% tumor cells (Equivocal)           
| 3+         | Strong circumferential staining in >10% tumor cells (Positive)              
 

Preprocessing & Quality Control
ROI Selection: Manual annotation by expert pathologists using Cytomine.
Color Histogram Filtering: Removed non-tumor/low-quality patches using HSV filtering.
Normalization: Intensity normalization across all patches.
Patch Extraction: Adaptive 1024×1024 extraction using sliding window method.
 

Usage
This dataset is suitable for:
HER2 scoring automation using deep learning
Explainable AI (Grad-CAM, attention models)
Color normalization and domain adaptation
Model benchmarking and generalization research
 

Dataset Statistics
 
HER2-IHC-40x (WSI Split)
| HER2 Class | WSIs | ROIs | Patches |
|----------|------|----- -|---------|
| 0            | 23   | 429   | 3789    |
| 1+         | 26   | 131   | 2153    |
| 2+         | 27   | 483   | 634     |
| 3+         | 31   | 156   | 3364    |
| Total      | 107 | 1199 | 9940    |
 

HER2-IHC-40x (Patch Split)
| HER2 Class | WSIs | ROIs | Patches |
|----------|-----|--------|---------|
| 0           | 23   | 429     | 3789    |
| 1+         | 26   | 131    | 2689    |
| 2+         | 27   | 483    | 1131    |
| 3+         | 31   | 156    | 3388    |
| Total      | 107  | 1199 | 10,997  |
 


Link: https://zenodo.org/records/15179608

Citation
If you use this dataset, please cite:
```bibtex
@dataset{nabi2025her2,
  author       = {Md Serajun Nabi and Mohammad Faizal Ahmad Fauzi and Hezerul Bin Abdul Karim and Phaik Leng Cheah and Seow Fan Chiew and Lai Meng Looi},
  title        = {HER2-IHC-40x and HER2-IHC-40x-WSI: High-Resolution Histopathology Dataset for HER2 IHC Scoring in Breast Cancer},
  year         = 2025,
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.15179608},
  url          = {https://zenodo.org/record/xxxxxxx}
}
 
 
This dataset is part of the research article:
**"Enhancing HER2 IHC Scoring Using HRNet and SwinT with Cross-Dataset Generalization"**  
Authors: Md Serajun Nabi, Mohammad Faizal Ahmad Fauzi, Hezerul Bin Abdul Karim, et al.  
(Preprint server or journal details to be confirmed.)
 
Search the paper for detail data description:
**HER2-IHC-40x: High-Resolution Histopathology Datasets for HER2 IHC Scoring**
The color histogram code source:
* https://github.com/seraju77/HER2-IHC-40x-data-preprocessing.git *
