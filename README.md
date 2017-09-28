# README

This is the skeleton code for the 2017 Fall ECE408 / CS483 course project.
In this project, you will get experience with practical neural network artifacts, face the challenges of modifying existing real-world code, and demonstrate command of basic CUDA optimization techniques.
Specifically, you will get experience with

* Managing a simple machine-learning dataset.
* Using, profiling, and modifying MxNet a standard open-source neural-network framework.

You will demonstrate your CUDA expertise by

* Implementing an optimized neural network layer
* merged layer
* fp16
* anything else?

The project will be broken up into 3 milestones

## Deliverables Overview

1. [Milestone 1: Getting Started: Due ()](#markdown-header-milestone-1)
    1. [Train the baseline network on the CPU.]()
    2. [Train the baseline network on the GPU.]()
    3. [Generate a profile of the GPU training using `nvprof`.]()
2. [Milestone 2: A New Layer in MXNet: Due ()](#markdown-header-milestone-2)
    1. []()
3. [Final Submission 3: Optimized GPU Forward Implementation](#markdown-header-milestone-3)
    1. []()
    2. [Final Report](#markdown-header-final-report)

## Milestone 1

### Getting Set Up and Getting Bugfixes

Clone this repository and skeleton code submodule.

    git clone https://cwpearson@bitbucket.org/hwuligans/2017fa_ece408_project.git --recursive

If a bug in the skeleton code is fixed, you can pull an updated version of the skeleton code with 

    git submodule update --recursive --remote

There may be unstable "improvements" in the `develop` branch of this repository.

### Install Prerequisites for Building `mxnet`.

The MxNet instructions are available [here](https://mxnet.incubator.apache.org/get_started/install.html). A short form of them follows.

    sudo apt install -y build-essential git libopenblas-dev liblapack-dev libopencv-dev

### Build mxnet library

Build the skeleton code

    cd 2017fa_ece408_mxnet_skeleton
    make

### Build Python Bindings

    sudo apt install -y python-dev python-setuptools python-numpy python-pip

Install the python binding

    cd python
    pip install --user -e .

You can always uninstall the python package with

    pip uninstall mxnet

This will uninstall anything installed with `--user` before anything else.

### (optional) Augment the fashion-mnist dataset

### 1.1 Train the baseline CPU implementation

Install quilt to get an update version of the data:

    pip install --user quilt

A simple convolutional neural network is implemented in `fashion-mnist-base.py`.
Read the comments in that file to understand the structure of the network.

Adjust your performance expectations based on whether you're using CUDA or CUDNN.

| Context  | Performance  |
|---|---|
| (CPU) Core i7-5820k          | 450 images/sec  |
| (GPU) GTX 1070         | 8k images/sec   |
| (GPU) GTX 1060 w/cudnn | 14k images/sec  |
| (GPU) GTX 1070 w/cudnn | 70k images/sec  | 

You should achieve an accuracy of XXX after XXX iterations.

### 1.2 Train the baseline GPU implementation

### 1.3 Generate a NVPROF Profile

Once you've gotten the appropriate accuracy results, generate a profile.

    nvprof fashion-mnist.py

## Milestone 2: A New Convolution Layer in MxNet: Due ()


### 2.1 Add a simple CPU forward implementation

Modify `src/operator/custom/ece408.cc` to implement the forward CPU operator. 

## Final Submission: An optimized layer

### Optimized Layer

### Final Report

## Extras

### Setting up Visual Studio Code

    sudo apt install python-pip
    pip install --user quilt numpy pylint pep8 autopep8