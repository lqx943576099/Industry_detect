# Industry_detect

RGB-D industrial fastener dataset and visual dimension-estimation benchmark for
tabletop-referenced metrology of bolts and washers under oblique views.

## Overview

This repository provides the dataset download information for the
**Industry_detect** dataset, which supports research on industrial fastener
detection, geometric keypoint extraction, and physical dimension estimation.
The dataset is designed for RGB-D based measurement scenarios where metallic
fasteners may produce specular reflection, depth holes, and unstable boundary
depth values.

The associated paper studies a tabletop-referenced visual metrology framework
that estimates bolt and washer dimensions from RGB-derived OBB keypoints rather
than relying on unreliable metallic-edge depth.

## Method Pipeline

![Pipeline](assets/pipeline.png)

The framework contains five main stages:

1. **Tabletop metric rectification**  
   The tabletop plane is used as a metric reference. Square tabletops are
   rectified through quadrilateral regularization, while circular tabletops use
   contour extraction, plane fitting, and circle-based metric recovery.

2. **Fastener detection and ROI refinement**  
   Oriented bounding boxes (OBBs) are detected for bolts and washers. For
   washers, a secondary ROI-based detector refines the inner-hole localization.

3. **Keypoint construction and homography projection**  
   OBB-derived structural keypoints are projected into the rectified metric
   tabletop domain.

4. **Metric-domain dimension computation**  
   Bolt length and diameter, washer outer and inner diameters, and tabletop
   referenced centers are computed in the metric domain.

5. **Hierarchical geometric error correction (HGEC)**  
   For bolts, HGEC compensates for non-coplanarity between the bolt axis and
   the tabletop reference plane, reducing systematic projection bias under
   oblique views.

## Dataset

The dataset is shared through Baidu Netdisk:

- Dataset name: `Industry_detect`
- Download link: https://pan.baidu.com/s/1TCulCazeRk3YwJ9xaFgL6w?pwd=niwu
- Extraction code: `niwu`

The dataset contains RGB-D images of industrial fasteners captured under
tabletop scenes. It can be used for OBB detector training, fastener localization,
and dimension-estimation evaluation.

## Intended Use

This dataset is intended for academic research on:

- Industrial visual metrology
- RGB-D fastener detection
- Oriented object detection
- Tabletop-referenced dimension estimation
- Robust measurement under metallic reflection and depth noise

## Citation

If you use this dataset or the associated framework in academic work, please
cite the corresponding paper after publication.

## License

This repository is intended for open research use. Please check the dataset
license or contact the dataset maintainer before commercial use.
