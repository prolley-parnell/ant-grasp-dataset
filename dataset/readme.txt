===============
Video Contents
===============

There are 167 experiments varying from 20 seconds to 5 minutes long.
Each experiment has been recorded using 5 cameras, labelled "camera_0" to "camera_4", and each video file is an MP4.


DISCLAIMERS
1. Most videos have a black first frame. This is normal and part of the software.
2. The verbal descriptions of each video do not have the total number of ants in any video,
but the number of ants involved in an interaction with the sensed object are described.


=================
Folder Structure
=================

The structure of the full dataset is shown in a text-tree format below.
A comprehensive list of all available videos can be found in description.csv.

*For brevity, not all files are shown in this file tree.*

=================

dataset
├── Annotation
│   ├── object_mask
│   │   └── input
│   │       ├── 240809-1240_cam0_avocado_session13
│   │       ├── ...
│   │       └── 240905-1616_cam4_blueberry_session56
│   └── sleap
│       ├── sleap_trained_model
│       ├── ant_skeleton.json
│       └── labels.v005.slp
├── Calibration
│   ├── 240725
│   ├── 240809
│   │   ├── 240809-1240
│   │   ├── 240809-1326
│   │   ├── 240809-1347
│   │   ├── 240809-1402
│   │   └── 240809-1436
│   └── 240905
│       ├── 240905-1616
│       │   ├── calibration
│       │   ├── 240905-1616_cam0_avocado_session0.mp4
│       │   ├── 240905-1616_cam1_coconut_session0.mp4
│       │   ├── 240905-1616_cam2_banana_session0.mp4
│       │   ├── 240905-1616_cam3_strawberry_session0.mp4
│       │   ├── 240905-1616_cam4_blueberry_session0.mp4
│       │   ├── parameters.toml
│       │   ├── points2d_stacked.npz
│       │   ├── visibility_masks_stacked.npz
│       │   └── volume.toml
│       └── 240925
│           ├── 240925-1557
│           └── 240925-1616
├── Data
│   ├── 240809-1240
│   │   ├── calibration
│   │   └── inputs
│   │       ├── segmentation
│   │       └── tracking
│   └── 240905-1616
│       ├── calibration
│       ├── inputs
│       │   ├── segmentation
│       │   │   ├── 240905-1616_cam0_avocado_session6.rle
│       │   │   ├── ...
│       │   │   ├── 240905-1616_cam0_avocado_session30.rle
│       │   │   ├── 240905-1616_cam1_coconut_session6.rle
│       │   │   ├── ...
│       │   │   ├── 240905-1616_cam1_coconut_session30.rle
│       │   │   ├── 240905-1616_cam2_banana_session6.rle
│       │   │   ├── ...
│       │   │   ├── 240905-1616_cam2_banana_session30.rle
│       │   │   ├── 240905-1616_cam3_strawberry_session6.rle
│       │   │   ├── ...
│       │   │   ├── 240905-1616_cam3_strawberry_session30.rle
│       │   │   ├── 240905-1616_cam4_blueberry_session6.rle
│       │   │   ├── ...
│       │   │   └── 240905-1616_cam4_blueberry_session30.rle
│       │   ├── tracking
│       │   │   ├── 240905-1616_cam0_avocado_session6.predictions.slp
│       │   │   ├── ...
│       │   │   ├── 240905-1616_cam0_avocado_session30.predictions.slp
│       │   │   ├── 240905-1616_cam1_coconut_session6.predictions.slp
│       │   │   ├── ...
│       │   │   ├── 240905-1616_cam1_coconut_session30.predictions.slp
│       │   │   ├── 240905-1616_cam2_banana_session6.predictions.slp
│       │   │   ├── ...
│       │   │   ├── 240905-1616_cam2_banana_session30.predictions.slp
│       │   │   ├── ...
│       │   │   ├── 240905-1616_cam3_strawberry_session30.predictions.slp
│       │   │   ├── 240905-1616_cam4_blueberry_session6.predictions.slp
│       │   │   ├── ...
│       │   │   ├── 240905-1616_cam4_blueberry_session30.predictions.slp
│       │   │   ├── session6_tracking.parquet
│       │   │   ├── ...
│       │   │   └── session30_tracking.parquet
│       │   ├── tracking_new_model_csv
│       │   │   ├── predictions.240905-1616_cam0_avocado_session6.csv
│       │   │   ├── ...
│       │   │   ├── predictions.240905-1616_cam0_avocado_session30.csv
│       │   │   ├── predictions.240905-1616_cam1_coconut_session6.csv
│       │   │   ├── ...
│       │   │   ├── predictions.240905-1616_cam1_coconut_session30.csv
│       │   │   ├── predictions.240905-1616_cam2_banana_session6.csv
│       │   │   ├── ...
│       │   │   ├── predictions.240905-1616_cam2_banana_session30.csv
│       │   │   ├── predictions.240905-1616_cam3_strawberry_session6.csv
│       │   │   ├── ...
│       │   │   ├── predictions.240905-1616_cam3_strawberry_session30.csv
│       │   │   ├── predictions.240905-1616_cam4_blueberry_session6.csv
│       │   │   ├── ...
│       │   │   └── predictions.240905-1616_cam4_blueberry_session30.csv
│       │   ├── tracking_old_model
│       │   ├── clear_seed.toml
│       │   └── ground_truth_ant_contact.toml
│       └── outputs
│           ├── segmentation
│           │   ├── 240905-1616_seed_session6.toml
│           │   ├── 240905-1616_seed_session6_frame500.dae
│           │   ├── 240905-1616_seed_session10.toml
│           │   ├── 240905-1616_seed_session10_frame180.dae
│           │   ├── 240905-1616_seed_session11.toml
│           │   ├── 240905-1616_seed_session11_batch.toml
│           │   ├── 240905-1616_seed_session11_frame380.dae
│           │   ├── 240905-1616_seed_session13.toml
│           │   ├── 240905-1616_seed_session13_frame849.dae
│           │   ├── 240905-1616_seed_session17.toml
│           │   ├── 240905-1616_seed_session17_frame459.dae
│           │   ├── 240905-1616_seed_session19.toml
│           │   ├── 240905-1616_seed_session19_frame59.dae
│           │   ├── 240905-1616_seed_session20.toml
│           │   ├── 240905-1616_seed_session20_frame842.dae
│           │   ├── 240905-1616_seed_session21.toml
│           │   ├── 240905-1616_seed_session21_frame24.dae
│           │   ├── 240905-1616_seed_session22.toml
│           │   ├── 240905-1616_seed_session22_frame93.dae
│           │   ├── 240905-1616_seed_session23.toml
│           │   ├── 240905-1616_seed_session23_frame8.dae
│           │   ├── 240905-1616_seed_session23_frame176.dae
│           │   ├── 240905-1616_seed_session26.toml
│           │   ├── 240905-1616_seed_session26_frame1921.dae
│           │   ├── 240905-1616_seed_session28.toml
│           │   ├── 240905-1616_seed_session28_frame2599.dae
│           │   ├── 240905-1616_seed_session28_frame2626.dae
│           │   ├── 240905-1616_seed_session29.toml
│           │   ├── 240905-1616_seed_session29_frame320.dae
│           │   ├── 240905-1616_seed_session29_frame595.dae
│           │   ├── 240905-1616_seed_session30.toml
│           │   └── 240905-1616_seed_session30_frame241.dae
│           └── tracking
│               ├── bone_stats_session6.json
│               ├── ...
│               ├── bone_stats_session30.json
│               ├── linked_tracks_session6.pkl
│               ├── ...
│               ├── linked_tracks_session30.pkl
│               ├── points_soup_session6.pkl
│               ├── ...
│               ├── points_soup_session30.pkl
│               ├── tracklets_session6.pkl
│               ├── ...
│               └── tracklets_session30.pkl
├── Metadata
│   ├── 240725-1509_metadata.json
│   └── 240925-1616_metadata.json
├── Video
├── dataset_description.csv
└── readme.txt
docs

