# product_matching_with_shelf_images

<h2>Problem Statement</h2>
Given a set of images captured in grocery stores(shelf image), and a set of close up images of products in
those stores, your task is as follows.

1. For every product image, find the location of that product in all shelf images in which it appears.
2. For every shelf image, locate all products and assign the name from given set of product images.

<br>
Find the whole soluction look for master branch

Dataset: https://www.kaggle.com/datasets/amanindiamuz/store-shelf-images-and-product-images-for-retial

### Product Image
<a href="https://imgbb.com/"><img src="https://i.ibb.co/S02LRSL/test-product-img2.jpg" alt="test-product-img2" border="0"></a>

### Shelf Image
<a href="https://ibb.co/hW3VvdW"><img src="https://i.ibb.co/vP0k8dP/test-shelf-img2.jpg" alt="test-shelf-img2" border="0"></a>

## Approach : Feature Extraction and Matching
Feature Matching is one of the widely used area of Computer vision with countless applications.
In this approach, I have used "Brute-Force Matching with ORB Descriptors" for solving the probem statement.
Well, I have tried other methods too, Including:

<ul><li>Harris Corner</li>
  <li>SIFT(Scale Invariant Feature Transform)</li>
<li>SURF(Speeded Up Robust Feature)</li>
<li>FAST(Features from Accelerated Segment Test)</li></ul>
  
But,
Satisfactory results were from "Brute-Force Matching with ORB Descriptors".
Here are the steps included in the approach.

<ul>Steps included in the approach are :
  <li>Reading Product and Shelf Images</li>
<li>Cropping product images</li>
<li>Removing Background for feature Extraction</li>
<li>Extracting features using ORB Descriptors</li>
<li>Matching features using BFMatcher</li>
<li>Visualization</li>
<li>Saving detected product cordinates in soluction.txt file<li></ul>

<img src="https://github.com/mramanindia/product_matching_with_shelf_images/blob/master/download.png">


## Approach: Deep Learning
As per the problem statement, the major/logical part of the problem is object recognition.
<br>
Recognizing the product on the shelf (Image), saving the coordinates of bounding boxes, and vice-versa.

<br>
Well,<br>
One approach can be Feature mapping.
<br>
<br>
Using SIFT algorithm to match the features of the object in the image and based on that Saving the coordinates of the same.
<br>
Tough, there are limitations of Feature mapping technique, like different lightning conditions, Image clarity, Size of Image and others.
<br>
<br>
Thus,<br>
For a robust model and higher recognition accuracy, there needed something complex which works with a most possible scenarios by reducing the chance of error.

Thus, <br>
Training deep learning neural Network is prefrable.

Over here, <br>
My approach is to have a neural network trained on product images and then using pretrained model of object detection from shelf images to recognize the product.

So, <br> 
For training neural network, I used Transfer learning. Use pretrained model and trained it further on the product dataset, Where dataset was upscaled using data Argumentation.
Then
using pre-trained YOLOv5 network that detects items from shelf images, Then further object matching.

Here are the Steps in detail that involve in building the soluction.

<h4>Steps included in the approach are :</h4>
<ul>
    <li>Reading Product and Shelf Images</li>
    <li>Exploratory Data Analysis</li>
    <li>Labelling the Product Data</li>
    <li>Image Augmentation</li>
    <li>Splitting the Data for Training and Testing</li>
    <li>Training pretrained Neural Network - ResNet (Transfer learning) </li>
    <li>Testing and accuracy Measure</li>
    <li>Using a pre-trained YOLOv5 network that detects items from shelf images.
    <li>Use similarity between products to match product in shelf image : Resnet network has been used for this purpose.</li>
    <li>Writing in the soluction.txt file </li>
</ul>

Rest other details are in the jupyter notebook notebook file.



