---
layout: index
title: About
name: Home
sidebar_link: true
sidebar_sort_order: 1
---


# Overview

This dataset is a set of 164 recordings of untethered ants grasping objects.
Each recording is:
- 100FPS
- Covered by 5 camera views - See [Setup](#setup)
- Synchronised
- Accompanied by written descriptions of behaviour captured on video
- Tagged according to object interaction category

The dataset was developed for use with 3D tracking of animal and object pose throughout the interaction and therefore a subset of the dataset is paired with:
- Calibration videos with provided camera intrinsics and extrinsics
- 2D Ant pose tracking using SLEAP -> [Pose Tracking](#2d-animal-pose)
- 3D Pose reconstruction using [mokap](https://github.com/FlorentLM/mokap) -> [3D Pose](#3d-animal-pose)
- 2D Object pixel occupancy mask -> [Object Mask](#object-mask)
- 3D Object pose estimation (WIP) -> [Object Pose](#object-pose)

## Setup
![Labelled diagram of the camera arrangement used to collect the video data used in this dataset. The ant nests are visible in the bottom left of the image.
In the top right, there is a computer monitor showing some application frames with a live stream video of the five different camera views.]({{ "/assets/img/arena_photo.png" | relative_url }})
_Labelled diagram of the camera arrangement used to collect the video data used in this dataset._


---

![A series of images containing the different objects used in the experiment sessions. 
In the centre of the frame is an image of a ChAruCo marker that was used in the calibration videos. All images are taken from the same camera so the ChAruCo board can be used for scale.]({{ "assets/img/object_photos.png" | relative_url }})

_A series of images containing the different objects used in the experiment sessions._

In the centre of the frame is an image of a ChAruCo marker that was used in the calibration videos. All images are taken from the same camera so the ChAruCo board can be used for scale.

# Download

| ![240905-1616_cam3_strawberry_session29.gif]({{ "assets/img/240905-1616_cam3_strawberry_session29.gif" | relative_url }}) | ![240905-1616_cam4_blueberry_session33.gif]({{ "assets/img/240905-1616_cam4_blueberry_session33.gif" | relative_url }})|

If you would like to download the full dataset or any part of it, follow the instructions [here]({{ site.baseurl }}{% link dataset_access.md %}) or [here]({{site.github.repository_url}}/blob/main/readme.md).


# Example
We've included an example of how this video dataset is being used [here]({{ site.baseurl }}{% link examples.md %}) with the [catar](https://github.com/annahadji/catar) repo for 3D pose extraction.

# Dataset

Aside from the large quantity of synchronised videos and verbal descriptions, there are additional features in this dataset.
The dataset README and some additional information on the file structure is available here: [readme.txt]({{site.github.repository_url}}/blob/main/dataset/readme.txt).

## Annotations

For the [3D Pose](#3d-animal-pose) and [Object Mask](#object-mask), the videos were manually annotated.
In addition to this, there are verbal descriptions and action tags for each experiment session.



### Descriptive

The videos are separated into 4 categories based on the observed behaviour of interest. In the context 
of recording, we were most interested in how the ants approached and sensed an object before grasping it and the influence 
of the sensing behaviour on the likelihood of grasp success. Therefore, we organised the videos into the following categories:

- ✅✅ Grasped and carried away
- ✅ Grasped and dropped
- ☑️ Manipulated or pinched but not grasped
- ❌ Sensed but not manipulated


### Object Mask

For the object mask, this comes in the form of pixel annotation of object presence in a CSV file.

[Object Mask Annotations]({{site.github.repository_url}}/blob/main/dataset/Annotation/object_mask/input)

[facebookresearch/sam2](https://github.com/facebookresearch/sam2)

[prolley-parnell/SAM2_cluster](https://github.com/prolley-parnell/SAM2_cluster)

### 2D Animal Pose

We used [sleap.ai](https://sleap.ai/) as the
Manually annotated frames with the following skeleton

Model is [Trained Sleap Model]({{site.github.repository_url}}/blob/main/dataset/Annotation/sleap)

![Two illustrated ants with some joint annotations for the name scheme used with SLEAP]({{ "assets/img/sleap_kp_map.png" | relative_url }})

[prolley-parnell/SLEAP_train](https://github.com/prolley-parnell/SLEAP_train)




|                                        *2D Pose*                                         |  *Object Mask*   |
|:----------------------------------------------------------------------------------------:|:----------------:|
| ![Annotated frame in SLEAP]({{ "/assets/img/sleap_label-24-08-09_1326-cam3-session4.png" | relative_url }}) | ![Masked video frame using SAM2]({{ "/assets/img/seed_mask_24-09-05_1616-cam1-session29.png" | relative_url }}) | 

## 3D Animal Pose








## Object Pose
Manually annotated images to segment the seed from the rest of the field of view


![An array of photographs showing the same ant viewed from five different cameras. Each image is annotated with the name of the camera taking the photo, and the object pixel mask is shown in blue.
Next to each photograph, the 3D volume created from the pixel mask is shown from the same perspective as the camera.]({{ "/assets/img/mask_to_volume.png" | relative_url }})

*An array of photographs showing the same ant viewed from five different cameras. Each image is annotated with the name of the camera taking the photo, and the object pixel mask is shown in blue.
Next to each photograph, the 3D volume created from the pixel mask is shown from the same perspective as the camera.*


