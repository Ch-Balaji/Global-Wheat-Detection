# Global-Wheat-Detection
This case study is focussed on detecting wheat heads from outdoor images of
wheat plants, including wheat datasets from around the globe. Using worldwide
data, you will focus on a generalized solution to estimate the number and size of
wheat heads.
These images in the training data are used to estimate the density and size of
wheat heads in different varieties. Farmers can use the data to assess health and
maturity when making management decisions in their fields.
The Global Wheat Head Dataset is led by nine research institutes from seven
countries: the University of Tokyo, Institut national de recherche pour
l’agriculture, l’alimentation et l’environnement, Arvalis, ETHZ, University of
Saskatchewan, University of Queensland, Nanjing Agricultural University, and
Rothamsted Research.

Goal: The goal is to predict bounding boxes around each wheat head in images
that have them. If there are no wheat heads, you must predict no bounding
boxes.

Data can be found from Kaggle -
https://www.kaggle.com/c/global-wheat-detection/data

Difficulties in the problem:
Wheat head detection in outdoor field images can be visually challenging. There
is often overlap of dense wheat plants, and the wind can blur the photographs.
Both make it difficult to identify single heads.
Additionally, appearances vary due to maturity, color, genotype, and head
orientation. Finally, because wheat is grown worldwide, different varieties,
planting densities, patterns, and field conditions must be considered.
This competition is evaluated on the mean average precision at different
intersections over union (IoU) thresholds.

First Cut Approach
1. Load the Data.
2. Check how many images we have for training and testing.
3. As this problem is regarding bounding boxes and wheat detection , we have to do
some sanity check on images in the given data.
4. Check weather bounding boxes are present for all the images in the training data
or not. If by chance there are images where there are no bounding boxes i think
it's better to represent them with 0 labels. [ Will get to this while i do EDA].
5. In this task we just need to detect wheat heads. So if a given image there will only
be 2 classes , either it will be wheat head or it will be considered as
background.so num_classes in this task is 2.
6. So create a dataframe with labelling classes as wheat_head for the images that
contain bounding boxes and 0 for the images that don't contain bounding boxes.
7. For EDA steps we can start to check distributions of the train data.
8. Check from what sources the images came and try to observe different kinds of
images from different sources.
9. Try to find the max and min number of boxes present in a given image. From this
we can conclude about the density of wheat heads in the images.
10. Visualize and see if the given ground truth bounding boxes are present in every
wheat head of the image or check if they missed to label some.
11. Once EDA is done, we split the dataset into train and cv and use image
augmentations for training the final model.
12. Most well versed object detection techniques are Faster RCNN and Yolo.
13. I will try to implement both of these techniques to train and will see which model
works best and what needs to change to further improve the score.
14. Metric uses are - IOU over bounding boxes.
15. I can also use TTA while making predictions for the test image dataset.
