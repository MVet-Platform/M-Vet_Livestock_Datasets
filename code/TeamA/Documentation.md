

Begin by installing ultralytics library using the command
- pip install ultralytics
```
.
├── 0001
├── 0002
├── 0003
├── 0004
├── 0005
├── 0006
├── 0007
├── datasets
│   ├── runs
│   │   └── detect
│   │       ├── train
│   │       │   └── weights
│   │       ├── train2
│   │           └── weights
│   │       
│   ├── test
│   │   └── images
│   ├── train
│   │   ├── images
│   │   └── labels
│   ├── valid
│   │   ├── images
│   │   └── labels
|
├── inference.ipynb
├── label_train.csv
├── metric.ipynb
├── prepare_files.ipynb
```
The above tree shows the project directory structure. Folders 0001 - 0007 contain the images. 

prepare_files.ipynb is run to organise these images into train, valid and test.

Training the model (yolov10m) is done in two phases all run in the linux terminal.

- Phase 1 training \
yolo train model=yolov10m.pt data=data.yaml epochs=200 imgsz=640 batch=16


- Phase 2 training (reduce the learning rate)\
yolo train model=runs/detect/train2/weights/last.pt data=data.yaml epochs=400 imgsz=640 batch=16 lr0=0.0001


Testing the model is done by running the cells in inference.ipynb file.

