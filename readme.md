![](/logo.png)

# NBMiner

Nvidia GPU Miner for `Bytom(BTM)`, `Ethereum(ETH)` , `Grin`, `Aeternity(AE)` mining.

## 中文说明

[查看中文说明](/readme_zh.md)

## Download

[Download here](https://github.com/NebuTech/BTMiner_NebuTech/releases)

## Support on Bitcointalk

[BitcoinTalk](https://bitcointalk.org/index.php?topic=5099379)

## Performance (stock frequency)

| Algorithm        |  Coin   | P106-100  |  1070ti  |  1080ti  |   2080   |
| :--------------- | :-----: | :-------: | :------: | :------: | :------: |
| tensority        |   BTM   |   1,900   |  3,400   |  5,000   |  11,500  |
| ethash           |   ETH   |   19.5M   |   26M    |   46M    |   35M    |
| tensority_ethash | BTM+ETH | 950+15.5M | 1350+22M | 2450+40M | 7000+28M |
| cuckaroo         | GRIN29  |    3.2    |   5.0    |   7.45   |   7.5    |
| cuckatoo         | GRIN31  |     -     |   0.92   |   1.45   |   1.66   |
| cuckoo_ae        |   AE    |    3.3    |   5.0    |   7.6    |   8.3    |

## Features

* Support Windows & Linux.
* Support backup mining pool configuration.
* Support SSL connection to mining pools.
* Dev Fee: 
  * tensority_ethash 3%
  * tensority(Pascal) 2%, tensority(Turing) 3%
  * ethash 0.65%
  * cuckaroo & cuckatoo & cuckoo_ae 2%

## Requirements

- **NVIDIA Driver version: >= 377**.
- GPU Specific Requirements:

|    Algorithm     |  Coin   | Compute Capability | Memory (Win7 & Linux) | Memory (Win10) |
| :--------------: | :-----: | :----------------: | :-------------------: | :------------: |
|    tensority     |   BTM   |   6.1, 7.0, 7.5    |          1GB          |      1GB       |
|      ethash      |   ETH   | 6.0, 6.1, 7.0, 7.5 |          4GB          |      4GB       |
| tensority_ethash | BTM+ETH |   6.1, 7.0, 7.5    |          4GB          |      4GB       |
|     cuckaroo     | GRIN29  | 6.0, 6.1, 7.0, 7.5 |          5GB          |      6GB       |
|     cuckatoo     | GRIN31  | 6.0, 6.1, 7.0, 7.5 |          8GB          |      10GB      |
|    cuckoo_ae     |   AE    | 6.0, 6.1, 7.0, 7.5 |          5GB          |      6GB       |

- \* Compute Capability reference link: [wikipedia](<https://en.wikipedia.org/wiki/CUDA#GPUs_supported>)