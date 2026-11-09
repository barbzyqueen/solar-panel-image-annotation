
# Solar Panel Image Annotation Guidelines

## 1. Purpose

This document describes the annotation guidelines used for the Solar Panel Image Annotation project.

The guidelines were developed to maintain consistency when identifying and annotating individual solar panels across the image dataset.

The project uses manual polygon annotation in Roboflow, with `Solar-Panel` as the object class.

## 2. Class Definition

### Class: `Solar-Panel`

A solar panel refers to an individual photovoltaic module visible in an image.

Each distinguishable panel must be treated as a separate object, even when multiple panels are installed together as part of a larger solar array.

**Annotation rules:**

- Assign the `Solar-Panel` class to every identifiable individual panel.
- Use the same class label throughout the dataset.
- Do not create separate classes for different panel sizes, orientations, or installation locations.
- Do not annotate individual photovoltaic cells within a panel.

## 3. Annotation Method

Polygon annotation is used to outline the visible boundaries of individual solar panels.

Each panel must have its own polygon annotation.

**Annotation rules:**

- Draw polygons along the visible outer boundaries of each panel.
- Follow the shape and orientation of the panel as closely as possible.
- Avoid including unnecessary background areas.
- Keep annotations for neighbouring panels separate.
- Do not use one polygon to represent an entire solar array containing multiple panels.

## 4. Boundary and Visibility Rules

### 4.1 Adjacent Panels

When multiple panels are installed close together:

- Annotate each panel individually.
- Follow the visible seams or boundaries separating neighbouring panels.
- Avoid allowing one polygon to significantly overlap the interior of another panel.
- Where boundaries are difficult to distinguish, follow the most identifiable visible edges.

### 4.2 Partially Visible Panels

When a panel extends beyond the image boundaries:

- Annotate only the portion visible within the image.
- Do not estimate or reconstruct the missing portion outside the image frame.

### 4.3 Partially Obstructed Panels

When objects such as vegetation or people cover part of a solar panel:

- Annotate the visible portions of the panel.
- Exclude the obstructing object from the polygon.
- Follow the visible panel boundaries around the obstruction.
- Do not estimate or draw hidden portions of the panel.

## 5. Occlusion and Shadows

### 5.1 Occlusion

Occlusion occurs when another object partially or completely blocks the view of a solar panel.

Examples include:

- Vegetation covering part of a panel.
- A person standing over or working on a panel.
- Other objects obstructing the panel surface.

Only the identifiable visible portions of the panel should be annotated.

### 5.2 Shadows

Shadows falling across a solar panel do not change its object classification.

- Include shadowed portions when the panel boundaries remain identifiable.
- Do not treat shadows as separate objects.
- Do not exclude a panel simply because part of its surface is darkened by a shadow.

## 6. Objects Excluded from Annotation

The following should not receive separate annotations:

- Individual photovoltaic cells within a panel.
- Mounting clips and small installation components.
- Vegetation covering or surrounding panels.
- People installing or inspecting panels.
- Shadows cast across panel surfaces.
- Background structures such as rooftops and buildings.

The annotation task focuses exclusively on individual solar panels.

## 7. Quality Assurance Checklist

Before completing an image annotation, review the following:

- [ ] Every distinguishable solar panel has been identified.
- [ ] Each panel has an individual polygon annotation.
- [ ] All annotations use the `Solar-Panel` class.
- [ ] Polygon boundaries follow the visible panel edges.
- [ ] Adjacent panels have separate annotations.
- [ ] Occluded panels include only their identifiable visible portions.
- [ ] Shadowed panel surfaces have not been incorrectly excluded.
- [ ] No unrelated objects have been annotated.
- [ ] No unnecessary background areas have been included.

## 8. Annotation Scope and Limitations

These guidelines were developed for a small practice dataset containing 15 images.

The rules reflect the annotation decisions applied during this project. They are intended to promote consistency within this dataset and may require further refinement when applied to larger datasets or images with more complex visual conditions.
