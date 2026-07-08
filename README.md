## Method Overview 
- Improving Neural Volume Rendering via Learning View-Dependent Integral Approximation   
IEEE Transactions on Visualization and Computer Graphics[[Paper]](https://ieeexplore.ieee.org/abstract/document/10938376)  
TL;DR: Improve geometric fidelity and consistency in novel view synthesis by modeling integrals with anisotropic representations  
- TayloRF: Approximate Volume Integral Using Explicit Polynomial Representations[[Paper]](https://arxiv.org/abs/xxxx)  
TL;DR: Propose a polynomial-based implicit 3D representation that explicitly models intra-interval variations in volume rendering  

## Visual Blender Result
<p align="center">
  <img src="assets/rip_materials_rgb.gif" width="45%">
  <img src="assets/rip_materials_depth.gif" width="45%">
</p>

## ⚙️ Setup
Our example code is based on [Nerfacc](https://github.com/nerfstudio-project/nerfacc).
### Clone this repository.
```text
git clone --recursive https://github.com/taylor2nerf/taylor-nerf.git
```
### Install Environment via Anaconda (Recommended)
```text
conda create -n nerfacc python=3.10
conda activate nerfacc
pip install -r requirements.txt
```
### Compilation tiny-cuda-nn
```text
pip install git+https://github.com/NVlabs/tiny-cuda-nn/#subdirectory=bindings/torch
```
| Windows & Linux | cu113 | cu115 | cu116 | cu117 | cu118 |
|-----------------|-------|-------|-------|-------|-------|
| torch 1.11.0    | ✅    | ✅    |       |       |       |
| torch 1.12.0    | ✅    |       | ✅    |       |       |
| torch 1.13.0    |       |       | ✅    | ✅    |       |
| torch 2.0.0     |       |       |       | ✅    | ✅    |


### 📦 Dataset
We mainly test our method on Synthetic Blender, and Mip-360 v2 dataset. Put them under the data folder:
```text
data
└── nerf_synthetic
    └── hotdog
    └── lego
```

### 🏃 Training
We provide the script to test our code on each scene of NeRF Synthetic datasets. Just run:
```bash
bash scripts/train_ns_all.sh
```

## TODO
The example of unbounded scene based on Zip-NeRF  

