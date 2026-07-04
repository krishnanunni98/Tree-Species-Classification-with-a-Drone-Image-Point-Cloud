# Tree Species Classification with a Drone Image Point Cloud

## Project Overview

This project uses a drone-derived photogrammetric point cloud from the Jyrinvaara conservation area to classify tree species. The workflow includes point-cloud generation with WebODM, empirical height correction using an ALS-based DTM, crown segmentation from a CHM, extraction of crown-level structural and RGB predictors, and LDA-based tree species classification. 

## Objectives

- Generate a photogrammetric point cloud from drone imagery.
- Compare empirical and theoretical height corrections.
- Normalize point-cloud heights using an ALS-based DTM.
- Segment individual tree crowns from the CHM.
- Extract crown-level predictors for species classification.
- Classify tree species using LDA. 

## Data

- Drone images from Jyrinvaara, Lieksa
- `jyrinvaara_dtm.tif` — ALS-based DTM
- `wgs84-n2000_heights.tif` — geoid height-difference raster
- `jyrinvaara_trees.csv` — reference tree data
- `Lieksa-6-13-2019-orthophoto.tif` — orthophoto
- `Lieksa-6-13-2019-georeferenced_model.laz` — photogrammetric point cloud :contentReference[oaicite:12]{index=12}

## Methodology

### Point Cloud Generation
- Processed 36 drone images in WebODM.
- Generated a georeferenced point cloud, orthophoto, and textured 3D model.
- Inspected the point cloud and orthomosaic for suitability in tree species analysis. :contentReference[oaicite:13]{index=13}

### Height Correction and Normalization
- Compared the point-cloud road elevation with the ALS-derived DTM.
- Derived an empirical correction factor and compared it with the theoretical N2000 correction raster.
- Normalized the point cloud heights to N2000 and then to ground level. 

### Crown Segmentation
- Built a canopy height model.
- Detected tree tops.
- Applied marker-controlled watershed segmentation to delineate individual crowns.
- Visually assessed the segmentation quality using the CHM and orthomosaic. 

### Species Classification
- Computed crown-level predictors from relative height distributions and RGB tonal statistics.
- Trained an LDA model using selected predictors.
- Evaluated classification performance with a discriminant plot and error matrix. 

## Main Outputs

- WebODM point cloud
- Orthophoto and textured 3D model
- Empirical height-correction estimate
- CHM and crown-segmentation map
- LDA discriminant plot
- Error matrix and overall accuracy
- Discriminant-function equations 

## Key Results

The report documented an empirical road-based correction of **29.1 m** and a theoretical correction of **16.38 m**. The final LDA model achieved an overall accuracy of about **91%**, with the report showing that the final five-predictor model gave the best balance between accuracy and complexity. :contentReference[oaicite:18]{index=18}

## Skills Demonstrated

- Drone photogrammetry
- WebODM processing
- Geometric height correction
- Crown segmentation
- Crown-level feature engineering
- Linear discriminant analysis
- Tree species classification
- Visual validation of remote-sensing outputs 

