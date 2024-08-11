### Description

* laughter-collectorのWSL2向けdocker compose(GPU対応)です.

### Prerequisites

* Windows 11(64GB)
* NVidia video card (RTX3060 12GB)
* WSL2 (32GB and operation confirmed on Ubuntu 20.04)

*上記以外の構成では未確認.

### Installing

* 以下のコマンドでDockerをビルド.
```
docker compose build
```

## Usage

* Installing実行後に以下を実行.
```
docker exec sbv2-tool-01 python3 collect_laughter.py -ow -i /volumes/inputs -o /volumes/outputs -m large-v3
```

## Version

* 2024/08/12

## Acknowledgments

* [laughter-collector](https://github.com/litagin02/laughter-collector)
* [nVidia 525 + Cuda 11.8 + Python 3.10 + pyTorch GPU Docker image](https://dev.to/ordigital/nvidia-525-cuda-118-python-310-pytorch-gpu-docker-image-1l4a)
