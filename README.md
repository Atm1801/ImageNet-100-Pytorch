# ImageNet-100 (IN100) Implementation

Implementation of ImageNet-100 dataset for usage

## Quick Start
Generate ImageNet-100 dataset based on [selected class file](https://arxiv.org/pdf/1906.05849.pdf) randomly sampled from ImageNet-1K dataset. Simply run the generate_IN100.py could generate folder of ImageNet-100.

For example, run the following command to generate ImageNet-100 data

arguments:
  - `--source_folder`: specify the ImageNet-1K data folder
  - `--target_folder`: specify the ImageNet-100 data folder
  - `--target_class`: specify the ImageNet-100 txt file with list of classes [default: 'IN100.txt']

```
python generate_IN100.py \
  --source_folder /path/to/ImageNet-1K data
  --target_folder /path/to/ImageNet-100 data
```

## Training ResNets on ImageNet-100
The implementation of training and validation code can be used in main_IN100.py, and run it for the usage.
```
python main_IN100.py --model resnet18 \
  --data_folder /path/to/ImageNet-100 main folder \
  --batch_size 256 \
  --epochs 200 \
  --learning_rate 0.2 \
  --cosine \
```
Note: Please set up the augment: --data_folder as main path to ImageNet-100 in the main_IN.py

Step learning schedule is applied as defult in the implementation (append --cosine to switch to cosine annealing).

## Results
Experiments on ImageNet-100:
| Arch | Batch Size | Epoch | Loss | kNN Accuracy(%) |
|:----:|:---:|:---:|:---:|:---:|
| ResNet18 | 256 | 200 | Cross Entropy |  -  |
| ResNet50 | 256 | 200 | Cross Entropy |  -  |