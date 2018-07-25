# BTMiner_NebuTech
Nvidia GPU Miner for `Bytom` mining.

## 中文说明

[查看中文说明](/readme_zh.md)

## Download

[Download here](https://github.com/NebuTech/BTMiner_NebuTech/releases)

## Features：

* Support Win7、Win10、Linux
* Support pools using stratum protocol
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
| 1030    | 175             |
| 1050    | 310             |
| 1050Ti  | 375             |
| 1060-3G | 590             |
| 1060-6G | 630             |
| 1070    | 880             |
| 1070Ti  | 1140            |
| 1080    | 1250            |
| 1080Ti  | 1680            |
| Titan V | 3400            |

## CMD options：

**Typical usage** ：BTMiner_NebuTech -url btm.f2pool.com:9221 -user bm1xxxxxxxxxxxx.rigName

Options：

  * -h, --help    Displays this help.
  * -v, --version    Displays version information.
  * -c, --config \<config file path>    Use config file rather than cmd line options.
  * --api  \<host:port>        The endpoint for serving REST API.
  * -B, --browser    Automatically open system browser for web monitor. Windows only.
  * -o, --url \<url>    Mining pool url.
  * -u, --user \<user>    User used in Mining pool, wallet address or username.
  * -p, --password \<password>    Password used in mining pool.
  * -d, --devices \<devices>    Specify GPU list to use. Format: "-d 0,1,2,3" to use first 4 GPU.
  * --no-fee    No dev fee, but turns off some optimization, result in lower hashrate.
  * -S, --ssl    Use SSL instead of regular tcp socket when connect to mining pool.
  * -M, --more-gpu    Set this option will avoid 'cuda out of memory error'.

## GPU Tuning

Bytom mining performance depend heavily on GPU core, instead of GPU memory.

Miner can gain beffer hashrate if tuning down GPU memory frequency.

For example, using MSI Afterburner to turn down GPU memory to -500.

## API Reference

### Web Monitor

Open http://api_host:port/ in your browser to use web monitor.

### Request

GET http://api_host:port/api/v1/status

### Response

``` json
{
    "kernel_reboot_times": 0,
    "miner": {
        "devices": [{
            "core_clock": 1556,
            "core_utilization": 100,
            "fan": 36,
            "hashrate": 1499,
            "id": 0,
            "info": "GeForce GTX 1080 Ti 11178 MB",
            "power": 182,
            "temperature": 65
        }, {
            "core_clock": 1518,
            "core_utilization": 100,
            "fan": 34,
            "hashrate": 1490,
            "id": 1,
            "info": "GeForce GTX 1080 Ti 11178 MB",
            "power": 172,
            "temperature": 62
        }],
        "total_hashrate": 2989,
        "total_power_consume": 354
    },
    "start_time": 1532482659,
    "stratum": {
        "accepted_share_rate": 0.99,
        "accepted_shares": 99,
        "password": "",
        "rejected_share_rate": 0.01,
        "rejected_shares": 1,
        "url": "btm.pool.zhizhu.top:3859",
        "use_ssl": false,
        "user": "bmxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.test"
    },
    "version": "v6.0"
}
```

## TODO

* Improve GPU error handle.
* Try to improve hashrate

## Thanks

@earthGavinLee

## Change Log

#### v6.0(2018-07-23)

- Add API for status query.
- Add dummy web monitor.
- Add more GPU status report: power usage, core clock, core utilization
- Low-level parameter adjustment, improve 2-3% hashrate on some mining rigs.
- Runtime check for number of corresponding responses for submits.
- Improve console log format

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