[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/activating-more-pixels-in-image-super/image-super-resolution-on-set5-4x-upscaling)](https://paperswithcode.com/sota/image-super-resolution-on-set5-4x-upscaling?p=activating-more-pixels-in-image-super)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/activating-more-pixels-in-image-super/image-super-resolution-on-urban100-4x)](https://paperswithcode.com/sota/image-super-resolution-on-urban100-4x?p=activating-more-pixels-in-image-super)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/activating-more-pixels-in-image-super/image-super-resolution-on-set14-4x-upscaling)](https://paperswithcode.com/sota/image-super-resolution-on-set14-4x-upscaling?p=activating-more-pixels-in-image-super)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/activating-more-pixels-in-image-super/image-super-resolution-on-manga109-4x)](https://paperswithcode.com/sota/image-super-resolution-on-manga109-4x?p=activating-more-pixels-in-image-super)

# SVTSR

### SVTSR: A Lightweight Scattering Vision Transformer for Image Super-Resolution 




## Updates


## Overview

## Citations


## Environment
- [PyTorch >= 1.7](https://pytorch.org/) **(Recommend **NOT** using torch 1.8!!! It would cause abnormal performance.)**
- [BasicSR == 1.3.4.9](https://github.com/XPixelGroup/BasicSR/blob/master/INSTALL.md) 
### Installation
Install Pytorch first.
Then,
```
pip install -r requirements.txt
python setup.py develop
```

## How To Test



Otherwise, 
- Refer to `./options/test` for the configuration file of the model to be tested, and prepare the testing data .  
 
- Then run the following codes (taking `SVTSR_X4net_g_latest.pth` as an example):
```
python hat/test.py -opt options/test/SVTSR_SRx4.yml
```
The testing results will be saved in the `./results` folder.  

- Refer to `./options/test/HAT_SRx4_ImageNet-LR.yml` for **inference** without the ground truth image.

**Note that the tile mode is also provided for limited GPU memory when testing. You can modify the specific settings of the tile mode in your custom testing option by referring to `./options/test/HAT_tile_example.yml`.**

## How To Train
- Refer to `./options/train` for the configuration file of the model to train.
- Preparation of training data can refer to [this page](https://github.com/XPixelGroup/BasicSR/blob/master/docs/DatasetPreparation.md). 
- The training command is like
```
CUDA_VISIBLE_DEVICES=0,1,2,3 python -m torch.distributed.launch --nproc_per_node=4 --master_port=4321 options/train/train_SVTSR_SRx2_from_scratch.yml --launcher pytorch
```
- Note that the default batch size per gpu is 1, which will cost about 5G memory for each GPU.  

The training logs and weights will be saved in the `./experiments` folder.

## Results
The inference results on benchmark datasets are available at
[Google Drive](https://drive.google.com/drive/folders/1-Y_R3tO-AS3pp30krurolGiyMPy6cxo7) or [Baidu Netdisk](https://pan.baidu.com/s/1nlzcBOhTf0AUy9aGY9TUEQ 
) (access code: a51h).


## Contact
If you have any question, please email jiabao18437907605@gmail.com
