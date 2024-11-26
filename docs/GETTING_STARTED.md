# Getting Started

All experiments are implemented on a single GPU. Below are the examples for training and testing various models of **Vim** and **DeiT**. You can use the default parameters we provide, or set the parameters yourself, or modify various parameters in the specific configuration files.

## Clone this repository
```
git clone https://github.com/zhenglab/MCAD-MM.git
```
## Run Vim
```
cd ~/models/vim
```
### Download the pre-trained models
**Vim-tiny**: You can download the **Vim-tiny** pre-trained model provided by the official source from [this link](https://huggingface.co/hustvl/Vim-tiny-midclstok/resolve/main/vim_t_midclstok_76p1acc.pth?download=true) and place it in any location.

### Training
```shell
python main.py --data-path ${your_DATA_PATH} --finetune ${your_PRETRAIN_PATH} --output_dir ${your_RESULT_PATH} --subset ${1705/1706/1705_1706} --split ${1/2/3} --channel ${1/2/3/4/5/6} --adjust-scale --model vim_tiny_patch16_224_bimambav2_final_pool_mean_abs_pos_embed_with_midclstok_div2 --input-size 224 --batch-size 16 --num_workers 4 --epochs 30 --data-set DCLDE --lr 1e-6 --min-lr 1e-8 --warmup-lr 1e-8 --drop-path 0.0 --weight-decay 0.01 --unscale-lr --no_amp
```
### Testing
```shell
python main.py --eval --test-five-crop --data-path ${your_DATA_PATH} --resume ${your_RESULT_PATH}/checkpoint.pth --output_dir ${your_RESULT_PATH} --subset ${1705/1706/1705_1706} --split ${1/2/3} --channel ${1/2/3/4/5/6} --model vim_tiny_patch16_224_bimambav2_final_pool_mean_abs_pos_embed_with_midclstok_div2 --input-size 224 --batch-size 16 --num_workers 4 --data-set DCLDE --no_amp
```


## Run DeiT
```
cd ~/models/deit
```
### Download the pre-trained models
**DeiT-tiny**: You can download the **DeiT-tiny** pre-trained model provided by the official source from [this link](https://dl.fbaipublicfiles.com/deit/deit_tiny_patch16_224-a1311bcf.pth) and place it in any location.

### Training
```shell
python main.py --data-path ${your_DATA_PATH} --finetune ${your_PRETRAIN_PATH} --output_dir ${your_RESULT_PATH} --subset ${1705/1706/1705_1706} --split ${1/2/3} --channel ${1/2/3/4/5/6} --adjust-scale --model deit_tiny_patch16_224 --input-size 224 --batch-size 16 --num_workers 4 --epochs 30 --data-set DCLDE --lr 1e-6 --min-lr 1e-8 --warmup-lr 1e-8 --drop-path 0.0 --weight-decay 0.01 --unscale-lr
```

### Testing
```shell
python main.py --eval --test-five-crop --data-path ${your_DATA_PATH} --resume ${your_RESULT_PATH}/checkpoint.pth --output_dir ${your_RESULT_PATH} --subset ${1705/1706/1705_1706} --split ${1/2/3} --channel ${1/2/3/4/5/6} --model deit_tiny_patch16_224 --input-size 224 --batch-size 16 --num_workers 4 --data-set DCLDE
```