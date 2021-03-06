# Dual-Path-Transformer-Network-PyTorch
Unofficial implementation of Dual-Path Transformer Network (DPTNet) for speech separation (Interspeech 2020)

## Plan


- [x] Data pre-processing
- [x] Training
- [x] Inference
- [x] Separate

## Data pre-processing


-- in-dir: It means your WSJ2mix dataset directory. (It has tr/cv/tt folders)

-- out-dir: It saves json files(file information) (recommand not to change)


```bash
$ python preprocess.py --in-dir /data/min --out-dir data --sample-rate 8000
```

## Training

```bash
$ python train.py
```


If you change --out-dir option, you have to set --train_dir '{your_directory}/tr' --valid_dir '{your_directory}/cv' 


```bash
$ python train.py --train_dir 'data/tr' --valid_dir 'data/cv'
```

## Inference


```bash
$ python evaluate.py --model_path 'exp/temp/temp_best.pth.tar'
```


If you change --out-dir option, you have to set --data_dir '{your_directory}/tt'


```bash
$ python evaluate.py --data_dir 'data/tt' --model_path 'exp/temp/temp_best.pth.tar'
```

## Separate

```bash
$ python separate.py --model_path 'exp/temp/temp_best.pth.tar'
```


If you change --out-dir option, you have to set --mix_json '{your_directory}/tt/mix.json'


```bash
$ python evaluate.py --mix_json 'data/tt/mix.json' --model_path 'exp/temp/temp_best.pth.tar'
```



## Result


I achive SI-SNRi **19.84dB** when L=4 (encoder kernel length)

You can check the separated audio samples in the result directory.


## Reference


https://github.com/kaituoxu/Conv-TasNet

https://github.com/ujscjj/DPTNet
