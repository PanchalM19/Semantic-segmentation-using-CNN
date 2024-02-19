# Semantic-segmentation-using-CNN

Our report focuses on Semantic Segmentation, a method that provides a detailed pixel-wise representation of an image's contents and their locations. It's crucial for perceiving dynamic objects and free road spaces simultaneously. Semantic Segmentation classifies each pixel in an image, enabling understanding of both dynamic elements (vehicles, pedestrians) and static elements (roadways, pedestrian walkways). Conducting Semantic Segmentation on camera data offers a comprehensive view, aiding tasks like object detection and scene understanding in applications like autonomous driving and surveillance.

We have performed semantic segmentation using the two models, UNet and SegNet and ran them with two different encoder architectures, VGG-16 and ResNet-50. For comparison, we calculated the mean Intersection over Union (mIoU) for all these 4 models.

## Dataset
The model was trained on the Cityscapes dataset, which contained training and test images. It also had the segmentation masks in the black and grey format, which was preferable. The images had good amount of instances for every class, which was good for training. The efficiency of training can be seen from the table in the conclusions. It shows how well the
architecture-encoder model can predict the segmentation classes in the test images. 

## Models
Ssemantic segmentation was perfomed using two models: UNet and SegNet. These models were chosen for their encoder-decoder architecture, facilitating efficient upscaling by utilizing encoder information at each decoder step. 

### U-Net
<img width="250" alt="image" src="https://github.com/PanchalM19/Semantic-segmentation-using-CNN/assets/115374409/0f6771c1-d37c-41f2-a897-6556c0f2485d">

### SegNet
<img width="250" alt="image" src="https://github.com/PanchalM19/Semantic-segmentation-using-CNN/assets/115374409/aea6d1c3-740d-47a0-af48-7274c5dcf005">

## Encoders
To analyze the impact of model backbones, or encoders, we experimented with classical and modern Convolutional Neural Networks (CNNs). For the classical approach, VGG-16 was selected due to its extensive usage and resource availability. For the modern approach, ResNet50 was chosen for its introduction of residual blocks, aiding in loss reduction and yielding efficient results over time.

### VGG-16
<img width="250" alt="image" src="https://github.com/PanchalM19/Semantic-segmentation-using-CNN/assets/115374409/1c64a6aa-76d6-4434-8a7a-4ea3b997ab9f">

### ResNet50
<img width="250" alt="image" src="https://github.com/PanchalM19/Semantic-segmentation-using-CNN/assets/115374409/170ea93f-8a7e-437b-8e8b-56e1734225a4">

## Results

### 1. U-Net + ResNet50
![image](https://github.com/PanchalM19/Semantic-segmentation-using-CNN/assets/115374409/c28406e8-3b8d-4409-88d5-c3009a54a6fe)

### 1. U-Net + VGG-16
![image](https://github.com/PanchalM19/Semantic-segmentation-using-CNN/assets/115374409/e12fe51b-443f-4471-af35-a04223e497b9)


### 1. SegNet + ResNet50
![image](https://github.com/PanchalM19/Semantic-segmentation-using-CNN/assets/115374409/ac9917b9-2fe3-45a8-b78c-418eb257196e)


### 1. SegNet + VGG-16
![image](https://github.com/PanchalM19/Semantic-segmentation-using-CNN/assets/115374409/ba30656c-803a-4380-a859-d5886eb57779)


## Evaluation: mIOU

IoU is the comparison of how much the prediction differs from the ground truth. This value helps in understanding the accuracy of the model. As mean IoU (mIOU) function is differentiable, it can be used to understand the losses and thus introduce steps to better train the model. We have used an open-source image segmentation repository and used its API’s for our models. We have chosen this because the code base is flexibile and can be customized by adding extra layers to make the architectures better.

<img width="250" alt="image" src="https://github.com/PanchalM19/Semantic-segmentation-using-CNN/assets/115374409/001371d1-648e-4a36-aa4a-f0c7195cdb77">

## Conclusion

When it comes to the backbones, we can concluded that the semantic segmentation network performs better when VGG-16 serves as the network’s main component when extracting long and wide roads. ResNet, which serves as the foundation of the semantic segmentation network, is better at extracting minor roads.

We also observed that for the UNet model, the stationary objects were clearly classified, However, the moving objects, i.e. the pedestrians, bicyclists and cars were not effectively classified. The same issue was observed with the model with SegNet and VGG backbone. The best results were obtained with the SegNet model with ResNet backbone
