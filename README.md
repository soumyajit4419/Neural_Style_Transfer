## Building Artistic Paintings [Image Style Transfer]
----------

## Description
NST(Neural Style Transfer) works on the concept that a pretrained convolution neural network (CNN) can we used  to transfer content from one image and styles from a another image to blend them together to form a new image which has content of content image and style of style image.
<img src="./Assets/collage.png" alt="batch of image"/>

### The code has been implemented using PyTorch based on the paper <br/>
* [https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)

## Neural Style Transfer

 Below are the various process for implemeting NST . The key points to be followed are:

1. Loading Images and Applying transforms
- 

2. Loading the Pertrained VGG19 Model
   - I have used pytorch for building the model.
   - I used three models:-
      1. The CNN model architecture consists of CNN Layer, Max Pooling, Flatten a Linear Layers.
      2. Using Transfer learning VGG16 Architecture.
      3. Using Transfer learning resnet34 Architecture.

3. Getting the content from differenet layers and creating gram matrix.

   The model was trained  by  using variants of above layers mentioned in model building and by varying hyperparameters. The best model was able to achieve 98.42% of test accuracy.

4. Initializing style weights and style and content weight

5. Defining content and Style Loss, and Comparing it with target image.

   The model was tested on total 17572 images of 38 classes.<br/>
   The model used for prediction on sample images. It can be seen below:
   <!-- <img src="" alt="index1" height="300px"/> -->
   <div align="center">
   <img src="./Assets/out1.png" alt="index2" height="300px" width="500"/>
   <img src="./Assets/out2.png" alt="index3" height="300px"  width="500"/>
   </div>
6. Various Model Architecture tried along with Learning Rate and Optimizer and various accuracy obtained with different models.
 
  <img src="./Assets/models.png" alt="models" />

  

## Usage:

### Code For Model Building and Training  
   Refer to the notebook [Code](Src)  

### The reseach paper according to which this code has been implemented:-
   Research Paper:- [https://github.com/soumyajit4419/Neural_Style_Transfer/tree/master/Paper](https://github.com/soumyajit4419/Neural_Style_Transfer/tree/master/Paper)


## Explanation
`To understand the code :` You  can find the complete explanation to the code in [Article](https://medium.com/@soumyajit4419/plant-ai-c8fc95ed90e6?source=friends_link&sk=4707825cbaefa2dcaaa92d0e3ed5de01)