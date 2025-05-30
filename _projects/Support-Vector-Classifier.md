---
layout: project
title:  "Support Vector Classifier for Raisin Classification"
subtitle: "An application of Support Vector Classifiers created for Machine Learning in Spring 2025."
date:   2025-03-05 13:18:22 -0500
background: ""
---
# Support Vector Classifier for Raisin Classification

## Overview
### Machine Learning Technique

A support vector classifier (SVC) is a method for classifying data into different groups. The method works to find the best seperation to maximize the distance between the 'support vectors', or closest points, within each class.

### Program's Purpose

This program is used to classify raisin types based on the given features of area, major and minor axis lengths, exxentricity, convex area, extent, and perimeter. Based on these features, the SVC will classify a variety of raisins as either Besni or Kecimen.

## Data

This program uses images from the [Raisin Dataset](https://www.kaggle.com/datasets/nimapourmoradi/raisin-binary-classification). Each raisin variety, Besni and Kecimen, have 450 data entries. The features provided for each entry are broken down as follows:

Area - The number of pixels of the raisin
Major Axis Length - Longest line that can be drawn across
Minor Axis Length - Shortest line that can be drawn across
Eccentricity - ratio of the distance from any point to the focus to the directrix
ConvexArea - The number of pixels of the smallest convex shell
Extent - Ratio of raisin pixels to total pixels in the bounding box
Perimeter - Distance between the boundaries of the raisin and the box

## Project Run Through

### Initialize and Find Data

Uses a test/train split with a test size of 30% to seperate the data.

Then ran a grid search to find the optimal C and gamma parameters.

<img src="https://github.com/user-attachments/assets/273a1967-8594-4900-981d-bc740dec78bc" alt="Grid Search Results" width="500"/>

### Results

The final accuracy on the test set is 0.9148. The confusion matrix below details these results further. But although the difference between the misclassifications is small, the SVC more often predicts Besni raisins as the Kecimen variety.

<img src="https://github.com/user-attachments/assets/878e0654-b36d-4f7f-a284-791110261f58" alt="Confusion Matrix" width="500"/>

## Reflection

The score as accuracy (# correct) works well to measure the results. The dataset is perfectly balanced between the two varieties. As well as this, false negatives and false positives are not necessarily harmful with this data as they would be with other topics.
