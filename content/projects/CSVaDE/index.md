---
title: CSVaDE
summary: My thesis research for zero and few shot image classification
tags:
- zero-shot learning
- few-shot learning
- image classification
- python
date: "2020-08-24T10:00:00Z"

image:
  caption: "CSVaDE Model"
  focal_point: Smart

url_pdf: 'media/CSVaDE.pdf'
url_code: 'https://github.com/toliz/CSVaDE'
url_slides: "media/CSVaDE.pptx"
url_video: ""
---

This thesis studies the feasibility of an image classifier trained only on a subset of the categories of the dataset, while being able to classify all the categories in the dataset.For this to be possible, image categories are not provided as pure categorical data but contain some information for each category instead; information which can correlated to the optical information of the image for classifying image from seen and unseen categories.

More specifically, both image and their categories are represented by vectors. For images the vector representation is the penultimate layer of ResNet-101, although any similar architecture could be used to extract features. For image categories small datasets provide handcrafted vector descriptions, while for big datasets like ImageNet we can use methods like word2vec.

After vector representation are extracted for both modalities (image and text), two Variational Autoencoders (VAE) are aligned to encode these vector representations in a common embedding space. The alignment of the VAEs is such that an image is encoded in the same region where its category has been encoded, while regions from different categories are well seperated and their distance is inversely proportional to their semantical correlation.

Finally, a simple classifier model is trained to classify the regions in the embedding space according to the category encodings. Hence, after the training of the proposed model, images are encoded in the embedding space, hopefully in the same region where their category has been encoded, and then the classifier points out the category they belong.

The proposed model is tested in various datasets, both in the zero-shot and the few-shot setting. The thesis presents quantitive and qualitive experiments to better understand how the proposed method works.