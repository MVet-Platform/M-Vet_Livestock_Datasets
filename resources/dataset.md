# Competition Datasets

There are 2 main datasets for this competion:

## Well Identification and Measurement Dataset

1. This dataset has 81 classes:
   a1, a10, a11, a12, a2, a3, a4, a5, a6, a7, a8, a9, b1, b10, b11, b12, b2, b5, b6, b7, b8, b9, c1, c10, c11, c12, c4, c5, c6, c7, c8, c9, d1, d10, d11, d12, d2, d5, d6, d7, d8, d9, e1, e10, e11, e12, e2, e5, e6, e7, e8, f1, f10, f11, f12, f3, f4, f6, f7, f8, f9, g1, g10, g11, g12, g3, g4, g5, g7, g8, g9, h1, h10, h11, h12, h3, h4, h5, h6, h8 and h9

2. The dataset is split as follows

   - Train with **63** images.
   - Validation with **6** images.
   - Test with **3** images.

3. Sample images from the dataset

<p align="center">
  <img src="https://github.com/MVet-Platform/M-Vet_Hackathon24/blob/main/sample_images/IMG_5750_JPG.rf.789dfecb1651011f75d36c7907c77683.jpg" alt="Image 1" width="45%" />
  <img src="https://github.com/MVet-Platform/M-Vet_Hackathon24/blob/main/sample_images/IMG_5760_JPG.rf.43199e715998f4adf77924e114b1d717.jpg" alt="Image 2" width="45%" />
</p>

4. The Dataset can be obtained using the following python code:

   ```python
   HOME=os.getcwd()
   !mkdir {HOME}/datasets
   %cd {HOME}/datasets
   DATASET_LOCATION=f"{HOME}/datasets/Well Identification and Measurement"

   data = {"username":"labanochwo","key":"cb6bdd8fa399054395055df848c757b8"}
   with open(f'{HOME}/kaggle.json', 'w') as file:
       json.dump(data, file, indent=4)

   !mkdir -p ~/.kaggle
   !mv '{HOME}/kaggle.json' ~/.kaggle/
   !chmod 600 ~/.kaggle/kaggle.json
   !kaggle datasets download -d labanochwo/well-identification-and-measurement
   !unzip -q well-identification-and-measurement.zip -d '{HOME}/datasets/Well Identification and Measurement'
   !rm -rf well-identification-and-measurement.zip
   ```

**NOTE**
You can use your own configuration with the train and validation sets during the model training.

## [Cocoa Detection Dataset](https://storage.googleapis.com/air-lab-hackathon/Cocoa/cocoa_new.zip)

1. The dataset contains objects in cocoa trees under 4 classes Spoilt, Immature, Mature_Unripe and Ripped. It has been split into 3 subsets.

   - Train with **4550** images.
   - Validation with **1262** images.
   - Test with **318** images.

2. The dataset can be downloaded as a single zip file of ~370MB from [here](https://storage.googleapis.com/air-lab-hackathon/Cocoa/cocoa_new.zip).

   <img src="https://github.com/AI-Lab-Makerere/CV4Agriculture_Hackathon24/blob/main/resources/images/cocoa_annotated.png" />

3. The dataset has 2 types of labels.
   The first type is PASCAL VOC XML files for every image with the label information (see picture below) and these are found in the respective train and validation folders alongside the images.
   The second type of label is a CSV file named `labelmap.csv` that is found in the train and validation folders. A row in the CSV represents an object in the image and has 10 columns;

   - **Image id** - The filename of the image in the respective folder. Note that this is repeated for images with multiple objetcs
   - **Actual Label** - The class label of the objects of interest in the image.
   - **xmin, ymin, xmax, ymax** - The bounding box cordinates of the objects in the image.
   - **xmin_norm, ymin_norm, xmax_norm, ymax_norm** - The normalized bounding box coordinates of the objects in the image.

  <p style="text-align: center;">Image shows a sample PASCAL VOC annoation in XML format</p>  
  <img height="400" src="https://github.com/AI-Lab-Makerere/CV4Agriculture_Hackathon24/blob/main/resources/images/cocoa_xml_label.png"/>

  <p style="text-align: center;">Image shows a sample of the labels in a CSV file for Cocoa</p>  
  <img height="400" src="https://github.com/AI-Lab-Makerere/CV4Agriculture_Hackathon24/blob/main/resources/images/cocoa_csv_label.png"/>

**NOTE**
You can use your own configuration with the train and validation sets during the model training.
