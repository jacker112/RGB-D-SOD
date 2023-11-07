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


## Training
If you want to retrain our network, we recommend that you follow these steps.

1.Download the dataset and place it in the PD_dataset folder.[code:0617]https://pan.baidu.com/s/1PzjLo43pigzhCm-CxTyDIw

2.Modify the training parameters of the model in options.py. Such as batchsize, gpu_id.

3.Open a terminal and run python3 PDNet_train.py. The trained parameter model will be saved in the PDNet_cpts folder.

## Testing
If you would like to reproduce our results, please follow these steps.

1.We provide a link to download the parameters of the trained model, put it in the model_pths folder.

2.Open a terminal and run python3 PDNet_test.py. 


## Evaluation
If you would like to evaluate our entire model parameters through quantitative metrics, please follow these steps.

1.Download the results of our experiments and place them in any path.

2.The evaluation metric code has been placed in the eval_code folder, please use MATLAB to open it.

3.Modify the path to the dataset in main.m.

4.run main.m.
