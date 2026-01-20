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
- Synchronised acquisition
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
## Objects
![A series of images containing the different objects used in the experiment sessions. 
In the centre of the frame is an image of a ChAruCo marker that was used in the calibration videos. All images are taken from the same camera so the ChAruCo board can be used for scale.]({{ "assets/img/object_photos.png" | relative_url }})

_A series of images containing the different objects used in the experiment sessions._

In the centre of the frame is an image of a ChAruCo marker that was used in the calibration videos. All images are taken from the same camera so the ChAruCo board can be used for scale.

# Download

| ![240905-1616_cam3_strawberry_session29.gif]({{ "assets/img/240905-1616_cam3_strawberry_session29.gif" | relative_url }}) | ![240905-1616_cam4_blueberry_session33.gif]({{ "assets/img/240905-1616_cam4_blueberry_session33.gif" | relative_url }})|

If you would like to download the full dataset or any part of it, follow the instructions [here]({{ site.baseurl }}{% link dataset_access.md %}) or [here]({{site.github.repository_url}}/blob/main/readme.md).


# Example
We've included an [Example]({{ site.baseurl }}{% link examples.md %}) of how this video dataset is being used with the [catar](https://github.com/annahadji/catar) repo for 3D pose extraction.

# Dataset

Aside from the large quantity of synchronised videos and verbal descriptions, there are additional features in this dataset.
The dataset [readme.txt]({{site.github.repository_url}}/blob/main/dataset/readme.txt) contains some additional information on the file structure.

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

One of the categories in the [dataset_description.csv]({{site.github.repository_url}}/blob/main/dataset/dataset_description.csv) is "Reviewed for Upload?".
In experiments where this says "Yes", the description and tag have been reviewed since July 2025, the others were last reviewed around December 2024.
This time gap allowed for more deliberation on which videos fit in which categories and the specific interesting behaviours to be described.
Therefore, experiments that have not been reviewed for upload may have less specific descriptions and incorrect behaviour tags.


|                                        *2D Pose*                                         |  *Object Mask*   |
|:----------------------------------------------------------------------------------------:|:----------------:|
| ![Annotated frame in SLEAP]({{ "/assets/img/sleap_label-24-08-09_1326-cam3-session4.png" | relative_url }}) | ![Masked video frame using SAM2]({{ "/assets/img/seed_mask_24-09-05_1616-cam1-session29.png" | relative_url }}) | 

### 2D Animal Pose
#### Skeleton Keypoints
![Two illustrated ants with some joint annotations for the name scheme used with SLEAP]({{ "assets/img/sleap_kp_map.png" | relative_url }})

Using [sleap.ai](https://sleap.ai/), around 500 frames of video were manually annotated for the keypoints shown in the [skeleton keypoints](#skeleton-keypoints).
The annotations are provided in the [Annotations/sleap]({{site.github.repository_url}}/blob/main/dataset/Annotation/sleap) directory, in the form of an ```.slp``` project file.
This folder also contains a trained model using a top-down approach.



### Object Mask

To extract a pixel occupancy mask, the process was accelerated by using [facebookresearch/sam2](https://github.com/facebookresearch/sam2) to segment the objects.
The pixel annotations used to train the SAM2 model are available in the [Annotations/object_mask/input]({{site.github.repository_url}}/blob/main/dataset/Annotation/object_mask/input) directory as ```.csv```.

The code used to train the model on University of Edinburgh cluster computing is also available at [prolley-parnell/SAM2_cluster](https://github.com/prolley-parnell/SAM2_cluster).

## 3D Animal Pose

Using the [mokap](https://github.com/FlorentLM/mokap) repository, the 2D keypoints can be combined into 3D keypoint poses for the frames in the videos where calibration parameters are good.
The output of this process can be found in [Data/240905-1616/outputs/tracking]({{site.github.repository_url}}/blob/main/dataset/Data/240905-1616/outputs/tracking) directory as ```tracklets_*.pkl``` files.

To read these files, use the repo [prolley-parnell/3d_ant_analysis](https://github.com/prolley-parnell/3d_ant_analysis).

Some further research has been carried out on how to extract a reliable 3D pose from multiple viewpoints in [Example]({{ site.baseurl }}{% link examples.md %}). 


## Object Pose

To generate the 3D object pose, the 2D pixel occupancy masks were combined using the camera parameters and voxel carving then using Iterative Closest Pairs (ICP) to match between the poses of sequential meshes.
The code to achieve this is also in [mokap](https://github.com/FlorentLM/mokap).

The output of this pose tracking is [Data/240905-1616/outputs/segmentation]({{site.github.repository_url}}/blob/main/dataset/Data/240905-1616/outputs/segmentation).
This folder contains both the ```.toml``` file with pose transforms from the reference frame, as well as the ```.dae``` of the reference frame.

Due to the object being tracked having rotational symmetry and being partially occluded by ants, the pose tracking is unreliable in places.

![An array of photographs showing the same ant viewed from five different cameras. Each image is annotated with the name of the camera taking the photo, and the object pixel mask is shown in blue.
Next to each photograph, the 3D volume created from the pixel mask is shown from the same perspective as the camera.]({{ "/assets/img/mask_to_volume.png" | relative_url }})

*An array of photographs showing the same ant viewed from five different cameras. Each image is annotated with the name of the camera taking the photo, and the object pixel mask is shown in blue.
Next to each photograph, the 3D volume created from the pixel mask is shown from the same perspective as the camera.*


