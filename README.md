# VHRTrees

This repository contains weights for YOLOv5, YOLOv7, YOLOv8, and YOLOv9 networks trained with the VHRTrees dataset. YOLOv5 [(link)](https://github.com/ultralytics/yolov5) and YOLOv8 [(link)](https://github.com/ultralytics/ultralytics) were built and trained by our team using Ultralytics library, while YOLOv7 training has been performed using the YOLOv7 repository [(link)](https://github.com/WongKinYiu/yolov7). YOLOv9 training has also been performed using the YOLOv9 repository [(link)](https://github.com/WongKinYiu/yolov9).

The [dataset](https://github.com/ultralytics/ultralytics), related source code, and [pre-trained models](https://github.com/ultralytics/ultralytics) are available below.

# Dataset Details
The imagery required for the dataset has been obtained from Google Earth. We have downloaded 218 RGB images, each with a resolution of 1920x1080 pixels and a ground sample distance (GSD) of 0.5 km, covering the districts of Karacabey in Bursa, Turkey and Dikili, Aliağa, Seferihisar, and Selçuk in İzmir, Turkey. Subsequently, images unsuitable for the dataset were carefully filtered out. These included images where individual trees were insufficiently visible, could not be annotated, or where cloud cover from the acquisition date obscured the trees. An automatic method was utilized to label trees. Initially, an automatic segmentation process was conducted in [eCognition Developer 64](https://geospatial.trimble.com/en/products/software/trimble-ecognition) to extract the boundaries of individual trees. The segmentation parameters used in this stage were as follows: scale parameter=30, shape=0.98, compactness=0.02. Manual adjustments were made for trees whose boundaries could not be precisely determined. The output was saved in vector (.shp) format. After ensuring that the images and corresponding output vector data were in the same coordinate system (WGS84), vectors were converted into bounding boxes using the Python programming language. A sample image and corresponding minimum boxes for trees can be seen the figure. The dataset has been approximately split as 70% (1023 images), 15% (226 images) and 15% (222 images) for training, validation and testing, respectively.

![sample_2_github1](https://github.com/sulenurtopgul/VHRTrees/assets/109470455/47e94be5-c3af-4770-b5b8-cb09330a6605)

## Models, Metric Results and Weights

| Model No | Network | Optimizer | Model | Batch Size | Epoch | F-1 Score | Precision | Recall | mAP50 | mAP50-95 |
|:--------:|:-------:|:---------:|:-----:|:----------:|:-----:|:---------:|:---------:|:------:|:-----:|:--------:|
| Model 1  |         |           |       |            |       |           |           |        |       |          |
| Model 2  |         |           |       |            |       |           |           |        |       |          |
| Model 3  |         |           |       |            |       |           |           |        |       |          |
| Model 4  |         |           |       |            |       |           |           |        |       |          |
| Model 5  |         |           |       |            |       |           |           |        |       |          |
| Model 6  |         |           |       |            |       |           |           |        |       |          |
| Model 7  |         |           |       |            |       |           |           |        |       |          |
| Model 8  |         |           |       |            |       |           |           |        |       |          |
| Model 9  |         |           |       |            |       |           |           |        |       |          |
| Model 10 |         |           |       |            |       |           |           |        |       |          |

***The pre-trained models and weights can be found [here](https://github.com/sulenurtopgul/VHRTrees/assets/109470455/47e94be5-c3af-4770-b5b8-cb09330a6605).*** 


