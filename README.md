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

![fig2high](https://github.com/jacker112/RGB-D-SOD/tree/main/PD-Net-main/paper_image/fig01.png)


## Result

- Comparisons with the excellent CoSOD methods in recent years on three benchmarks, CoCA, Cosal2015 and CoSOD3k. The value of MAE is the smaller, the better. While others are the larger, the better. Black bold fonts indicates the best performance.

<img width="468" alt="result_all" src="https://github.com/JoeLAL24/CCINet/assets/100739402/a4688225-8bd5-483a-976c-b30706a07e63">

- Ablation study:

<img width="259" alt="tab2" src="https://github.com/JoeLAL24/CCINet/assets/100739402/3ae56ddb-da40-423c-8afb-9d353346ba80"> <img width="257" alt="tab3" src="https://github.com/JoeLAL24/CCINet/assets/100739402/14c8a49c-e8fe-4546-a605-53beaccf1e7a">

<img width="256" alt="tab4" src="https://github.com/JoeLAL24/CCINet/assets/100739402/3c0bcb22-c82e-4b53-9f38-f70663efc576"> <img width="259" alt="tab5" src="https://github.com/JoeLAL24/CCINet/assets/100739402/3087f007-5eef-4835-a6ab-f9cbbe2b4cff">

## Prediction

![fig5high](https://github.com/JoeLAL24/CCINet/assets/100739402/706d4e35-fcd9-4bb2-8fbf-9781fade913c)

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
