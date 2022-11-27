# Fire-Detection-using-Mask-RCNN

## Business Objective

1. Fire is one of the deadliest risks any person can encounter in his life. In a concise time frame, fire can wreck an area, say in a forest, hut, house, building, etc. Fire can lead to the loss of expensive property, and in the worst possible scenario, it can also lead to the loss of human life. Detecting fire thus becomes a significant concern.

2. My project will carry out fire detection by adopting an RGB (Red, Green, Blue) model based on chromatic and disorder measurement for extracting fire pixels and smoke pixels. Our main aim is to locae the position where the fire is present, which will help the authorities take proper measures to avoid any loss. To prevent this, I am building an early fire detection using image segmentation with the help of the mrcnn model.

3. Image Localization helps to detect the location of a single object in any given image. In our case, image localization can locate the fire in a given image. We will be using image segmentation, in which we group a similar set of pixels, i.e., divide the image into segments and thus make use of the essential segments. Hence image segmentation is used in this project as it gives us the desired location of our
object in the image. Further, we will use the Mask RCNN model to train and build predictions over our input
images. 

## Data Description

1. In this case, I am using 20 fire images for the training set and 10 fire images for the validation set, and one image for test data. These images can be JPG, PNG, JPEG formats.

2. Via_project.json is the annotation file containing the region of interest marked.

## Aim
This project aims to make predictions over images and detect mask and bounding boxes around the area of interest, i.e., mask and bounding around the fire in a given image.

## Tech stack

 
 -> Language - Python

 
 -> Libraries – numpy, keras, tensorflow, mrcnn, scikit-image, etc

## My Approach

1. Install the requirements.txt file.

2. Import the required libraries.

3. Using the VGG Annotator, create annotations and save them in the JSON files. Then creating a class to add these annotations and use them. (Link for the VGG Annotator - https://www.robots.ox.ac.uk/~vgg/software/via/via_demo.html)

4. Define LoadDatatset class for loading of image data and annotations for train
and inference data.

5. The setting of the root directory for the project and the path of the weights file.

6. Define config class for setting configuration for training on the dataset.

7. Define the LoadBackBone for train and inference data class, for loading the backbone pre-trained weights to extract features.

8. Model Building (Using Mask RCNN)
 
	a. Overtraining data images
 	
	b. Over validation data images.

9. Predict the mask and then plot it over the test data images.


## Project code overview

1. input folder - It contains all the data that we have for analysis. These are three subfolders present in the dataset folder. These folders contain images along with the via_project.json files. Also, a rcnn coco.h5 file is present.
 
 -> Train (20 images)
 
 -> Test (1 image)
 
 -> Val (10 images)

2. src folder - This is the most important folder of the project. This folder contains the original ipython notebook of the project 

3. output folder – The output folder contains the logs generated after training the mrcnn model. A training model is saved per epoch in h5 format. The model is trained on 20 images and a h5 file is been generated. This model can be quickly loaded and used for future use and the user need by passing different set of images.
