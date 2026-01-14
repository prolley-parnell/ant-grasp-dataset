---
layout: index
title: About
name: Home
sidebar_link: true
sidebar_sort_order: 1
---


# Overview

This database is a set of videos of untethered ants grasping objects.
- 100FPS
- 5 Views
- Synchronised
- Calibration intrinsics and extrinsics
- 2D Pose Tracking using SLEAP
- 3D Pose reconstruction using a method published
- Written descriptions of behaviour captured on video
- Labelled according to object interaction category

![Labelled diagram of the camera arrangement used to collect the video data used in this dataset. The ant nests are visible in the bottom left of the image.
In the top right, there is a computer monitor showing some application frames with a live stream video of the five different camera views.]({{ "/assets/img/arena_photo.png" | relative_url }})
*Photo of the recording set-up.*



| ![240905-1616_cam3_strawberry_session29.gif]({{ "assets/img/240905-1616_cam3_strawberry_session29.gif" | relative_url }}) | ![240905-1616_cam4_blueberry_session33.gif]({{ "assets/img/240905-1616_cam4_blueberry_session33.gif" | relative_url }})|






# Download

If you would like to download the full dataset or any part of it, follow the instructions [here]({{ site.baseurl }}{% link dataset_access.md %}).


# Example

We've included an example of how this video dataset is being used [here]({{ site.baseurl }}{% link examples.md %}).


# Output

Aside from the large quantity of synchronised videos and verbal descriptions, there are additional features in this dataset.
![object photos]({{ "assets/img/object_photos.png" | relative_url }})

|                                        *3D Pose*                                         |  *Object Mask*   |
|:----------------------------------------------------------------------------------------:|:----------------:|
| ![Annotated frame in SLEAP]({{ "/assets/img/sleap_label-24-08-09_1326-cam3-session4.png" | relative_url }}) | ![Masked video frame using SAM2]({{ "/assets/img/seed_mask_24-09-05_1616-cam1-session29.png" | relative_url }}) | 

## 3D Pose

We used [sleap.ai](https://sleap.ai/) as the
Manually annotated frames with the following skeleton






## Object Mask
Manually annotated images to segment the seed from the rest of the field of view


![An array of photographs showing the same ant viewed from five different cameras. Each image is annotated with the name of the camera taking the photo, and the object pixel mask is shown in blue.
Next to each photograph, the 3D volume created from the pixel mask is shown from the same perspective as the camera.]({{ "/assets/img/mask_to_volume.png" | relative_url }})

*An array of photographs showing the same ant viewed from five different cameras. Each image is annotated with the name of the camera taking the photo, and the object pixel mask is shown in blue.
Next to each photograph, the 3D volume created from the pixel mask is shown from the same perspective as the camera.*

## Annotations

For each of the [3D Pose](#3d-pose) and [Object Mask](#object-mask), there required manual annotation.

For the object mask, this comes in the form of pixel annotation of object presence in a CSV file.
