# BTMiner_NebuTech
Nvidia GPU Miner for Bytom mining.

## 中文说明

[查看中文说明](/readme_zh.md)

## Download

[Download here](https://github.com/NebuTech/BTMiner_NebuTech/releases)

## Features：

* Support Win7、Win10、Linux
* Support pools using stratum protocol，tested on：[f2pool](https://www.f2pool.com/)、[antpool](https://www.antpool.com/)、[zhizhu](https://pool.zhizhu.top/)、[btcc](https://btccpool.info/) 、[91pool](http://www.91pool.com)、[uupool](http://uupool.cn)
* Do not require any CPU performance or PCIE bandwidth, funtion perfectly on rigs with 6 or more gpu cards.
* **Only NVIDIA Pascal and later GPU cards are supprted.**
* Contains 3% dev fee, can be turned off.

## Usage：

1. **Driver version: Windows >= 385 , Ubuntu >= 384**.
2. Edit `start_cmd.bat`(`start_cmd.sh`if using linux), set mining pool url after `-url `and username after `-user.`
3. Start mining by double click `start_cmd.bat` on windows, or start `start_cmd.sh` from terminal on linux.

## Reference GPU Hashrates

* **Tested with stock settings**

| GPU     | Hashrate（H/s） |
| ------- | --------------- |
| 1030    | 170             |
| 1050    | 300             |
| 1050Ti  | 360             |
| 1060-3G | 570             |
| 1060-6G | 610             |
| 1070    | 850             |
| 1070Ti  | 1100            |
| 1080    | 1200            |
| 1080Ti  | 1600            |
| Titan V | 3300            |

## CMD options：

**Typical usage** ：BTMiner_NebuTech -url btm.f2pool.com:9221 -user bm1xxxxxxxxxxxx.rigName

Options：

  * -h, --help    Displays this help.
  * -v, --version    Displays version information.
  * -c, --config <config file path>    Use config file rather than cmd line options.
  * -o, --url <url>    Mining pool url.
  * -u, --user <user>    User used in Mining pool, wallet address or username.
  * -p, --password <password>    Password used in mining pool.
  * -d, --devices <devices>    Specify GPU list to use. Format: "-d 0,1,2,3" to use first 4 GPU.
  * --no-fee    No dev fee, but turns off some optimization, result in lower hashrate.
  * -S, --ssl    Use SSL instead of regular tcp socket when connect to mining pool.
  * -M, --more-gpu    Set this option will avoid 'cuda out of memory error'.

## TODO

* Improve GPU error handle.
* API for miner status query.
* Try to improve hashrate

## Thanks

@earthGavinLee

## Change Log

#### v5.1(2018-07-07)

* Disable quick edit mode on windows CMD window, prevent from process frozen.
* Disable windows error report when miner crash.

#### v5.0(2018-07-03)

* Improve hashrate
* Option to start program using json config file
* Option to connect mining pool using SSL socket.
* Option to turn off dev fee.
* Remove CPU boost mode.
* Remove GUI_Wrapper

#### v3.3(2018-06-16)

* Function autosave user and url in GUI_Wrapper.
* Bug fix.

#### v3.0(2018-06-09)

* Hashrate improved
* Function auto set -i parameter for different gpu.
* Option -M for rigs encounterd with `CUDA out of memory error`.
* Function Simple GUI_Wrapper for beginners.
* Bug fix.

#### v2.0(2018-06-04)

* Function lower CPU usage.
* Option -C using CPU boost mode for high-end CPUs and motherboards with high PCIE bandwidth.
* Function Linux support.
* Bug fix.

#### v1.3(2018-06-03)

* First public version.