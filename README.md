# Line2Image
A mini project on image generation using CNNs.

## Method
1. Use the canny edge detection method to extract edges from the original images to simulate simpler sketches.
1. Use a U-Net model to create an output image of same size as input. (224,224,3)
1. Use the VGG16 network as a feature extractor to compare the generated image and the original image.
1. Use the root mean squared distance between the features as a loss. 

## Some more details
* Used a python generator to preprocess the original image to create training images. 
* Adapted the U-Net model infrastructure with the addition of some batch normalization layers.

## Results
* Model did not manage to generate the original image. (well that's kinda expected, since a sketch with a box shape could really turn out to be anything. e.g. a fridge)
* However, the model did somehow manage to generate pretty aesthetically pleasing "oil-painting" like images from the edges.
* But.. you'd still need a pretty decent artist to create a detailed enough sketch for the model to generate a good result. Perhaps I should have decreased the number of edges in the preprocessing step so that the input would have been much simpler images.

## Some examples generated from the model
<p align="center">
Lines  -------------- Generated Image ------------- Original

<p align="center">
  <img src="b2c2_example_1.JPG?raw=true" alt="b2c2 example 1" width=80%>
</p>


<p align="center">
  <img src="b2c2_example_2.JPG?raw=true" alt="b2c2 example 2" width=80%>
</p>


<p align="center">
  <img src="b2c2_example_3.JPG?raw=true" alt="b2c2 example 3" width=80%>
</p>

