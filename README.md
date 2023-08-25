# SSL-Histopathology Image Retrieval

## Description

This project implements an image retrieval system for histopathology images using various self-supervised learning models from the solo library. The goal is to retrieve similar histopathology images given a query image.

The following self-supervised models from solo are explored:

- nnCLR - A simple framework for contrastive learning.
- SimCLR - A simple framework for contrastive learning with larger batch sizes.
- Barlow Twins - Learns representations by predicting redundancy between augmented samples.
- SwAV - Learns representations by clustering using a swapping prediction.

## Models  

The above models are pretrained on unlabeled image datasets like ImageNet using the solo library to learn visual representations in a self-supervised manner, without human annotations.

In this project, each model is used as an image encoder. Histopathology images are passed through the encoders to generate feature vectors for indexing and retrieval. 

The different models are compared and evaluated to determine which provides the best feature representations.

## Datasets

The models are trained and evaluated on:

- [BracS](https://www.bracs.icar.cnr.it/) - Breast Cancer Histopathology Images
- [CRC](https://warwick.ac.uk/fac/cross\_fac/tia/data/extended\_crc\_grading/) - Colorectal Cancer Histopathology Images
- [BATCH](https://iciar2018-challenge.grand-challenge.org/Dataset/) - BreAst Cancer Histology Images 

## Usage

A query histology image can be uploaded to the retrieval system. The dataset is indexed based on embeddings from each model to find the most similar images, which are returned ranked by similarity.

The project provides code to train the self-supervised models using solo on histopathology data and utilities for indexing/retrieval.

## References

- [solo](https://github.com/vturrisi/solo-learn)
- [nnCLR](https://arxiv.org/abs/2104.14548)  
- [SimCLR](https://arxiv.org/abs/2002.05709)
- [Barlow Twins](https://arxiv.org/abs/2103.03230)
- [SwAV](https://arxiv.org/abs/2006.09882)
