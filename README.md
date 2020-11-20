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
