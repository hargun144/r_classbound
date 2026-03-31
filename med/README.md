# Medium Test: Grand Tour Boundary Comparison

## Overview
Used grand tour from the tourr package to compare decision boundaries 
of rpart and PPtreeExt on the data69_1 dataset (5000 obs, 21 variables, 3 classes).
This reproduces Figure 11b and 11c from the PPtreeExt paper.

## Results
- rpart produces axis-aligned splits visible as sharp rectangular boundaries
- PPtreeExt produces oblique splits that better capture the data structure

## rpart Tour
![rpart tour](rpart_tour.gif)

## PPtreeExt Tour  
![PPtreeExt tour](pptreeext_tour.gif)

