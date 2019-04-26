# EdgeMap345C_Dataset

![examples](https://github.com/PengBoXiangShang/EdgeMap345C_Dataset/blob/master/illustrations/edges.png)

## Introduction
This is a edge-map dataset including **290281** edge-maps
corresponding to **345** object categories, termed as **Edge-Map-345C**, established by [Peng Xu](www.pengxu.net). In particular, these 345 categories are corresponding to the 345 free-hand sketch categories of [Google QuickDraw dataset](https://github.com/googlecreativelab/quickdraw-dataset). Please see [categories.txt](https://github.com/PengBoXiangShang/EdgeMap345C_Dataset/blob/master/categories.txt) for details.

Some edge-mage samples are shown in above figure. This repository provides zip format packages in Google Drive and Baiduyun Disk, and will be continuously updated! <font color=red> Our paper associated with this dataset will be released soon. </font> If this dataset can be used in your research, please cite our paper.

<font color=red>For sketch-specific study, this edge-map dataset can be used to pretrain the networks to solve the training data scarcity issue.</font>

## Collection Instructions
The data collection can be divided into two steps: photo collection and edge-map extraction.
### Photo Collection
There are 157 (out of 345) classes of QuickDraw having at least one corresponding class in [ImageNet](http://image-net.org/challenges/LSVRC/2012/). For each of these 157 categories, I manually choose one most similar category from ImageNet. Since many of ImageNet are multi-object images, we crop photos from the annotated bounding box areas, thus only photos with bounding box annotations provided can be used. This cropping operation can alleviate the domain gap between edge-map and sketch. For the remaining 188 categories, we program crawler to download images from [Google Images](https://images.google.com).
### Edge-Map Extraction
After photo collection, we use [Edge Boxes toolbox](https://github.com/pdollar/edges) to extract edge-maps from our collected photos. Each edgemap has been located in the center and takes up about 90% area of the photo. We resized all the edge-maps as 3×224×224. We recruit five volunteers to manually remove the messy edge-maps that can not be recognize by human. Finally, we obtain 290, 281 edge-maps across 345 categories (averagely 841 per category).

These 290, 281 edge-maps were randomly divided into training set (263, 655) and validation set (26, 626).

The main preprocessing scripts will be released in [./code/](https://github.com/PengBoXiangShang/EdgeMap345C_Dataset/tree/master/code).

## Classification Results on Edge-Map-345C
I trained some state-of-the-art CNN
networks on Edge-Map-345C training set, and classification results on Edge-Map-345C validation set are reported in following table.

|Model | Validation Accuracy|
|-----|-----|
|MobileNet V1 | 0.6108|
|MobileNet V2 | 0.5971|
|ResNet-18 | 0.5943|
|ResNet-34 | 0.5931|
|ResNet-50 | 0.5896|
|ResNet-152 | 0.5829|
|DenseNet-121 | 0.6153|
|DenseNet-161 | 0.5518|
|DenseNet-169 | 0.5177|
|DenseNet-201 | 0.5514|
|GoogLeNet Inception V3 | 0.6237|
|VGG-11 | 0.6132|

## Downloading Links
Please download them via following links, respectively.

Training Set (4.9GB): [Baiduyun Disk part 1](https://pan.baidu.com/s/10WLUyvDgMKeHYYh2cBTveA)， [Baiduyun Disk part 2](); [Google Drive]() (coming soon).

Validation Set (490MB): [Baiduyun Disk](https://pan.baidu.com/s/1MNb0oTrFkcnw-GD3O2Ys1Q：), [Google Drive]() (coming soon).

<font color=green>If you want to download from Baiduyun, Please send email to Peng Xu to get the fetch code.</font>

If these links can not work well, please feel free to contact Peng Xu (peng.xu [AT] bupt.edu.cn).



