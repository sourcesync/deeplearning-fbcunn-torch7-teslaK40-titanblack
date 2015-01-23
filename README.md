# fbcunn-torch7-teslaK40-titanblack

I run Deep machine learning algorithms on a system with super high end GPU cards from Invidia. It wasn't easy getting that up and running :)  I hope these instructions and examples are useful to any of you having trouble getting your cards humming. 

If you are up and running, then checkout my examples below.  They should be useful starting points for your own work.

[ This is a work in progress so bear with me...]

# Installation

## Prerequisites

* Ubuntu 14.04 LTS
* One or both already installed:
    *  TeslaK40 NVidia Graphics Card
    *  Titan Black NVidia Graphics Card

## Updating Ubuntu

Run the following command:
```
sudo apt-get update
```

## Checking Your Hardware

Run the following command:
```
lspci
```
You should see your NVidia Graphics card(s) and its PCI Address.  For example, my K40 looks like this:

```
...
05:00.0 3D controller: NVIDIA Corporation GK110BGL [Tesla K40c] (rev a1)
...
```

## Installing The Cuda Drive

[ TBD ]

## Installing the Cuda Sample Code

[ TBD ]

## Running DeviceQuery

[ TBD ]

## Installing IPython

[ TBD ]

## Installing Facebook FAIR Torch7 Deep Learning Libraries

[ TBD ]

# Examples

[ TBD ]

## iTorch/ConvNet_On_Cifar_GPU

This is an iTorch script, based entirely on Soumith Chantala's excellent example [ LINK ], presented at the NextML Workshop at Galvanize SOMA in January 2015.  I've made a few changes which demonstrate how to marshal tensors to the GPU memory.

## iTorch/Siamese_On_Pose_GPU

### Download The Sample Data

[ Instructions ]

### Run ITorch Script

[ Instructions ]

# Docker Images

[ Experimental ]
