# Image Classification Pytorch

## Dataset
* CIFAR-10

## Version
* Python: 3.6.9
* PyTorch: 1.7.1
* PyTorch-Lightning: 1.1.6


## Results(Accuracy)

|Models|CIFAR-10|CIFAR-100|#Params|
|:--:|:--:|:--:|:--:|
|[AllCNNC](https://arxiv.org/abs/1412.6806)|93.640|72.040|1.4M|
|[VGG16](https://arxiv.org/abs/1409.1556)|-|-|-|
|[ResNet18](https://arxiv.org/abs/1512.03385)|94.465|74.465|11.2M|
|[PreAct18](https://arxiv.org/abs/1603.05027)|94.575|75.415|11.2M|
|[PreAct34](https://arxiv.org/abs/1603.05027)|95.010|75.715|21.3M|
|[PreAct50](https://arxiv.org/abs/1603.05027)|94.970|76.685|23.5M|


## Hyperparameters
|Params|Values|
|:--|:--:|
|Epochs| 200|
|Batch Size| 128|
|Learning Rate| 0.1|
|LR Milestones| [100, 150]|
|LR Decay Rate| 0.1|
|Weight Decay| 1e-4|

* For the fair comparison, all experiments are done under the same experimental settings.

## Future Work
* Spatial dimensions of tensors right before GAP should be 4x4 rather than 2x2.
* No bias term used for Squeeze-and-Excitation Module.
* Use dropout right after activation.(in WRN, at least.)
    * If apply dropout right after conv, the performance degrades by 1-2% in CIFAR-100

## References
* All-CNN-C(+BN)[[Springenberg, J.(ICLRW'15)]](https://arxiv.org/abs/1412.6806)
* VGG16(+BN)[Simonyan, K.(ICLR'15)](https://arxiv.org/abs/1409.1556)
* ResNet[[He, K.(CVPR'16)]](https://arxiv.org/abs/1512.03385)
* PreAct-ResNet[[He, K.(ECCV'16)]](https://arxiv.org/abs/1603.05027)
* WideResNet[[Zagoruyko, S.(BMVC'16)]](https://arxiv.org/abs/1605.07146)
* ResNeXt[[Xie, S.(CVPR'17)]](https://arxiv.org/abs/1611.05431)
* SENet[[Hu, J.(CVPR'18)]](https://arxiv.org/abs/1709.01507)
* MobileNetV1[[Howard, A.(2017)]](https://arxiv.org/abs/1704.04861)
* MobileNetV2[[Sandler, M.(CVPR'18)]](https://arxiv.org/abs/1801.04381)
* MobileNetV3[[Howard, A.(ICCV'19)]](https://arxiv.org/abs/1905.02244)


