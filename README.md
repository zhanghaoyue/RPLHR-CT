# RPLHR-CT Dataset and Transformer Baseline for Volumetric Super-Resolution from CT Scans (MICCAI 2022)
[Pengxin Yu](https://github.com/smilenaxx/), [Haoyue Zhang](https://github.com/zhanghaoyue), 
Han Kang, Wen Tang, Corey W. Arnold, Rongguo Zhang

[![paper](https://img.shields.io/badge/arXiv-Paper-<COLOR>.svg)](https://arxiv.org/pdf/2206.06253.pdf)
[![paper](https://img.shields.io/badge/MICCAI-Paper-green)](https://link.springer.com/chapter/10.1007/978-3-031-16446-0_33)

## Abstract
>In clinical practice, anisotropic volumetric medical images with low through-plane resolution are commonly used due to short acquisition time and lower storage cost. Nevertheless, the coarse resolution may lead to difficulties in medical diagnosis by either physicians or computer-aided diagnosis algorithms. Deep learning-based volumetric super-resolution (SR) methods are feasible ways to improve resolution, with convolutional neural networks (CNN) at their core. Despite recent progress, these methods are limited by inherent properties of convolution operators, which ignore content relevance and cannot effectively model long-range dependencies. In addition, most of the existing methods use pseudo-paired volumes for training and evaluation, where pseudo low-resolution (LR) volumes are generated by a simple degradation of their high-resolution (HR) counterparts. However, the domain gap between pseudo- and real-LR volumes leads to the poor performance of these methods in practice. 
In this paper, we build the first public real-paired dataset RPLHR-CT as a benchmark for volumetric SR, and provide baseline results by re-implementing four state-of-the-art CNN-based methods. Considering the inherent shortcoming of CNN, we also propose a transformer volumetric super-resolution network (TVSRN) based on attention mechanisms, dispensing with convolutions entirely. This is the first research to use a pure transformer for CT volumetric SR. The experimental results show that TVSRN significantly outperforms all baselines on both PSNR and SSIM. Moreover, the TVSRN method achieves a better trade-off between the image quality, the number of parameters, and the running time.

## Network Architecture
![截屏2022-09-19 下午3 37 10](https://user-images.githubusercontent.com/23478954/190970275-f7b153d2-de80-4c13-abb0-6c9526d1ae10.png)

## Visual Comparison Results
![截屏2022-09-19 下午3 38 30](https://user-images.githubusercontent.com/23478954/190970495-f94ccaea-b7e1-47b3-88d4-eadafe11ae4c.png)

## Code
**Model train**
```
python train.py train --path_key SRM --gpu_idx 0 --net_idx TVSRN
```
**Model validation**
```
python val.py val --path_key SRM --gpu_idx 0 --net_idx TVSRN
```
**Model test**
```
python test.py test --path_key SRM --gpu_idx 0 --net_idx TVSRN
```

## Data
We open source a dataset **RPLHR-CT**, which contains 250 cases of data (100 cases for training, 50 cases for validation, 100 cases for testing). 
We build a tiny dataset with 20/10/20 (train/val/test) cases to [baidu cloud disk](https://pan.baidu.com/s/1QXbcFuWAHOiY3FijEcsowQ?pwd=ut7p). 
For data usage rights reasons, should you required the complete dataset, please contact **ypengxin@infervision.com**.

## Citation
If you use RPLHR-CT, please consider citing:
```
    @inproceedings{yu2022rplhr,
      title={RPLHR-CT Dataset and Transformer Baseline for Volumetric Super-Resolution from CT Scans},
      author={Yu, Pengxin and Zhang, Haoyue and Kang, Han and Tang, Wen and Arnold, Corey W and Zhang, Rongguo},
      booktitle={International Conference on Medical Image Computing and Computer-Assisted Intervention},
      pages={344--353},
      year={2022},
      organization={Springer}
    }
```

**Acknowledgment**: This code is based on the [Swin Transformer](https://github.com/microsoft/Swin-Transformer).

## Our Related Works
- Stereo-Correlation and Noise-Distribution Aware ResVoxGAN for Dense Slices Reconstruction and Noise Reduction in Thick Low-Dose CT, MICCAI 2019. [paper](https://link.springer.com/chapter/10.1007/978-3-030-32226-7_37)
- SAINT-Spatially Aware Interpolation NeTwork for Medical Slice Synthesis, CVPR 2020. [paper](http://openaccess.thecvf.com/content_CVPR_2020/html/Peng_SAINT_Spatially_Aware_Interpolation_NeTwork_for_Medical_Slice_Synthesis_CVPR_2020_paper.html)
- Multi-stream Progressive Up-Sampling Network for Dense CT Image Reconstruction, MICCAI 2020. [paper](https://link.springer.com/chapter/10.1007/978-3-030-59725-2_50)
- DA-VSR: Domain Adaptable Volumetric Super-Resolution for Medical Images, MICCAI 2021. [paper](https://link.springer.com/chapter/10.1007/978-3-030-87231-1_8)





