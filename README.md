# NFNet Pytorch Implementation

All credits go to the authors of the [original paper](https://arxiv.org/abs/2102.06171): High-Performance Large-Scale Image Recognition Without Normalization. This repo is inspired by their JAX implementation in the [official repository](https://github.com/deepmind/deepmind-research/blob/master/nfnets/). Visit their repo for citing.

## Get started
After cloning this repo enter
```
git clone https://github.com/benjs/nfnets_pytorch.git
pip3 install -r requirements.txt
```
Go to the [config file](default_config.yaml) and enter the path to your ImageNet directory (downloadable after asking for access from [image-net.org](http://www.image-net.org/challenges/LSVRC/2012/downloads.php#images)).
The directory needs to contain the unpacked ImageNet archives and the dev_kit.tar file.

Start normal training with
```
python3 train.py --config default_config.yaml
```

Start training with pretrained weights through
```
python3 train.py --config default_config.yaml --pretrained pretrained/F0_haiku.npz
```


## Development status

- [x] NFNet Models
  - [x] F0-F7
  - [x] Scaled weight standardization
  - [x] Squeeze and excite
  - [x] Stochastic depth
  - [ ] FP16 activations
- [x] SGD with unit adaptive gradient clipping (SGD-AGC)
  - [x] Exclude certain layers from weight-decay, clipping
  - [ ] FP16 gradients
  - [ ] Label smoothing loss from [Szegedy et al.](https://arxiv.org/abs/1512.00567)
- [x] Training on ImageNet
- [x] Model overfits on small dataset
- [x] Pre-trained weights 
- [ ] Tensorboard support + general usability (eval script etc.)
- [ ] Multi-GPU support
- [ ] Data augmentation
- [ ] Model validation to _Baseline + CutMix_ 
- [ ] Training on custom data
- [ ] Signal propagation plots (from [first paper](https://arxiv.org/abs/2101.08692))
