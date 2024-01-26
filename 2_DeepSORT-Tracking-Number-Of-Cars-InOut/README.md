# YOLOv8-with-DeepSORT-Tracking-Number-Of-Cars-InOut

## Features

- **YOLOv8 Object Detection with DeepSORT Tracking (ID + Trails):** Utilises the latest advancements in object detection and tracking to ensure accurate and efficient performance.

## Dataset Used

- **Dataset Information:**
Focuses on image processing techniques and doesn't explicitly use a large dataset for training or a pre-trained model for prediction.

## Model Details

- **Model Used:** YOLO-V8
We have used "YOLOv8" for our project which was officially released on 10th January, 2023 and offers higer accuracy and faster speed compared to the older versions. For instance, the YOLOv8(medium) has a 50.2 mAP score at 1.83 milliseconds on the COCO dataset and A100 TensorRT. YOLO v8 also features a Python package and CLI-based implementation, making it easy to use and develop. 
YOLOv8 comes in five variants based on the number of parameters – nano(n), small(s), medium(m), large(l), and extra large(x). We can use all the variants for classification, object detection, and segmentation.  

## Problem Statement

- **Purpose and Impact:**
  - The model is designed to detect the number of cars going in and out from a particular point effectively, addressing a crucial road safety issue.
  - Its application extends to improving road conditions, thereby benefiting public safety and vehicle maintenance.

## Model Pros

- **Advantages of Selected Model:**

Improved accuracy: YOLOv8 delivers state-of-the-art results on a range of object identification benchmarks. It outperforms prior versions of YOLO, particularly for tiny and difficult-to-detect objects.

Quicker speed: YOLOv8 is quicker than earlier versions of YOLO while remaining more accurate. This is the result of several optimisations, including a new backbone network based on EfficientNet.

Improved developer experience: YOLOv8 has several improvements that make it easier to use and customise than prior versions of YOLO. For example, it has a new API that simplifies model training and deployment.


## Steps to run Code

-   Clone the repository

```
git clone https://github.com/annimukherjee/Road-Safety-ModelZoo/tree/main
```

-   Goto cloned folder

```
cd 2_DeepSORT-Tracking-Number-Of-Cars-InOut
```

-   Install the ultralytics package

```
pip install ultralytics==8.0.0
```

-   Setting the Directory.

```
cd yolo/v8/detect
```

-   Do Tracking

```
# video file
python tracking_vehicle_counting.py model=yolov8l.pt source="test.mp4" show=True
```

## Results



<br>



## ⁠Results

**Video Demo**

https://github.com/annimukherjee/Road-Safety-ModelZoo/assets/85307430/f7ba3b0f-39b6-4ced-9300-8c975b02643a

<p align="center">
  <img src="results-screenshots/results-01.png" alt="Alt text" width="75%"/>
</p>
<p align="center">
  <img src="results-screenshots/results-02.png" alt="Alt text" width="75%"/>
</p>
<p align="center">
  <img src="results-screenshots/results-03.png" alt="Alt text" width="75%"/>
</p>
<p align="center">
  <img src="results-screenshots/results-04.png" alt="Alt text" width="75%"/>
</p>


