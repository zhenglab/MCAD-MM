# Preparation


## Requirements

* Linux (Windows is not officially supported)
* Python 3.10+
* PyTorch 2.1.1 or higher
* CUDA 11.8 or higher

## Installation

**We strongly recommend following the guidance provided by the official [Vision Mamba (Vim)](https://github.com/hustvl/Vim/tree/main) repository to install the environment!**

<details open>
<summary>Installation details</summary>

### 1. Clone the Vim repository
`git clone https://github.com/hustvl/Vim.git`

### 2. Create a conda environment with Python version 3.10.13.
`conda create -n [your_env_name] python=3.10.13`

`conda activate [your_env_name]`

### 3. Install torch 2.1.1 + cu118.
`pip install torch==2.1.1 torchvision==0.16.1 torchaudio==2.1.1 --index-url https://download.pytorch.org/whl/cu118`

### 4. Install the requirements for Vim.
`pip install -r vim/vim_requirements.txt`

### 5. Install the two essential packages: casual_conv1d and mamba.
`pip install -e causal_conv1d>=1.1.0`

`pip install -e mamba-1p1p1`

</details>

<br></br>
After completing the installation of the Vim environment, you can run various models of this project within this environment.

## Dataset Preparation

- Download the DCLDE dataset via the [Baidu Netdisk](https://pan.baidu.com/s/1jKAl2qK_tYE77muw7c5lBw?pwd=IMTS) links.

- Unzip and copy the dataset files directory as following shows:
```
DCLDE
├── 1705_FLAC
│   ├── CHANNEL_1
│   ├── CHANNEL_2
│   ├── CHANNEL_3
│   ├── CHANNEL_4
│   ├── CHANNEL_5
│   └── CHANNEL_6
├── 1706_FLAC
│   ├── CHANNEL_1
│   ├── CHANNEL_2
│   ├── CHANNEL_3
│   ├── CHANNEL_4
│   ├── CHANNEL_5
│   └── CHANNEL_6
└── annotations
    ├── annotations-1705
    │   ├── split-1
    │   ├── split-2
    │   └── split-3
    ├── annotations-1705_1706
    │   ├── split-1
    │   ├── split-2
    │   └── split-3
    └── annotations-1706
        ├── split-1
        ├── split-2
        └── split-3
```