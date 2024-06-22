# VHRTrees

This repository contains weights for YOLOv5, YOLOv7, YOLOv8, and YOLOv9 networks trained with the VHRTrees dataset. YOLOv5 [(link)](https://github.com/ultralytics/yolov5) and YOLOv8 [(link)](https://github.com/ultralytics/ultralytics) were built and trained by our team using Ultralytics library, while YOLOv7 training has been performed using the YOLOv7 repository [(link)](https://github.com/WongKinYiu/yolov7). YOLOv9 training has also been performed using the YOLOv9 repository [(link)](https://github.com/WongKinYiu/yolov9).

*The [dataset](https://github.com/ultralytics/ultralytics), related source code, and [pre-trained models](https://github.com/ultralytics/ultralytics) are available below.

# Dataset Details
The imagery required for the dataset has been obtained from Google Earth. We have downloaded 218 RGB images, each with a resolution of 1920x1080 pixels and a ground sample distance (GSD) of 0.5 km, covering the districts of Karacabey in Bursa, Turkey and Dikili, Aliağa, Seferihisar, and Selçuk in İzmir, Turkey. Subsequently, images unsuitable for the dataset were carefully filtered out. These included images where individual trees were insufficiently visible, could not be annotated, or where cloud cover from the acquisition date obscured the trees. An automatic method was utilized to label trees. Initially, an automatic segmentation process was conducted in [eCognition Developer 64](https://geospatial.trimble.com/en/products/software/trimble-ecognition) to extract the boundaries of individual trees. The segmentation parameters used in this stage were as follows: scale parameter=30, shape=0.98, compactness=0.02. Manual adjustments were made for trees whose boundaries could not be precisely determined. The output was saved in vector (.shp) format. After ensuring that the images and corresponding output vector data were in the same coordinate system (WGS84), vectors were converted into bounding boxes using the Python programming language. A sample image and corresponding minimum boxes for trees can be seen the figure. The dataset has been approximately split as 70% (1023 images), 15% (226 images) and 15% (222 images) for training, validation and testing, respectively.

![sample_2_github1](https://github.com/sulenurtopgul/VHRTrees/assets/109470455/47e94be5-c3af-4770-b5b8-cb09330a6605)

# Models, Metric Results and Weights

Experiments were conducted on Kaggle P100, Colab A100, and NVIDIA Quadro P6000 GPUs. We conducted an initial experiment in which we tested the impact of different network sizes, such as 416x416, 640x640 and 960x960 on the performance of different YOLO models. Additionally, due to the large number of experiments and computational constraints, we fixed the batch size at 16 for the YOLOv5, YOLOv7, and YOLOv8 models, while for YOLOv9, the batch size was set to 8. We have applied various augmentation techniques such as random horizontal flip, rotation, and mosaic, which significantly improved the training results. All experiments were conducted on powerful GPUs and executed concurrently, resulting in similar durations. The evaluation results are given in Table below.

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

# Visual Results

![figure3_visual_results](https://github.com/sulenurtopgul/VHRTrees/assets/109470455/c30a47ae-6d23-488a-8e38-98199cff8862)




