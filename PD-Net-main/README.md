# PD-Net
A Cascaded Refined RGB-D Salient Object Detection Network Based on the Attention Mechanism

## Experimental environment 

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
