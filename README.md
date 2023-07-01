# Task 1
本次实验使用CPC（Contrastive Predictive Coding）模型,对比baseline：ResNet-18在CIFAR-100图像分类的性能。

### Run

```
python test.py
``````


# Task 2
本次实验使用CeiT作为 CNN + Transformer 的网络模型
使用 ResNet18 作为CNN对比模型

### Train

需先在`./configs/default.yaml`文件的最后一行指定数据增强模式，可供选择的参数有：normal、cutmix、cutout、mixup. 

默认为normal，即无任何数据增强。

之后在终端运行下一行程序。

```
python train.py -c configs/default.yaml --name train
```

### test

下行程序中的checkpoint可替换成以下四种，分别代表使用四种不同数据增强模式所训练的模型：

- ./output/normal_checkpoint.pyt
- ./output/cutmix_checkpoint.pyt
- ./output/cutout_checkpoint.pyt
- ./output/mixup_checkpoint.pyt

之后在终端运行下一行程序。

```python
python test.py -c configs/defaul.yaml --name test -p checkpoint
```

### Reference

https://github.com/chx7514/Data-Augmentations-for-CIFAR100

https://github.com/193814327/transformer-cifar100

# Task 3

本次实验使用COLMAP + NeRF进行三维重建，需安装COLMAP软件对数据进行预处理，然后使用NeRF模型对物体进行三维重建

由于数据集和COLMAP软件处理后的数据集文件较大，故完整代码+处理前后数据集+结果上传至云盘，github中仅存有必要代码和结果展示

### How to Run

数据集的COLMAP处理详细记录在report中，将COLMAP处理结果文件复制到Nerf项目 data/nerf_llff_data下面的新的plant文件

命令行输入命令

```
python run_nerf.py --config configs/plant.txt 即可开始进行训练
``````

### Result




### Reference

https://colmap.github.io/

https://github.com/yenchenlin/nerf-pytorch