=============

All videos have a unique identification of the following structure:
{YYMMDD-HHMM}_cam{CAMERA_ID}_{CAMERA_NAME}_session{ACQUISITION_ID}.mp4

CAMERA_ID: Number 0 to 4 corresponding with the assigned index of each camera.
This does not change throughout the database, and the position of each camera remains
approximately the same.

In the Calibration folder, there are all recorded calibration videos, and the estimated calibration intrinsics and extrinsics.
Some of these calibration parameters are duplicated in the Data folder. The parameters available in the Data folder are more reliable and the quality of 3D reconstruction was good.
If there are videos of interest that are not given in the Data folder, consider re-estimating the camera parameters where possible.

=============
metadata.json
=============

{
    "sessions": [
        {
            "start": 1725549940.254741,
            "end": 1725550044.313758,
            "duration": 104.0590169429779,
            "hardware_triggered": true,
            "cameras": [
                {
                    "idx": 0,
                    "name": "avocado",
                    "width": 1440,
                    "height": 1080,
                    "exposure": 4800,
                    "gain": 0.0,
                    "gamma": 1.0,
                    "black_level": 1.0,
                    "frames": 10407,
                    "framerate_theoretical": 100,
                    "framerate_actual": 100.01055464230275
                },

Session indices increase with the start and stop of camera acquisition at the time of gathering experiment data.
** Session indices are not all sequential integers, some unremarkable sessions were removed. **
See the descriptions.csv for a comprehensive list of the Session indices for each Experiment.

===========
Calibration
===========

All video experiments {YYMMDD-HHMM} have a calibration folder
but the camera extrinsics and intrinsics are only provided for
240905-1616 in the file parameters.toml

For all videos, the position of the camera is approximately the same, with some
experiments changing the camera position up to 10cm, and the lens-sensor distance modified
to change focal point. A calibration video is recorded after before each experiment and
the unprocessed, synchronised video is provided and the calibration parameters where they
have been calculated.

The calibration square is a ChAruCo marker that is 9mm X 7.5mm. Each square is 1.5mm and the grid is 6 X 5.

=======================
dataset_description.csv
=======================

| Calibration Parameters |
| ---------------------- |
Are there accurate calibration parameters available for this session?

| Grasped? |
| -------- |
Tag describing the extent of interaction; Did the ant grasp the object?

| Hardware Synchronised? |
| ---------------------- |
Was this session hardware or software synchronised? If the session was software synchronised, the frames may be misaligned by one or two frames (0.01 to 0.02 seconds).

| Notes |
| ----- |
This is a verbal description of what interactions occur in the length of the video. It is to supplement the tag system in "Grasped?".

| Object |
| ------ |
What object does the ant grasp?

| Reviewed for Upload |
| ------------------- |
Has this description and "Grasped?" tag been reviewed since June 2025?

| Session Number |
| -------------- |
For this experiment, which session is this description for?

| Video Date |
| ---------- |
What date and time did the set of Sessions (Experiment) start? This time stamp is used to differentiate experiments.