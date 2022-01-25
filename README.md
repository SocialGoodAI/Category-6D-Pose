# CRNet_IROS

### [Paper](https://arxiv.org/abs/2108.08755) | [Webpage](https://wangjiaze.cn/projects/6DPoseEstimation.html)

- This is the official implementation of the paper: **Category-Level 6D Object Pose Estimation via Cascaded Relation and Recurrent Reconstruction Networks** (IROS 2021).

<div align=center>

<img src="https://github.com/JeremyWANGJZ/Category-6D-Pose/blob/main/img/intro.png" height="400" alt="image"/>

</div>


## Quick Start

### (1) Install Packages
**Requires:**

* Python ≥ 3.6
* Pytorch ≥ 1.0
* CUDA ≥ 9.0

**Compile nn_distance:**
```
ROOT=/path/to/object-deformnet
cd $ROOT/lib/nn_distance
python setup.py install --user
```

### (2) Dataset
Please download the Dataset following [SPD](https://github.com/mentian/object-deformnet/).

Unzip and organize these files in $ROOT as follows:
```
data
├── CAMERA
│   ├── train
│   └── val
├── Real
│   ├── train
│   └── test
├── gts
│   ├── val
│   └── real_test
└── obj_models
    ├── train
    ├── val
    ├── real_train
    └── real_test

results
├── mrcnn_results
│   ├── real_test
│   └── val
└── nocs_results
    ├── real_test
    └── test
```
### (3) Train and Evaluate
```
# train: python train.py

# test: python evaluate.py
```


## Performance
Please download our models $ROOT/models.

**Camera25:**
|    Camera25    | 3D50 | 3D75 | 5°2cm | 5°5cm | 10°2cm | 10°5cm |
|:--------------:|:----:|:----:|:-----:|:-----:|:------:|:------:|
|    Our Paper   | **93.8** | 88.0 |  **72.0** |  76.4 |  81.0  |  87.7  |
| Released Model | 93.7 | **88.1** |  71.2 |  **76.5** |  **81.1**  |  **88.4**  |

**Real275:**
|     Real275    | 3D50 | 3D75 | 5°2cm | 5°5cm | 10°2cm | 10°5cm |
|:--------------:|:----:|:----:|:-----:|:-----:|:------:|:------:|
|    Our Paper   | **79.3** | 55.9 |  27.8 |  34.3 |  47.2  |  60.8  |
| Released Model | 78.9 | **57.8** |  **31.5** |  **34.9** | **51.5**  |  **62.8**  |

## Citation
If you find our work helpful, please consider citing:
```
@inproceedings{wang2021category,
  title={Category-level 6d object pose estimation via cascaded relation and recurrent reconstruction networks},
  author={Wang, Jiaze and Chen, Kai and Dou, Qi},
  booktitle={2021 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)},
  pages={4807--4814},
  year={2021},
  organization={IEEE}
}
```
You can also refer to our last work [SGPA](https://openaccess.thecvf.com/content/ICCV2021/html/Chen_SGPA_Structure-Guided_Prior_Adaptation_for_Category-Level_6D_Object_Pose_Estimation_ICCV_2021_paper.html) on ICCV2021：
```
@inproceedings{chen2021sgpa,
  title={Sgpa: Structure-guided prior adaptation for category-level 6d object pose estimation},
  author={Chen, Kai and Dou, Qi},
  booktitle={Proceedings of the IEEE/CVF International Conference on Computer Vision},
  pages={2773--2782},
  year={2021}
}
```

## Contact Us
WANG Jiaze: jzwang.cuhk@gmail.com | [Homepage](https://wangjiaze.cn/)

## Acknowledgment
Our implementation leverages the code from [SPD](https://github.com/mentian/object-deformnet/), [NOCS](https://github.com/hughw19/NOCS_CVPR2019), [3PU](https://github.com/yifita/3PU_pytorch) and [DCP](https://arxiv.org/abs/1905.03304/).
