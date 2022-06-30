# SRCN3D: Sparse R-CNN 3D Surround-View Cameras 3D Object Detection and Tracking for Autonomous Driving

This repo is the official implementations of SRCN3D (https://arxiv.org/abs/2110.06923). Our implementation is based on MMdetection3D.  

<!-- <div align="center">
  <img src="figs/overview.png"/>
</div><br/> -->

### Preparation

Please install the latest version of mmdet3d (https://github.com/open-mmlab/mmdetection3d) according to Open-MMLab guidelines. Give a soft link of mmdetection3d with 

* Reference Environments  
  Linux(Ubuntu18.04LTS), Python==3.7.13, CUDA == 11.3, pytorch == 1.10.2,torchvision == 0.11.3 ,mmdet3d == 0.17.2   

`ln -s /path/to/mmdetection3d {/path/to/SRCN3D}/`

### Data
1.  Follow the mmdet3d to process the nuScenes dataset (https://github.com/open-mmlab/mmdetection3d/blob/master/docs/en/data_preparation.md).  

### Train
1. Downloads the [pretrained backbone weights] from DETR3D repository (https://drive.google.com/drive/folders/1h5bDg7Oh9hKvkFL-dRhu5-ahrEp2lRNN?usp=sharing) to ckpts/ 

2. For example, to train a basic version of SRCN3D on 2 GPUs, please use

`bash tools/dist_train.sh projects/configs/srcn3d/srcn3d_res101_roi7_nusc.py 2`

### Pretrained models
1. Download the weights accordingly.  

|  Backbone   | mAP | NDS | Download |
| :---------: | :----: |:----: | :------: |
|[SRCN3D, ResNet101 w/ DCN](./projects/configs/srcn3d/srcn3d_res101_roi7_nusc.py)|33.7|42.8|[model](https://drive.google.com/uc?export=download&id=1z5Vc7Apfu0TNOMkPZTF1prj4bK5dm3CH) &#124; [log](https://drive.google.com/uc?export=download&id=19da3VhaTYTjFOLxKumfWqCh20jXOl0iQ)|


2. for a validation and test submission, use  
`tools/dist_test.sh path/to/config.py /path/to/ckpt 1 --eval=bbox`

### Bibtex 
If you find this repo useful for your research, please consider citing the papers

```
@inproceedings{
   SRCN3D,
   title={SRCN3D: Sparse R-CNN 3D Surround-View Cameras 3D Object Detection and Tracking for Autonomous Driving},
   author={},
   journal={arXiv preprint arXiv:2206.01256},
   year={2022}
}
```
# News
- [2022/6/27]: We release an initial version of SRCN3D. 
</br>

### Acknowledgement
Thanks to prior excellent open source projects:
- [DETR3D](https://github.com/WangYueFt/detr3d) 
- [mmdet3d](https://github.com/open-mmlab/mmdetection3d)

### Contact
The repository is still in an early stage, if you have any questions, feel free to open an issue or contact us at syn21@mails.tsinghua.edu.cn.
