# Cross-Domain Few-Shot Learning 


## Enviroment

Python 3.5.5

Pytorch 0.4.1

h5py 2.9.0


## Model

ResNet10： https://drive.google.com/file/d/1Nk60qqkYThXtE4phBtg2TGfxbe91Rm9p/view?usp=sharing, 

ResNet12：https://drive.google.com/file/d/1VbpSb94HnATihRkPePx-zPOId_1CJpoT/view?usp=sharing,

ResNet18：https://drive.google.com/file/d/1lA6gt47fm4kUCGU2QoE5PeQRnLweHpOM/view?usp=sharing


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
    Framework: https://github.com/IBM/cdfsl-benchmark
    Backbone: https://github.com/wyharveychen/CloserLookFewShot
