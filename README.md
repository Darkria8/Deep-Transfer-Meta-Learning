# Cross-Domain Few-Shot Learning (CD-FSL) Benchmark


## Introduction

The Cross-Domain Few-Shot Learning (CD-FSL) challenge benchmark includes data from the CropDiseases [1], EuroSAT [2], ISIC2018 [3-4], and ChestX [5] datasets, which covers plant disease images, satellite images, dermoscopic images of skin lesions, and X-ray images, respectively. The selected datasets reflect real-world use cases for few-shot learning since collecting enough examples from above domains is often difficult, expensive, or in some cases not possible. In addition, they demonstrate the following spectrum of readily quantifiable domain shifts from ImageNet: 1) CropDiseases images are most similar as they include perspective color images of natural elements, but are more specialized than anything available in ImageNet, 2) EuroSAT images are less similar as they have lost perspective distortion, but are still color images of natural scenes, 3) ISIC2018 images are even less similar as they have lost perspective distortion and no longer represent natural scenes, and 4) ChestX images are the most dissimilar as they have lost perspective distortion, all color, and do not represent natural scenes.


## General information

* **No meta-learning in-domain**
* Only ImageNet based models or meta-learning allowed.
* 5-way classification
* n-shot, for varying n per dataset
* 600 randomly selected few-shot 5-way trials up to 50-shot (scripts provided to generate the trials)
* Average accuracy across all trials reported for evaluation.


## Enviroment

Python 3.5.5

Pytorch 0.4.1

h5py 2.9.0


## Model

model based on Transer learning



model based on Meta learning



## Steps



1. Change configuration file `./configs.py` to reflect the correct paths to each dataset. Please see the existing example paths for information on which subfolders these paths should point to.

2. Train base models on miniImageNet

    • *Standard supervised learning on miniImageNet*

    ```bash
        python ./train.py --dataset miniImageNet --model ResNet10  --method baseline --train_aug
    ```

    • *Train meta-learning method (protonet) on miniImageNet*

    ```bash
        python ./train.py --dataset miniImageNet --model ResNet10  --method protonet --n_shot 5 --train_aug
    ```

3. Test

    • *Finetune*

    ```bash
        python finetune.py --model ResNet10 --method baseline  --train_aug --n_shot 5 
    ```
    
    
## References

