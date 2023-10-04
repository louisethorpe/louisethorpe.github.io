---
layout: post
title:  "Shapes to Sound"
date:   2023-10-04 09:31:00 +0100
categories: projects
---

# Introduction

Back in 2022, I finished up my master's degree and completed my dissertation project looking at the relationship between shape and sound. This was a side project to larger work being undertaken by Sebastian Löbbers - you can find his research [here](https://sebastianlobbers.com/). 

As part of my work, I used data collected by Sebastian to train a multi-class classifier to classify six categories of shapes to a corresponding sound descriptor and I was pretty happy with how the final results came out. Below is a confusion matrix showing the ground truth labelling against the predicted labelling. 

![confusion_matrix_ss](/assets/img/ss_heatmap.png)

Ok, so the confusion matrix looks a little bit messy - but you'll understand my reasoning for being happy with these results after I've explained my thinking.

# The Data

As I was using data collected from a small study, there wasn't much of it. BUT luckily, the sketches collected were stored in the same format of those in the [Quick, Draw!](https://github.com/googlecreativelab/quickdraw-dataset) dataset by Google - so I could make use of the machine learning technique transfer learning.

I selected six categories from the dataset that represented abstract shapes, these ended up being: *circle, line, square, sqiggle, tornado and zig-zag*. These categories had a lot more samples that the Sketching Sounds dataset (2500 per category vs 62 per catgeory) and could be used to pretrain the classification network. After this round of training, part of the network was frozen and the smaller training dataset was run through. To help a little bit, data augmentation was applied via a random scaling of sketches for both datasets.

# The Network

![terrible_network_diagram](/assets/img/classification_network.png)

# The Results!

<!-- ![confusion_matrix_qd](/assets/img/qd_heatmap.png) -->
