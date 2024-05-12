# Image Classification Pytorch

## Dataset
* CIFAR-10

## Version
* Python: 3.6.9
* PyTorch: 1.7.1
* PyTorch-Lightning: 1.1.6

## Summary on ViT Optimizations
1. Architecture Adjustment: The sequence of F.gelu() followed by nn.Dropout() was adjusted. Reversing this order led to gradients becoming zero, hindering the learning process.
2. Performance on CIFAR-10: For a model with N_LAYERS = 6, HIDDEN_SIZE = 384, and N_HEADS = 6, it was found that using a PATCH_SIZE = 8 and even more so with PATCH_SIZE = 4 led to performance improvements compared to using PATCH_SIZE = 16.
3. Comparison on CIFAR-10: Smaller-sized models compared to the standard ViT-Base model performed better on CIFAR-10.


## Results(Accuracy)

|Models|CIFAR-10|#Params|
|:--:|:--:|:--:|
|[AllCNNC](https://arxiv.org/abs/1412.6806)|93.640|1.4M|
|[ResNet](https://arxiv.org/abs/1512.03385)|94.465|4.47M|
|[ViT](https://arxiv.org/abs/2010.11929)|86.400|--|


## Hyperparameters for Proposed ViT

* DROP_PROB = 0.1
* N_LAYERS = 6
* HIDDEN_SIZE = 384
* MLP_SIZE = 384
* N_HEADS = 12
* PATCH_SIZE = 4
* BASE_LR = 1e-3
* BETA1 = 0.9
* BETA2 = 0.999
* WEIGHT_DECAY = 5e-5
* WARMUP_EPOCHS = 5
* SMOOTHING = 0.1
* CUTMIX = False
* CUTOUT = False
* HIDE_AND_SEEK = False
* BATCH_SIZE = 2048
* N_EPOCHS = 300

## Notes
* Training notebooks show development in v100 GPU due to its faster efficiency compared to the consumer friendly RTX Models.
* To avoid fork errors, please define `num_workers=0` in pytorch dataloaders.
* SOTA Models were considered for pruning but ResNet architecture was chosen for ease of deployment.

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


