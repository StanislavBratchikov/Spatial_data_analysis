# Spatial_data_analysis
This sub-project is aimed to master data analysis skills of spatial transcriptomics data provided by different platforms: Nanostring CosMX, 10x Xenium in-Situ. 
# Motivatoin 
Future projects will include our own spatial transcriptomics data (Nanostring CosMx) that will need to be analysed. In order to train on data handling, be able to run unsupervised clustering, dimension reduction, visualizing tissue sentions and mapping clustering results back to those tissues to explore cell neighborhood it was decided to first try this on open source data from 10x and Nanostring platforms. 
# Open source data 
Two datasets consisting of CosMx data prepared from FFPE (Formalin fixed Paraffin embeded) samples were found: one from lung tissue (Non Small Cell Lung Cancer; NSCLC), and one from liver tissue (healthy and liver cancer patients). More precise description about those two can be found on [Nanostring CosMX webpage](https://nanostring.com/products/cosmx-spatial-molecular-imager/ffpe-dataset/). [A dataset from 10x](https://www.10xgenomics.com/resources/datasets/xenium-ffpe-human-breast-with-custom-add-on-panel-1-standard) is also prepared from FFPE sample of human breast cancer (infiltrating ductal carcinoma). 
# Plan of action
- Run aggregation for all lung CosMx datasets using plain scanpy (no integration) to assess batch effect
- If batch effect is present - run integration using scVI
- Run lung/liver or cosmx/xenium aggregation/integration
- Visualize scVI clusters on spatial images
# Updates 
- Ran Integration using [scVI tool](https://docs.scvi-tools.org/en/stable/index.html).
- Aggregated lung and liver datasets produced a batch effect
- Standard LogNorm and SCTransform produced different results: LogNorm is more prone to batch effect conservation
- Liver CosMx dataset didn't show batch effect
- CosMx lung datasets didn't show batch effect
- Giotto package is bad at handling multiple spatial data samples - it runs out of memmory. 
# Usefull resources 
R: 
- [Seurat](https://satijalab.org/seurat/articles/spatial_vignette_2.html#mouse-brain-10x-genomics-xenium-in-situ): QC, cropping images and cell boundaries, and unsupervised clustering
- [Giotto](https://giottosuite.readthedocs.io/en/latest/subsections/datasets/xenium_breast_cancer.html): add statistics, normalize expression, calculate high variable features, dimension reduction, clustering, and subcellular visualization
- [Voyager](https://pachterlab.github.io/voyager/articles/vig5_xenium.html): QC, spatial autocorrelation of QC metrics, Moran’s I (correlation coefficient, measures how one object is similar to others surrounding it), dimension reduction, differential expression, and local spatial statistics of marker genes 

Python: 
- [StLearn](https://stlearn.readthedocs.io/en/latest/index.html)- (two tutorials, [CCI](https://stlearn.readthedocs.io/en/latest/tutorials/Xenium_CCI.html), [PSTS](https://stlearn.readthedocs.io/en/latest/tutorials/Xenium_PSTS.html)): normalization, gridding, permutation test for high co-expression, [cell-cell interactions](https://stlearn.readthedocs.io/en/latest/tutorials/Xenium_CCI.html), clustering, and [pseudo-time-space spatial trajectory analysis](https://stlearn.readthedocs.io/en/latest/tutorials/Xenium_PSTS.html)
- [SquidPy](https://squidpy.readthedocs.io/en/latest/external_tutorials/tutorial_xenium.html) - QC, dimension reduction, spatial statistics, neighbors enrichment analysis, and compute Moran’s I score

Spatial data anlysis pipelines: 
[Spatial Transcriptomics book](https://pachterlab.github.io/LP_2021/)
