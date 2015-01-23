# deeplearning-fbcunn-torch7-teslaK40-titanblack

I run Deep machine learning algorithms on a system with super high end GPU cards from Invidia. It wasn't easy getting that up and running :)  I hope these instructions and examples are useful to any of you having trouble getting your cards working.

If you are up and running, then checkout my examples below.  They should be useful starting points for your own work.

[ This is a work in progress so bear with me...]

# Installation

## Prerequisites

* Ubuntu 14.04 LTS
* One or both already installed:
    *  TeslaK40 NVidia Graphics Card
    *  Titan Black NVidia Graphics Card
* GCC development environment
* Uninstall any previous cuda libraries, drivers, and source code

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

## Installing The Cuda 6.5 Driver

Download the DEB package file from NVidia called [cuda-repo-ubuntu1404_6.5-14_amd64.deb](https://developer.nvidia.com/cuda-downloads)

Run the following command to determine uninstalled dependencies:
```
sudo dpkg -i cuda-repo-ubuntu1404_6.5-14_amd64.deb
```
Install the dependencies:
```
sudo apt-get install -f
```
Install cuda:
```
sudo dpkg -i cuda-repo-ubuntu1404_6.5-14_amd64.deb
```

## Test The Cuda Driver
Install the nvidia-smi utilities
```
sudo apt-get install nvidia-smi
```
Run nvidia-smi:
```
nvidia-smi
```
You should see something like this:
```
+------------------------------------------------------+                       
| NVIDIA-SMI 340.65     Driver Version: 340.65         |                       
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  Tesla K40c          Off  | 0000:05:00.0     Off |                    0 |
| 23%   32C    P0    63W / 235W |     23MiB / 11519MiB |    100%      Default |
+-------------------------------+----------------------+----------------------+
                                                                               
+-----------------------------------------------------------------------------+
| Compute processes:                                               GPU Memory |
|  GPU       PID  Process name                                     Usage      |
|=============================================================================|
|  No running compute processes found                                         |
+-----------------------------------------------------------------------------+
```

## Install the Cuda Sample Code

The following will install the cuda source code into your home directory:
```
/usr/local/cuda/bin/cuda-install-samples-6.5.sh ~
```
## Build the Cuda Sample Code
```
cd ~/NVIDIA_CUDA-6.5_Samples; make
```

## Running DeviceQuery
```
cd ~/NVIDIA_CUDA-6.5_Samples/1_Utilities/deviceQuery; ./deviceQuery
```
You should see something like this:
```
 CUDA Device Query (Runtime API) version (CUDART static linking)

Detected 1 CUDA Capable device(s)

Device 0: "Tesla K40c"
  CUDA Driver Version / Runtime Version          6.5 / 6.5
  CUDA Capability Major/Minor version number:    3.5
  Total amount of global memory:                 11520 MBytes (12079136768 bytes)
  (15) Multiprocessors, (192) CUDA Cores/MP:     2880 CUDA Cores
  GPU Clock rate:                                745 MHz (0.75 GHz)
  Memory Clock rate:                             3004 Mhz
  Memory Bus Width:                              384-bit
  L2 Cache Size:                                 1572864 bytes
  Maximum Texture Dimension Size (x,y,z)         1D=(65536), 2D=(65536, 65536), 3D=(4096, 4096, 4096)
  Maximum Layered 1D Texture Size, (num) layers  1D=(16384), 2048 layers
  Maximum Layered 2D Texture Size, (num) layers  2D=(16384, 16384), 2048 layers
  Total amount of constant memory:               65536 bytes
  Total amount of shared memory per block:       49152 bytes
  Total number of registers available per block: 65536
  Warp size:                                     32
  Maximum number of threads per multiprocessor:  2048
  Maximum number of threads per block:           1024
  Max dimension size of a thread block (x,y,z): (1024, 1024, 64)
  Max dimension size of a grid size    (x,y,z): (2147483647, 65535, 65535)
  Maximum memory pitch:                          2147483647 bytes
  Texture alignment:                             512 bytes
  Concurrent copy and kernel execution:          Yes with 2 copy engine(s)
  Run time limit on kernels:                     No
  Integrated GPU sharing Host Memory:            No
  Support host page-locked memory mapping:       Yes
  Alignment requirement for Surfaces:            Yes
  Device has ECC support:                        Enabled
  Device supports Unified Addressing (UVA):      Yes
  Device PCI Bus ID / PCI location ID:           5 / 0
  Compute Mode:
     < Default (multiple host threads can use ::cudaSetDevice() with device simultaneously) >

deviceQuery, CUDA Driver = CUDART, CUDA Driver Version = 6.5, CUDA Runtime Version = 6.5, NumDevs = 1, Device0 = Tesla K40c
Result = PASS
```

## Installing IPython

### IPython 2.3.1 tarball

Locate the IPython 2.3.1 tarball.  Download it, unpack it, and install it:
```
cd ipython-2.3.1; sudo python setup.py
```

## Installing Facebook FAIR Torch7 Deep Learning Libraries

Follow the [Soumith Chintala's](https://github.com/soumith) excellent instructions here

# Examples

[ TBD ]

## iTorch/ConvNet_On_Cifar_GPU

This is an iTorch script, based entirely on [Soumith Chantala's](https://github.com/soumith) excellent [example](https://github.com/soumith/nextml), presented at the [NextML Workshop](http://www.next.ml/) at Galvanize SOMA in January 2015.  I've made a few changes which demonstrate how to marshal tensors to the GPU memory and how to use the GPU for optimization.

## iTorch/Siamese_On_Pose_GPU

### Download The Sample Data

[ Instructions ]

### Run ITorch Script

[ Instructions ]

# Docker Images

[ Experimental ]
