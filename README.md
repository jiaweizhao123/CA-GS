<h1 style="text-align:center;">CA-GS: Restoring Occluded Details in 3DGS via Contribution Aware Densification Across Viewpoints</h1>

<center>
    <a href='#'><u>Dongliang Guo</u></a><sup>1,*</sup>
    <a href='#'><u>Jiawei Zhao</u></a><sup>1,*</sup>
    <a href='#'><u>Le Xu</u></a><sup>1</sup>
    <a href='#'><u>Yanfen Wang</u></a><sup>1</sup>
    <a href='#'><u>Yong Tang</u></a><sup>1</sup>
    <a href='#'><u>Feng Wang</u></a><sup>1</sup>
    <a href='#'><u>Wei Liu</u></a><sup>2</sup>
</center>

<center>
    <sup>1</sup>Yan Shan University <sup>2</sup>University of Technology Sydney
    <br>*Indicates Equal Contribution
</center>

<center>
    <a href="#">Paper</a> <b>|</b> <a href="#">arxiv</a> <b>|</b> <a href="#">Project Page</a>
</center>

<img src="images/teaser.png" alt="teaser">
<p>此仓库是"CA-GS_Restoring Occluded Details in 3DGS via Contribution Aware Densification Across Viewpoints"的项目代码</p>
<p>We present a contribution-weighted gradient accumulation method that eliminates blurry artifacts during reconstruction. (a) Real image and initial point cloud visualization. (b) Rendering comparison with 3DGS. Notably, Our method improves
detail recovery in occluded regions. (c) Point cloud and memory comparison with 3DGS (both enlarged with 20% Gaussian blur
for contrast). (d) Gaussians may experience occlusion issues across different viewpoints, hindering their normal growth and
differentiation. (e) Our method produces more Gaussians in local regions, satisfying the need for detailed representation.</p>

<h2>安装</h2>

```
git clone https://github.com/jiaweizhao123/CA-GS.git --recursive
# You can use the environment of 3dgs
# Or create a new environment as follow+
conda create -n ca_gs python=3.7
pip install -r requirements.txt

# The following template must be reissued because this part of the template has been modified
cd submodules
pip install ./diff-gaussianirasterzation
pip install ./simple-knn
```

<h2>数据集</h2>
<h3>MipNeRF 360</h3>
You can download the <a href="https://jonbarron.info/mipnerf360/"><u>MipNeRF 360</u></a> dataset, which contains 9 scenes including indoor and outdoor ones. The pictures of each scene have 4 different resolutions.
<h3>Tanks and Temples</h3>
You can directly download the <a href="#"><u>Tanks and Temples</u></a> dataset processed by us, or you can download the pictures of various scenes through the <a href="#"><u>official website of Tanks and Temples</u></a>, and then obtain the corresponding configuration files such as camera poses and initial sparse point clouds through colmap processing.
<h3>Deep Blending</h3>
Download the <a href='#'><u>Deep Blending</u></a> dataset we use.
<h3>自定义数据集</h3>
You can also process your own images through colmap to generate data that conforms to the 3DGS training format.
<h2>训练及评估</h2>

```
# Dataset training
python train.py -s <dataset path> -m <output path> --eval

# Rendering images
python render.py -m <output path>

# Calculate the quality of the reconstruction result
python metrics.py -m <output path>

# Use this script to evaluate the reconstruction quality of the dataset we use
python full_eval.py -m360 <mipnerf360 folder> -tat <tanks and temples folder> -db <deep blending folder>

```

<h2>引用</h2>
If you find our code or paper useful, please consider citing:

```

```