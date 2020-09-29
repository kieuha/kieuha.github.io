---
layout: post
title:      "formatted like this"
date:       2020-09-29 06:04:30 +0000
permalink:  formatted_like_this
---

[](http://)X-Ray Images Analysis with CNN


1.	Introduction

Background:

Artificial neural networks have a history dated back in 1943 when Warren McCulloch, a neurophysiologist, and a young mathematician, Walter Pitts, wrote a paper on how neurons might work. They modeled a simple neural network with electrical circuits [1].

Convolutional neural network (CNN) has become a popular model for image and pattern recognition in recent years. But the first single-layer model (ADALINE) was developed at Stanford University by professor Bernard Wildrow and his students in 1959 [1]. It consists of a weight, a bias, and a summation function. The main purpose was to recognize binary patterns by reading streaming bits from a phone line and predict the next bit. Today, it is still used by air traffic control systems. The second model (MADALINE) was developed with 3 layers (input, hidden, and output). It is a fully connected and feeding forward artificial neural network that uses ADALINE units in its hidden and output layers. In 1975, a true multilayered neural network model was developed by Kunihiko Fukushima. The goal was to create a computer that can solve complicated problems like a human brain [1].

What is a neural network?
Neural networks are densely interconnected meshes of simple information processors that learn to perform tasks by analyzing huge sets of training data. A neural network, in general, is a highly interconnected network of billions of neurons with trillion interconnections between them [2].

How does it work?
A neural network is a network of neurons that is composed of artificial neurons or nodes. The connections of the neuron are modeled as weights. A positive weight reflects an excitatory connection, while negative values mean inhibitory connections. The basic building blocks of CNN are convolution, pooling, fully connected layer, and output [2].

The input is images with shape (number of images), image height, and depth. These images first pass through a layer called the convolution layer. Here, the data is labeled to create a feature map that has "stationary" properties. In this case of x-ray images, the feature could be the outline of the thoracic cavity, two lungs, and the ribs.

Pooling is a down-sampling operation that reduces the dimensionality of the feature map. The rectified feature map now goes through a pooling layer to generate a pooled feature map. This is achieved by passing the feature map through the whole image one section at the time. A 4x4 matrix for example is reduced to a 2x2 matrix through size filtering, striding, and max or averaging. Image reduction also helps to speed up the computation.
The next and final step in the process is flattening which results in one single long continuous linear vector which is the input of the fully connected layer. The outcome is the identification of the image.
Convolutions have three main advantages: reducing overfitting, reducing computational cost, and extracting representative features from input tensor.

2.	Data

The data came from Kaggle. The dataset is organized into 3 folders (train, test, val) and contains subfolders for each image category (Pneumonia/Normal). There are 5,863 X-Ray images (JPEG) and 2 categories (Pneumonia/Normal). Chest X-ray images (anterior-posterior) were selected from retrospective cohorts of pediatric patients of one to five years old from Guangzhou Women and Children’s Medical Center, Guangzhou. All chest X-ray imaging was performed as part of patients’ routine clinical care. For the analysis of chest x-ray images, all chest radiographs were initially screened for quality control by removing all low quality or unreadable scans. The diagnoses for the images were then graded by two expert physicians before being cleared for training the AI system. In order to account for any grading errors, the evaluation set was also checked by a third expert.

3.	Conclusion

Neural networks build up their understanding of images through textures, patterns, edges, parts, and objects. The model has an accuracy scores of 94% using 234 normal images and 390 pneumonia positive images. As shown in feature map visualization, the model successfully extracted different features of the image. The proposed model can be served as an independent method to verify x-ray-technologists on pneumonia diagnosis. Analyzing x-ray images by the model offers many advantages such as its ability to quickly scan through images and classify them. Thousands of images can be done in the matter of hours. As the result, x-ray images analysis can help lower the cost of the treatment and provide doctors with information quicker and reduce clinician workload significantly.

References

1. Neural Networks. Standford University. https://cs.stanford.edu/people/eroberts/courses/soco/projects/neural-networks/History/history1.html

2. Rikiya Yamashita, Mizuho Nishio, Richard Kinh Gian Do, Kaori Togashi Insights Imaging. 2018 Aug; 9(4): 611–629. Published online 2018 Jun 22. doi: 10.1007/s13244-018-0639-9


