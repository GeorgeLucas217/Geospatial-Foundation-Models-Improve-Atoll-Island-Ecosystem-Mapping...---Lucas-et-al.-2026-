# Geospatial-Foundation-Models-Improve-Atoll-Island-Ecosystem-Mapping...---Lucas-et-al.-2026-

---

code for repeating the analysis presented in "Geospatial Foundation Models Improve Atoll Island Ecosystem Mapping A Case Study using AlphaEarth Embeddings" by Lucas, Cresswell, Duce, Young, Shan, and Murray

Accurate ecosystem mapping is essential for protecting ecosystems around the world. Geospatial Foundation Models (GeoFMs) appear to provide an improved ability to detect ecosystems over traditional approaches. In this study, we investigate whether the use of embeddings from Google’s AlphaEarth Foundations model yields improvements to ecosystem maps developed in the Republic of Maldives compared to Sentinel-2 satellite imagery. 

---

## Instructions
The correct order for the code to be run is as follows:

### 1 - Study Site Extraction - RStudio: 
This code takes shapefiles from the Government of Maldives' official map of islands and reefs and randomly selects 20 (one within each administrative atoll) using a seed (for repeatability). Running this code will return a shapefile of the 20 study sites used in this analysis.

### 2 - Generating Training Points - Google Earth Engine:
This code takes the study sites extracted in the previous step and generates training points ready for annotation. These points are split 60:40 between land and water, which is achieved by calculating the Normalised Difference Water Index using Sentinel-2 satellite imagery.

### 3 - Validation Points Parts 1 and 2 - Google Earth Engine: 
This code generates training points that are ready for annotation. The land/water split is applied again here, but further calculations are done to try to represent all ecosystem types. The code is split into two parts due to its large computing requirements.

### 4 - Annotating Training and Validation Points:
This step can be conducted in QGIS, ArcGIS, OlmoEarth or any other software that allows you to annotate spatial point data. The annotated points used in this study are available as a Google Earth Engine asset.

### 5 - Running Models and Displaying Classification Maps - Google Earth Engine:
This code takes the annotated training points and runs Random Forest classification models over AlphaEarth Foundations and Sentinel-2 imagery, then displays these side by side. A confusion matrix (necessary for per-class accuracy analysis) and probability values (necessary for the confidence analysis) are also generated in this code.

### 6 - Confusion Matrix - Microsoft Excel:
To prepare for the Per-class accuracy analysis, the confusion matrix must be assembled and neatened in Microsoft excel. Producers' accuracy is used for per-class accuracy, and is calculated as the proportion of correctly classified reference sites compared to the total number of reference sites. Here is a useful guide: https://gsp.humboldt.edu/olm/courses/GSP_216/lessons/accuracy/metrics.html 

### 7 - Accuracies and Confidences - RStudio:
This code generates graphs for producer's accuracy, confidence against producer's accuracy, confidence against the number of training points (per-class), and producer's accuracy against the number of training points (per class).

### 8 - Class Reduction Scenarios I-VI - Google Earth Engine:
This code repeats the ecosystem classification conducted in step 5 on decreasing numbers of classes (for detail on the meanings of the different scenarios, please view the methods section of the manuscript). Separate codes are used for each scenario as this was found to be the most efficient approach. 

### 9 - Class Reduction - RStudio:
Finally, this code takes the overall accuracies calculated in step 8 and plots them.

---

## Contact
For any questions related to the code or manuscript, please contact George Lucas at george.lucas@anu.edu.au

---

## Citation
to cite this research, please use:
> Lucas, G.W., Cresswell B.J., Duce S., Young A.R., Shan A., Murray N.J. (2026). *Geospatial Foundation Models Improve Atoll Island Ecosystem Mapping A Case Study using AlphaEarth Embeddings*

---

## License

The content of this repository is licensed under dual terms to balance open code reuse with intellectual property protection for the manuscript:

* **Code:** All source code and scripts are dedicated to the public domain under the **Creative Commons CC0 1.0 Universal License** ([CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/)).
* **Manuscript & Results:** The text of the manuscript, figures, and research outcomes are licensed under the **Creative Commons Attribution-NonCommercial 4.0 International License** ([CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)).

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/) &nbsp; [![CC BY-NC](https://licensebuttons.net/l/by-nc/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc/4.0/)

---

## Authors
George W. Lucas<sup>1</sup>, Benjamin J. Cresswell<sup>1</sup>, Stephanie Duce<sup>1</sup>, Alys R. Young<sup>1</sup>, Ahmed Shan<sup>2</sup>, Nicholas J. Murray<sup>1</sup>
### Affiliations
<sup>1</sup> College of Science and Engineering, James Cook University, Townsville QLD 4811, Australia 
<sup>2</sup> Maldives, Ministry of Tourism and Environment  

### Coresponding Author
**George Lucas** * Email: george.lucas@anu.edu.au
