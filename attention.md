export MODELSCOPE_CACHE=/home/featurize/work/modelscope/hub
## 按照以下environment来安装
```shell
name: anytext
channels:
  - pytorch
  - nvidia
  - defaults
dependencies:
  - python=3.10.6
  - pip=23.0.1
  - cudatoolkit=11.7
  - numpy=1.23.3
  - cython==0.29.33
  - pip:
      - huggingface-hub==0.25.0
      - Pillow==9.5.0
      - gradio==3.50.0
      - albumentations==0.4.3
      - opencv-python==4.7.0.72
      - imageio==2.9.0
      - imageio-ffmpeg==0.4.2
      - pytorch-lightning==1.5.0
      - omegaconf==2.2.3
      - test-tube==0.7.5
      - streamlit==1.20.0
      - einops==0.4.1
      - transformers==4.30.2
      - webdataset==0.2.5
      - kornia==0.6.7
      - open_clip_torch==2.7.0
      - torchmetrics==0.11.4
      - timm==0.6.7
      - addict==2.4.0
      - yapf==0.32.0
      - safetensors==0.4.0
      - basicsr==1.4.2
      - jieba==0.42.1
      - modelscope==1.10.0
      - tensorflow==2.13.0
      - torch==2.0.1
      - torchvision==0.15.2
      - easydict==1.10
      - xformers==0.0.20
      - subword-nmt==0.3.8
      - sacremoses==0.0.53
      - sentencepiece==0.1.99
      - fsspec
      - diffusers==0.10.2
      - ujson
```
```shell
conda env create --prefix /home/featurize/work/anytext -f environment.yaml
```
## 报错:ImportError: libnccl.so.2: cannot open shared object file: No such file or directory
```shell
sudo apt update && sudo apt upgrade
sudo apt install build-essential dkms
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-keyring_1.0-1_all.deb
sudo dpkg -i cuda-keyring_1.0-1_all.deb
sudo apt-get update
sudo apt install libnccl2 libnccl-dev
ldconfig -p | grep libnccl
export LD_LIBRARY_PATH=/path/to/nccl/lib:$LD_LIBRARY_PATH
```
## 报错:ImportError: Using SOCKS proxy, but the 'socksio' package is not installed. Make sure to install httpx using `pip install httpx[socks]`.
```shell
unset all_proxy && unset ALL_PROXY
```
## 报错：RuntimeError: Failed to import transformers.models.clip.feature_extraction_clip because of the following error (look up to see its traceback):No module named 'tensorflow.python'
重装tensorflow
```shell
pip uninstall tensorflow
pip install tensorflow==2.13.0
```
