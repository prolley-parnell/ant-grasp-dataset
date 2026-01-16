---
layout: page
title: Download
sidebar_link: true
sidebar_sort_order: 2
---
# File Structure

## How to download files

Some of the files are stored in Git LFS (Large File Storage), so the file uploaded in this repo is only a pointer.
To access the real file, follow these instructions:

### 1. Install git-lfs
Follow the instructions on the website: [Installing Git LFS](https://docs.github.com/en/repositories/working-with-files/managing-large-files/installing-git-large-file-storage)

### 2. Clone the repo
```bash
git clone https://github.com/insectrobotics/ant-grasp-dataset.git
```

### 3. Pull files from LFS
This line would pull everything (probably don't do this, it's about 8.8GB in total).
```bash
git lfs pull  
```

This line would only pull files for the given directory (1.07 GB).
```bash
git lfs pull --include "dataset/Video/240905/240905-1616/*"
```

Alternatively, this line would only pull all the analysis input and output data available (1.27 GB).
```bash
git lfs pull --include "dataset/Data/*"
```

