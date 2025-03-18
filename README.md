# Torch and TorchVision R Improvements

This repository contains my submission for the R-GSOC project "torchvision in R improvements". The project aims to enhance the R interface for torch and torchvision, making computer vision models and datasets more accessible to R users.

## Background

`torch` is a powerful machine learning package for R, based on the LibTorch C++ library. `torchvision` provides additional functionality specifically for computer vision tasks, including pre-trained models, datasets, and image transformations. However, the R implementation of torchvision is currently missing several features compared to its Python counterpart. This project aims to address some of these limitations.

## Tasks Completed

### Easy Task: Gaussian Linear Model

For the easy task, I installed torch and created a simple Gaussian Linear Model using the instructions from the distributions vignette. The implementation demonstrates:

- Creating and visualizing synthetic data
- Building a custom neural network model with torch
- Training the model using autograd and optimization
- Comparing results with R's built-in `glm` function
- Visualizing the fitted model against the true relationship

The implementation is available in `easy.Rmd` with its rendered output as a PDF.

### Medium Task: Custom Dataset for Spam Classification

The medium task involved adapting the "Loading data" vignette to work with the spam dataset from "Elements of Statistical Learning". This implementation showcases:

- Creating a custom dataset class for email classification
- Implementing helper functions for data download and preprocessing
- Building a dataloader for efficient batch processing
- Creating a neural network for binary classification
- Training and evaluating the model on spam detection

The implementation is available in `medium.Rmd` with its rendered output as a PDF.

### Hard Task: Pull Request for Spam Dataset

For the hard task, I forked the torch repository and created a PR that adds a proper data loader for the spam dataset, complete with tests and documentation. This contribution makes the spam dataset easily accessible to other R users via the torch package.

PR link: https://github.com/mlverse/torch/pull/1294

## Repository Structure

```
.
├── README.md               # This file
├── easy.Rmd                # Source for the easy task (Gaussian Linear Model)
├── easy.pdf                # Rendered output of easy task
├── medium.Rmd              # Source for the medium task (Spam Dataset)
└── medium.pdf              # Rendered output of medium task
```

## How to Run

### Requirements

- R (>= 4.0.0)
- torch package
- knitr and rmarkdown for rendering the Rmd files

### Installation

```r
install.packages("torch")
install.packages(c("knitr", "rmarkdown"))
```

### Rendering the Documents

To render the Rmd files:

```r
rmarkdown::render("easy.Rmd")
rmarkdown::render("medium.Rmd")
```

