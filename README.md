## Building Artistic Paintings 
### Neural Style Transfer using PyTorch
----------

## Description
NST(Neural Style Transfer) works on the concept that a pretrained convolution neural network (CNN) can we used  to transfer content from one image and styles from a another image to blend them together to form a new image which has content of content image and style of style image.
<img src="./Assets/collage.png" alt="batch of image"/>

### The code has been implemented using PyTorch based on the paper <br/>
* [https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)

## Neural Style Transfer

 Below are the various process for implemeting NST . The key points to be followed are:

1. Loading Images and Applying transforms:
   - Loading the content image and style image and resizing them for faster processing and converting them into Tensors.

2. Loading the Pertrained VGG19 Model:
   - Loading the Pretrained VGG19 model and freezing the layers so that no gradient computation or the update of gradients takes place.
   - We only need the convolution layers of the model or the features layers as we are not training any classifier.
   - As the model is already trained with large no of images we will be using its convolution layers to extract the content and style of the images using these convolution layers.

3. Getting the content from differenet layers and creating gram matrix:
   - To get the content of the image we need to pass through the various convolution layers of vgg model.
   - Style refers to the colour and texture of present in the image. To get the style of an image we we find the correlation    between different conv layers which can be found by a gram matrix.


4. Defining content and Style Loss, and Comparing it with target image:
   - We define the content and target loss by comparing the content of the target image with content of the  content image and style loss by comparing the gram matrix of target and style image. 

5. Initializing style weights for each layers and style and content weight to balance the losses:
   - We define style weights for each indvidual style layers.We give initial layers a higher value than lower layers.

   - We define weights for content weight(alpha) and style weight(beta) so that both maintain an equal balance between both losses.
     Usually alpha is smaller and beta is larger. As beta increses we see more style in target image.  


6. Various Content and Style images tried along with Learning Rate and Different values of weights:
<center>
  <img src="./Generated Images/house.jpg" alt="generated images" height="250"/>
  <img src="./Generated Images/football.jpg" alt="generated images" height="250"/>
  <img src="./Generated Images/girl_painting.jpg" alt="generated images" height="250"/>
</center>
  


## Usage:

### Code for all the various combination tried:
   - Combination of House and Paintings: [House-Painting](Image_Style_Transfer[Building].ipynb)
   - Combination of Girl and Paintings: [Girl-Painting](Image_Style_Transfer[Girl].ipynb)
   - Combination of Football and Paintings: [Footbal-Painting](Image_Style_Transfer[Football].ipynb)  


<!-- ## Explanation of the Code: -->
<!-- `To understand the code :` You  can find the complete explanation to the code in [Article](https://medium.com/@soumyajit4419/plant-ai-c8fc95ed90e6?source=friends_link&sk=4707825cbaefa2dcaaa92d0e3ed5de01) -->