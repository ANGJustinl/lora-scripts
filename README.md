<div align="center">

<img src="https://github.com/Akegarasu/lora-scripts/assets/36563862/3b177f4a-d92a-4da4-85c8-a0d163061a40" width="200" height="200" alt="SD-Trainer" style="border-radius: 25px">

# SD-Trainer

_✨ Enjoy Stable Diffusion Train！ ✨_

</div>

<p align="center">
  <a href="https://github.com/Akegarasu/lora-scripts" style="margin: 2px;">
    <img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/Akegarasu/lora-scripts">
  </a>
  <a href="https://github.com/Akegarasu/lora-scripts" style="margin: 2px;">
    <img alt="GitHub forks" src="https://img.shields.io/github/forks/Akegarasu/lora-scripts">
  </a>
  <a href="https://raw.githubusercontent.com/Akegarasu/lora-scripts/master/LICENSE" style="margin: 2px;">
    <img src="https://img.shields.io/github/license/Akegarasu/lora-scripts" alt="license">
  </a>
  <a href="https://github.com/Akegarasu/lora-scripts/releases" style="margin: 2px;">
    <img src="https://img.shields.io/github/v/release/Akegarasu/lora-scripts?color=blueviolet&include_prereleases" alt="release">
  </a>
</p>

<p align="center">
  <a href="https://github.com/Akegarasu/lora-scripts/releases">Download</a>
  ·
  <a href="https://github.com/Akegarasu/lora-scripts/blob/main/README.md">Documents</a>
  ·
  <a href="https://github.com/Akegarasu/lora-scripts/blob/main/README-zh.md">中文README</a>
</p>

# 昂-修正v0.1 - casdao 分支

## https://console.casdao.com:9001/#/s-login?refer=1413a7dfa0f77264fe6549b42d078f21dee09629188af2ae357b67eab0728c38
#### 与原版不同特性

* 适配autodl自带 Tenserboard, 请打开 容器实例 页面的 tenserboard 查看
* 配置了clash-for-linux, 以便自行进行学术加速
* 预装 git-lfs 并启用
* 可自行修改 ´lora-scripts/sdxl_train_util.py´ 中clip模型路径, 规避网络错误

> 20行 TOKENIZER1_PATH = "openai/clip-vit-large-patch14" # 将这里换成你下好的clip路径 [https://ai.gitee.com/hf-models/openai/clip-vit-large-patch14](https://ai.gitee.com/hf-models/openai/clip-vit-large-patch14)

> 21行 TOKENIZER2_PATH = "laion/CLIP-ViT-bigG-14-laion2B-39B-b160k" # [https://ai.gitee.com/hf-models/laion/CLIP-ViT-bigG-14-laion2B-39B-b160k/blob/main/README.md](https://ai.gitee.com/hf-models/laion/CLIP-ViT-bigG-14-laion2B-39B-b160k/blob/main/README.md)

#### 沿用的原版特性

* 全新：训练界面正式更新，使用 bash run_gui.sh 运行。
* 内置 SDXL 模型，以及修复的 VAE。训练时如果遇到报错请填写覆盖 VAE 的参数，路径 `./sd-models/vae/sdxl_vae.safetensors`
* 升级至 SD-Trainer v1.8.3
* Tag 编辑器

# 镜像使用


### 1.推荐：使用GUI训练

#### https://www.bilibili.com/read/cv24050162/

### 2.旧版训练 LoRA

打开镜像后 应已经处于 lora-scripts 项目目录。无需安装任何依赖，直接打开
train.sh 进行编辑参数，上传图片至 train 文件夹内。请注意图片文件夹的命名方式。准备好参数和数据后可以开始训练。
打开终端，运行 bash train.sh 即可开始训练。

注意
本镜像所使用的 xformers 基于 sm86 架构编译，本身我是在北京区的3090显卡上制作的这个镜像，推荐你也直接使用3090显卡。

也可以尝试使用这些显卡：Tesla GA10x , RTX Ampere – RTX 3080, GA102 – RTX 3090, RTX A6000, RTX A40

其他显卡不做正常运行保障。如果你用其他显卡，请自行重新安装xformers。

训练数据监控
默认输出日志到 /root/tf-logs 文件夹
