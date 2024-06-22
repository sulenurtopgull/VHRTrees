# VHRTrees

This repository contains weights for YOLOv5, YOLOv7, YOLOv8, and YOLOv9 networks trained with the VHRTrees dataset. YOLOv5 [(link)](https://github.com/ultralytics/yolov5) and YOLOv8 [(link)](https://github.com/ultralytics/ultralytics) were built and trained by our team using Ultralytics library, while YOLOv7 training has been performed using the YOLOv7 repository [(link)](https://github.com/WongKinYiu/yolov7). YOLOv9 training has also been performed using the YOLOv9 repository [(link)](https://github.com/WongKinYiu/yolov9).

The [dataset](https://github.com/ultralytics/ultralytics), related source code, and [pre-trained models](https://github.com/ultralytics/ultralytics) are available below.

# Dataset Details
The imagery required for the dataset has been obtained from Google Earth. We have downloaded 218 RGB images, each with a resolution of 1920x1080 pixels and a ground sample distance (GSD) of 0.5 km, covering the districts of Karacabey in Bursa, Turkey and Dikili, Aliağa, Seferihisar, and Selçuk in İzmir, Turkey. Subsequently, images unsuitable for the dataset were carefully filtered out. These included images where individual trees were insufficiently visible, could not be annotated, or where cloud cover from the acquisition date obscured the trees. An automatic method was utilized to label trees. Initially, an automatic segmentation process was conducted in [eCognition Developer 64](https://geospatial.trimble.com/en/products/software/trimble-ecognition) to extract the boundaries of individual trees. The segmentation parameters used in this stage were as follows: scale parameter=30, shape=0.98, compactness=0.02. Manual adjustments were made for trees whose boundaries could not be precisely determined. The output was saved in vector (.shp) format. After ensuring that the images and corresponding output vector data were in the same coordinate system (WGS84), vectors were converted into bounding boxes using the Python programming language. A sample image and corresponding minimum boxes for trees can be seen the figure. The dataset has been approximately split as 70% (1023 images), 15% (226 images) and 15% (222 images) for training, validation and testing, respectively.

![sample_2_github1](https://github.com/sulenurtopgul/VHRTrees/assets/109470455/47e94be5-c3af-4770-b5b8-cb09330a6605)


No	Model	Optim	Network	Aug	Bs	Epoch	F1	Prec	Recall	mAP
50	mAP
50:95	Time
(hour)	Aug	F1	Prec	Recall	mAP
50	mAP
50:95	Time
(hour)
1	YOLOv5s	SGD	640x640	-	16	50	0.927	0.932	0.923	0.933	0.559	0.293	-	-	-	-	-	-	-
2	YOLOv5m	SGD	640x640	-	16	50	0.927	0.933	0.922	0.931	0.564	0.774	-	-	-	-	-	-	-
3	YOLOv5l	SGD	640x640	-	16	50	0.925	0.928	0.922	0.931	0.565	0.780	-	-	-	-	-	-	-
4	YOLOv5s	Adam	640x640	-	16	50	0.925	0.931	0.920	0.931	0.558	0.2777	-	-	-	-	-	-	-
5	YOLOv5m	Adam	640x640	-	16	50	0.926	0.929	0.924	0.932	0.561	0.495	-	-	-	-	-	-	-
6	YOLOv5l	Adam	640x640	-	16	50	0.927	0.928	0.926	0.932	0.562	0.765	-	-	-	-	-	-	-
7	YOLOv5s	AdamW	640x640	-	16	50	0.927	0.930	0.925	0.933	0.562	0.276	-	-	-	-	-	-	-
8	YOLOv5m	AdamW	640x640	-	16	50	0.927	0.927	0.928	0.933	0.561	0.498	-	-	-	-	-	-	-
9	YOLOv5m	SGD	960x960	-	16	50	0.929	0.932	0.926	0.934	0.569	0.929	+	0.876	0.929	0.829	0.845	0.523	0.430
10	YOLOv5m	AdamW	960x960	-	16	50	0.926	0.927	0.926	0.932	0.564	0.925	+	0.875	0.923	0.831	0.844	0.525	0.431
11	YOLOv5s	SGD	960x960	-	16	50	-	-	-	-	-	-	+	0.931	0.93	0.933	0.933	0.567	0.868
12	YOLOv7	SGD	640x640	-	16	50	0.924	0.926	0.923	0.903	0.526	0.954	+	0.925	0.930	0.920	0.908	0.531	1.105
13	YOLOv7	Adam	640x640	-	16	50		0.915	0.923	0.899	0.514	0.962	+	0.918	0.921	0.916	0.904	0.512	1.100
14	YOLOv7-X	SGD	640x640	-	16	50	0.916	0.23	0.909	0.893	0.50	1.334	-	-	-	-	-	-	-
15	YOLOv7	SGD	960x960	-	16	50	0.929	0.930	0.928	0.908	0.549	11.758	+	0.925	0.926	0.924	0.905	0.536	1.422
16	YOLOv7-X	SGD	960x960	-	16	50	0.930	0.923	0.937	0.912	0.552	13.779	+	0.927	0.935	0.920	0.903	0.535	1.626
17	YOLOv7	Adam	960x960	-	16	50	0.920	0.924	0.916	0.898	0.522	11.697	-	-	-	-	-	-	-
18	YOLOv7-X	Adam	960x960	-	16	50	0.919	0.923	0.916	0.895	0.521	13.772	-	-	-	-	-	-	-
19	YOLOv8s	Auto	640x640	-	16	50	0.896	0.938	0.857	0.894	0.569	0.362	+	0.894	0.933	0.859	0.887	0.564	0.661
20	YOLOv8m	Auto	640x640	-	16	50	0.913	0.928	0.899	0.915	0.582	0.655	+	0.930	0.925	0.936	0.933	0.595	1.226
21	YOLOv8l	Auto	640x640	-	16	50	0.919	0.924	0.914	0.920	0.582	0.958	+	0.907	0.932	0.884	0.903	0.582	1.788
22	YOLOv8s	SGD	640x640	-	16	50	0.911	0.931	0.891	0.915	0.581	0.358	+	0.890	0.941	0.844	0.883	0.567	0.651
23	YOLOv8m	SGD	640x640	-	16	50	0.916	0.932	0.901	0.923	0.590	0.654	+	0.919	0.936	0.902	0.918	0.597	1.218
24	YOLOv8l	SGD	640x640	-	16	50	0.883	0.932	0.838	0.877	0.562	0.945	+	0.860	0.943	0.790	0.845	0.565	1.780
25	YOLOv8s	Adam	640x640	-	16	50	0.924	0.925	0.923	0.934	0.580	0.362	+	0.897	0.942	0.856	0.896	0.570	0.666
26	YOLOv8m	Adam	640x640	-	16	50	0.916	0.926	0.907	0.922	0.574	0.658	+	0.866	0.935	0.806	0.854	0.544	1.222
27	YOLOv8l	Adam	640x640	-	16	50	0.917	0.926	0.908	0.925	0.579	0.962	+	0.848	0.936	0.775	0.822	0.526	1.790
28	YOLOv8s	Auto	960x960	-	16	50	0.893	0.941	0.850	0.889	0.566	0.657	+	0.30	0.928	0.932	0.934	0.604	1.459
29	YOLOv8m	Auto	960x960	-	16	50	0.926	0.929	0.924	0.934	0.593	1.470	+	0.932	0.932	0.932	0.934	0.608	2.668
30	YOLOv8s	SGD	960x960	-	16	50	0.925	0.926	0.925	0.938	0.590	0.648	+	0.930	0.929	0.932	0.935	0.606	0.36
31	YOLOv8m	SGD	960x960	-	16	50	0.928	0.929	0.928	0.932	0.600	1.422	+	0.915	0.942	0.890	0.916	0.608	0.514
32	YOLOv8s	Adam	960x960	-	16	50	0.921	0.925	0.918	0.932	0.581	0.654	-	-	-	-	-	-	-
33	YOLOv8m	Adam	960x960	-	16	50	0.923	0.920	0.927	0.934	0.585	1.427	-	-	-	-	-	-	-
34	YOLOv8m	AdamW	960x960	-	16	50	-	-	-	-	-	-	+	0.925	0.928	0.923	0.936	0.595	2.781
35	YOLOv9-gelan	SGD	640x640	-	8	45	0.924	0.926	0.922	0.931	0.570	0.308	+	0.889	0.935	0.848	0.887	0.549	1.912
36	YOLOv9-gelan	Adam	640x640	-	8	45	0.897	0.924	0.871	0.895	0.551	1.022	+	0.912	0.924	0.901	0.917	0.565	1.927
37	YOLOv9-gelan	AdamW	640x640	-	8	45	0.877	0.936	0.825	0.871	0.542	1.027	+	0.910	0.921	0.899	0.913	0.558	1.926
38	YOLOv9-gelan-c	SGD	640x640	-	8	45	0.924	0.930	0.918	0.934	0.573	0.533	+	0.928	0.924	0.932	0.936	0.594	1.881
39	YOLOv9-gelan-c	Adam	640x640	-	8	45	0.890	0.936	0.848	0.893	0.553	0.992	+	0.878	0.927	0.834	0.865	0.538	1.875
40	YOLOv9-gelan-c	AdamW	640x640	-	8	45	0.898	0.925	0.873	0.897	0.553	0.998	-	-	-	-	-	-	-
41	YOLOv9-gelan	SGD	960x960	-	8	45	0.923	0.926	0.921	0.932	0.571	0.44	+	0.924	0.926	0.922	0.933	0.58	0.79
42	YOLOv9-gelan-c	SGD	960x960	-	8	45	-	-	-	-	-	-	+	0.924	0.922	0.927	0.534	0.584	0.846
