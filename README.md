# RGB-D-SOD
Pluralistic depth-aware network for RGB-D saliency object detection

pytorch==1.8.0

torchvision==0.9.0

tensorboardX==2.5

opencv-python==4.5.5.64

# PDNet

The official repo of the paper `Pluralistic depth-aware network for RGB-D saliency object detection`.

## Abstract

RGB-D saliency detection mimics human attentional behavior by combining depth information and RGB information to locate the most salient regions in an image. Existing work usually samples the modification of the feature fusion module, thus neglecting the analysis of information extraction from the backbone network and the loss of feature information when the image is transformed at different scales. To address this issue, we propose a pluralistic depth-aware network (PDNet), which is dedicated to improving the feature information extraction ability of the backbone network and optimizing the depth image. In the encoding stage, we add pluralistic attention module (PA) to the backbone network, which enriches the high-level feature information and reduces the loss of information in the convolutional transform, which is a feature refinement process. In the stage of fusion of depth information and RGB information, we design the adaptive depth modification module (ADM), optimize the channel attention module, and develop the adaptive tuning function of attention for the characteristics of the channel transform ratio, which maximizes the depth filtering while retaining the uniqueness of the depth information. In the decoding stage, a depth-aware semantic extraction module (DSE) consisting of lightweight transformers is proposed to aggregate the high-level depth information and guide the low-level feature refinement through the lightweight transformers. The source code is available at https://github.com/jacker112/RGB-D-SOD.git.

## Framework Overview
The pipeline of CCINet is shown in the figure below. 

![fig01](https://github.com/jacker112/RGB-D-SOD/assets/148022707/189c9df7-9ac0-4842-b193-ca3c4a855927)



## Result
![fig11](https://github.com/jacker112/RGB-D-SOD/assets/148022707/77c65b25-4e4e-4fa5-abb1-c943e13de6ca)

- Comparison with excellent RGB-D SOD methods of recent years on NJUD, NLPR , SIP, STERE, LSFD, RGBD135 The smaller the MAE value the better. Larger values are better. Red font indicates the best performance.
  ![data_test](https://github.com/jacker112/RGB-D-SOD/assets/148022707/d5920c7c-fa9c-4d89-ae45-ec2b5b16334e)




## Prediction

![data](https://github.com/jacker112/RGB-D-SOD/assets/148022707/10f92d46-b263-47a6-8b7a-5d6fdab38e78)


## Environment Requirement

create environment and install as following: 


pytorch==1.8.0

torchvision==0.9.0

tensorboardX==2.5

opencv-python==4.5.5.64

## Data Format

trainset: COCO-SEG

testset: CoCA, CoSOD3k, Cosal2015

Put the datasets ([gts](https://pan.baidu.com/s/1A0cklgxqK2yPtYI7GNY62Q?pwd=7xo7) and [imgs](https://pan.baidu.com/s/1Bf3HfdDWMiV4MIaHu2MJQQ?pwd=scub)) to `CCINet/data` as the following structure:

```
CCINet
   ├── other codes
   ├── ...
   │ 
   └── data
         ├── gts
              ├── CoCo-SEG (CoCo-SEG's gt files)
         	  ├── CoCA (CoCA's gt files)
              ├── CoSOD3k (CoSOD3k's gt files)
              └── Cosal2015 (Cosal2015's gt files)
         ├── images
              ├── CoCo-SEG (CoCo-SEG's image files)
         	  ├── CoCA (CoCA's image files)
              ├── CoSOD3k (CoSOD3k's image files)
              └── Cosal2015 (Cosal2015's image files)
```

## Trained model

trained model can be downloaded from [papermodel](https://pan.baidu.com/s/1R-isw86_4UrCGNo2T2ubSg?pwd=koy2).

Run `test.py` for inference.

The evaluation tool please follow: https://github.com/zzhanghub/eval-co-sod

## Reproduction

reproductions by myself on RTX3090 can be found at [reproduction](https://pan.baidu.com/s/1R-isw86_4UrCGNo2T2ubSg?pwd=koy2).
