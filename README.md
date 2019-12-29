# EIP4_Phase1_Final
Train like Super Saiyan
### Final Score
     val_gender_output_acc	      0.886319
     val_image_quality_output_acc	0.562008
     val_age_output_acc	          0.435039
     val_weight_output_acc	      0.619587
     val_bag_output_acc	          0.670276
     val_pose_output_acc	        0.855315
     val_footwear_output_acc	    0.670768
     val_emotion_output_acc	      0.679134
### Model Name
    Wide ResNet (base Model Code: https://github.com/titu1994/Wide-Residual-Networks)
    File Name In Repo:
    	FinalModel_Assignment5.ipynb
    	https://github.com/rajy4683/EIP4_Phase1_Final/blob/master/FinalModel_Assignment5.ipynb
### Training Methodology
    1. Initialize Method
    2. Default Batch Size = 16
    3. LR Range test
    4. Loss Weights Ratio:
       {'gender_output': 2, 
        'image_quality_output': 2, 
        'age_output': 4, 
        'weight_output': 3, 
        'bag_output': 3, 
        'pose_output': 3, 
        'footwear_output': 2, 
        'emotion_output': 4}
####  Training Stages
    1. Stage1 - Convergence procedure to stabilize loss:
       a. Epochs=100 Steps_per_epoch=30
       b. Epochs=100 Steps_per_epoch=100
       c. Epochs=100 Steps_per_epoch=200
       d. Epochs=30 Steps_per_epoch=720 (Train_size/Batch_size)
    2. Stage 2 
        a. Small Steps_per_epoch
        b. Augmentation strategy change
        c. Loss_weights tweaks
    3. Stage 3:
        c. Max Steps_per_epoch runs 3x30 runs
    4. Stage 4:
        a. Final round of subsequent runs
	   
####   Accuracy at Various stages  
                                  Stage1  Stage2  Stage3  Stage4
     val_gender_output_acc	      0.8233	0.8489	0.8853  0.886319
     val_image_quality_output_acc	0.5536	0.5399	0.5576  0.562008
     val_age_output_acc	          0.4026	0.4173	0.4134  0.435039
     val_weight_output_acc	      0.6083  0.6156  0.626   0.619587
     val_bag_output_acc           0.6427  0.6565	0.6811	0.670276
     val_pose_output_acc          0.8081	0.8361	0.8538	0.855315
     val_footwear_output_acc      0.658   0.6708	0.6683	0.670768
     val_emotion_output_acc       0.7077	0.6944	0.686   0.679134


### Other Models Tried
	1. WIDE Resnet with Depth=16 Width=2 and Separable Conv2D 
	2. Modified DavidNet with 3 Layer Depth, Separable Conv2D.
	3. ResNet50v2
	4. InceptionV3
	5. Simple CNN with Separable Conv2D
#### Useful tools:
	1. Plotter Notebook for monitoring Training progress
