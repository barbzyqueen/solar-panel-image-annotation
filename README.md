# Solar Panel Image Annotation Using Roboflow

A practical image annotation project focused on identifying and annotating individual solar panels using polygon annotations in Roboflow.

## Project Overview

This project involved manually annotating a collection of solar panel images to create a structured dataset for an object detection task.

Using Roboflow, I identified individual solar panels in each image and outlined their visible boundaries with polygon annotations. The project also involved applying consistent class labels, handling partially occluded objects, and reviewing annotations for accuracy.

The final dataset contains 15 images and 177 individual annotations.

**Live Project:** [View Solar Panel Annotation Project on Roboflow Universe](https://universe.roboflow.com/barbaras-workspace-if1sy/solar-panel-yii8h)

## Project Objectives

- Gain practical experience with image annotation and computer vision datasets.
- Identify individual solar panels within images.
- Apply polygon annotations to capture object boundaries.
- Maintain consistent class labelling across the dataset.
- Handle partially visible and occluded objects.
- Export annotations in a standard machine-readable format.

## Tools and Technologies

- **Roboflow:** Image annotation and dataset management.
- **COCO JSON:** Export format for structured annotation data.
- **Polygon Annotation:** Used to outline individual solar panels.

## Dataset Information

| Attribute | Description |
|---|---|
| Project name | Solar Panel |
| Task type | Object Detection |
| Number of images | 15 |
| Total annotations | 177 |
| Annotation method | Manual polygon annotation |
| Active class | Solar-Panel |
| Export format | COCO JSON |
| Dataset version | Version 1 |
| Model training | Not performed |

The images were obtained from publicly available image sources, including Unsplash and Pexels.

Original image files are not included in this repository because of image redistribution and licensing considerations.

## Annotation Methodology

Each image was reviewed individually, and distinguishable solar panels were annotated using polygons.

The annotation process followed these principles:

1. **Individual object identification:** Each distinguishable solar panel was treated as a separate object.
2. **Polygon annotation:** Polygons were drawn along the visible boundaries of individual panels rather than using rectangular bounding boxes.
3. **Consistent labelling:** The same `Solar-Panel` class was applied to all annotated panels.
4. **Partial visibility:** Where panels were obscured by objects such as vegetation or people, annotations followed the visible portions of the panels.
5. **Boundary accuracy:** Polygon outlines were adjusted to follow panel edges and distinguish neighbouring panels.
6. **Image boundaries:** Where panels extended beyond the image frame, only the visible portions were annotated.

## Annotation Guidelines

The following guidelines were used to maintain consistency:

- Annotate each individual solar panel separately.
- Do not annotate individual photovoltaic cells within a panel.
- Do not create separate annotations for mounting clips or other small installation components.
- Exclude objects such as vegetation and people when outlining partially occluded panels.
- Include shadowed portions of a panel when its boundaries remain identifiable.
- Avoid estimating or drawing hidden portions of partially occluded objects.
- Keep neighbouring panel annotations separate by following their visible boundaries.

## Dataset Export

After completing the annotations, I generated the first dataset version in Roboflow.

The dataset was exported in **COCO JSON format**, which stores annotation information, including image references, class information, and polygon segmentation coordinates.

No model was trained as part of this project. The focus was on manual annotation, dataset preparation, and quality review.

## Project Screenshots

### 1. Dataset Overview

![Solar panel dataset overview](screenshots/dataset-overview.png)

Overview of the 15 images in the Roboflow dataset, with annotation overlays enabled.

### 2. Individual Image Annotation

![Individual solar panel annotations](screenshots/individual-annotation.png)

Example of polygon annotations applied to individual solar panels.

### 3. Dataset Version and Export

![Roboflow dataset version](screenshots/dataset-version.png)

The generated dataset version and download interface.

### 4. Class Configuration

![Solar panel class configuration](screenshots/class-configuration.png)

Class configuration showing the `Solar-Panel` label and annotation count.

## Repository Structure

```text
solar-panel-image-annotation/
│
├── README.md
│
├── annotations/
│   └── _annotations.coco.json
│
├── screenshots/
│   ├── dataset-overview.png
│   ├── individual-annotation.png
│   ├── dataset-version.png
│   └── class-configuration.png
│
├── annotation-guidelines.md
│
└── image-sources.md


## Author

**Barbara**

[GitHub Profile](https://github.com/barbzyqueen)
