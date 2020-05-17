# Cross-Domain Few-Shot Learning 

## Introduction




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

