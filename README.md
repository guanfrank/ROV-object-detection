#  ROV object detection

### 1. Introduction

This is an implementation of [YOLOv3]in TensorFlow.

- Efficient tf.data pipeline
- Weights converter (converting pretrained darknet weights on COCO dataset to TensorFlow checkpoint.)
- Extremely fast GPU non maximum supression.
- Full training and evaluation pipeline.
- Kmeans algorithm to select prior anchor boxes.

### 2. Requirements

conda activate yolo3

Python version:  3

Packages:

- tensorflow >= 1.14.0 
- opencv-python
- tqdm


### 3. Running demos

There are some demo images and videos under the `./data/demo_data/`. You can run the demo by:

Single image test demo:

```shell
python single_image.py ./data/demo_data/messi.jpg
```

Video test demo:

```shell
python video_test.py ./data/demo_data/video.mp4
```


Video ROV demo:

```shell
python videoROV.py ./data/demo_data/video.mp4 

```


### 4. Inference speed

How fast is the inference speed? With images scaled to 416*416:


| Backbone              |   GPU    | Time(ms) |
| :-------------------- | :------: | :------: |
| Darknet-53 (paper)    | Titan X  |    29    |
| Darknet-53 (my impl.) | Titan XP |   ~23    |

why is it so fast? Check the ImageNet classification result comparision from the paper:

![](https://github.com/wizyoung/YOLOv3_TensorFlow/blob/master/docs/backbone.png?raw=true)

### 6. Model architecture

For better understanding of the model architecture, you can refer to the following picture. With great thanks to [Levio](https://blog.csdn.net/leviopku/article/details/82660381) for your excellent work!

![](https://github.com/wizyoung/YOLOv3_TensorFlow/blob/master/docs/yolo_v3_architecture.png?raw=true)

