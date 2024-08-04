This repository contains all the necessary files for participating in the Animal Type detection challenge.

## Dataset Overview

The dataset includes the following components:

1. **Images**: The images are divided into seven batches, named `0001` to `0007`.
2. **Sample Submission File**: A file named `sample_submission.csv` which contains headers: **filename**, **class**, **xmin**, **ymin**, **xmax**, **ymax** with filename being file names for the test set. This file indicates the expected format of the submission file.
3. **Training Ground Truth**: A file named `label_train.csv` provides image filenames and their associated labels and bounding box cordinates and it should be used for training and validation purposes.
4. **Tutorial**: The file `animal-type-detection-tutorial.ipynb` contains demo code for the challege.
