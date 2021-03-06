## Introduction

This folder contains an example ZenML pipeline for a Style Transfer workflow using the CycleGAN architecture.

Most of the code for the actual Tensorflow implementation of the CycleGAN model was taken from
the [CycleGAN tutorial](https://www.tensorflow.org/tutorials/generative/cyclegan) in the Tensorflow documentation.

The data for this tutorial has been sourced from and is licensed according
to [the original CycleGAN repository](https://github.com/junyanz/CycleGAN).

## Citation

Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks.

Jun-Yan Zhu*, Taesung Park*, Phillip Isola, Alexei A. Efros

Berkeley AI Research Lab, UC Berkeley

IEEE International Conference on Computer Vision (ICCV) 2017. (* equal contributions)

## Code explanation

The code for the tutorial is structured according to our recommendation on repository structure. The `preprocessing`
folder contains the preprocessing code and ZenML step. The `trainer` folder contains the CycleGAN model implementation
as well as the TrainerStep that handles data sourcing and preparation.

The `prepare_gan_images.py` script can be used to generate a labels.json file for use in the ZenML image pipeline.
Simply set the (hardcoded) paths inside the file to the image folder locations on your machine.

The `cycle_gan.ipynb` notebook is the main Jupyter Notebook object of this tutorial. Executing it runs a ZenML pipeline
on an example image dataset persisted in a public Google Cloud Storage bucket. In addition, it contains an optional 
tutorial on running the same workload with a deployment step on Google Cloud AI Platform, and shows how to obtain 
styled images by sending prediction requests to the deployed model over a Google API client.
