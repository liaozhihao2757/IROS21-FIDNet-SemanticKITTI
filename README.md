# FIDNet_SemanticKITTI

## Motivation
Implementing complicated network modules with only one or two points improvement on hardware is tedious. So here we propose a LiDAR semantic segmentation pipeline on 2D range image just with the most commonly used operators: convolutional operator and bilinear upsample operator. The designed network structure is simple but efficient. We make it achieve the comparable performance with the state-of-the-art projection-based solutions. The training can be done on a single RTX 2080 Ti GPU. 

A demo video of our IROS paper on test set:
<br />
<img src="https://github.com/placeforyiming/IROS21-FIDNet-SemanticKITTI/blob/main/semantic.gif?raw=true" alt="Figure" style="width: 540px; height: 280px;" hspace="10" align="left"/>
<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
## Dataset Organization

    IROS21-FIDNet-SemanticKITTI
    ├──  Dataset
    ├        ├── semanticKITTI                 
    ├            ├── semantic-kitti-api-master         
    ├            ├── semantic-kitti.yaml
    ├            ├── data_odometry_velodyne ── dataset ── sequences ── train, val, test         # each folder contains the corresponding sequence folders 00,01...
    ├            ├── data_odometry_labels ── dataset ── sequences ── train, val, test           # each folder contains the corresponding sequence folders 00,01...
    ├            └── data_odometry_calib        
    ├──  save_semantic ── ResNet34_point_2048_64_BNTrue_remissionTrue_rangeTrue_normalTrue_rangemaskTrue_2_1.0_3.0_lr1_top_k0.15

    

## How to run

```` 
```
docker pull pytorch/pytorch:1.7.1-cuda11.0-cudnn8-runtime
```
````
For training inside the docker:
```` 
```
python semantic_main.py
```
````
For evaluate inside the docker:
````
```
python semantic_inference.py
```
````
Generate the test predictions:
````
```
python semantic_test.py
```
````
