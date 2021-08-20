![](/logo.png)

# NBMiner

GPU Miner for `ETH`, `RVN`,  `GRIN`, `BEAM`, `CFX`, `ZIL`, `ERGO`, `AE`, `SERO`

## Disclaimer

[nbminer.com](https://nbminer.com) & [NBMiner_github](https://github.com/NebuTech/NBMiner) are the only 2 officially maintained site for publishing information and new releases of NBMiner.

Be aware when you download NBMiner binaries from other sources.

## 中文说明

[查看中文说明](/readme_zh.md)

## Contact Us

- Email: nebutech@hotmail.com
- Discord: https://discord.gg/ZMejVXj
- BitcoinTalk: https://bitcointalk.org/index.php?topic=5099379

## Download

[Download here](https://github.com/NebuTech/NBMiner/releases)

## Performance (stock settings)

| Algorithm             |  COIN   |  P106-100  |  P104-8G   |   1070ti   |  1080ti  |   2080   | RX580 2048sp |
| :--------------- | :-----: | :--------: | :--------: | :--------: | :------: | :------: | :----------: |
| ethash           |   ETH   |   21.2M   |   34.5M    |   26.9M    |   46M    |  35.5M   |     24M      |
| cuckatoo         | GRIN31  |     X      |    0.89    |    0.94    |   1.56   |   1.65   |      X       |
| cuckatoo32       | GRIN32  |   0.215    |    0.38    |    0.41    |   0.63   |   0.65   |      X       |
| cuckoo_ae        |   AE    |    3.35    |    5.5     |    5.15    |   7.9    |   8.75   |      X       |
| progpow_sero     |  SERO   |   10.3M    |   17.5M    |   13.3M    |  22.5M   |  25.8M   |     10M      |
| kawpow           |   RVN   |   10.3M    |   17.5M    |   13.3M    |  22.5M   |  25.8M   |     11M      |
| beamv3           |  BEAM   |    12.5    |    19.6    |    19.5    |    26    |   30.5   |      X       |
| octopus          |   CFX   |    5.5M    |    8.5M    |    9.8M    |  14.8M   |  48.5M   |     X     |
| ergo | ERGO | 42M | 68M | 53M | 64M | 74M | 64M(eth bios) |

## Features

* Support Windows & Linux.
* Support backup mining pool configuration.
* Support SSL connection to mining pools.
* Dev Fee: 
  * ethash etchash 1%
  * cuckatoo & cuckatoo32 & cuckoo_ae 2%
  * progpow_sero 2%
  * kawpow 2%
  * beamv3 2%
  * octopus 3%
  * ergo 2%

## Requirements

- **NVIDIA Driver version: >= 384**.
- Nvidia GPU Specific Requirements:

| Algorithm        |  Coin   | Compute Capability | Memory (Win7 & Linux) | Memory (Win10) |
| :--------------- | :-----: | :----------------: | :-------------------: | :------------: |
| ethash           |   ETH   | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 |          5GB          |      6GB      |
| cuckatoo         | GRIN31  | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 |          8GB          |      10GB      |
| cuckatoo32 | GRIN32 | 6.0, 6.1, 7.0, 7.5 | 8GB | 10GB |
| cuckoo_ae        |   AE    | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 |          5GB          |      6GB       |
| progpow_sero     |  SERO   | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 |          3GB          |      4GB      |
| kawpow           |   RVN   | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 |          3GB          |      4GB      |
| beamv3 | BEAM | 6.0, 6.1, 7.0, 7.5 | 3GB | 3GB |
| octopus | CFX | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 | 5GB | 6GB |
| ergo | ERGO | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 | 3GB | 3GB |

- \* Compute Capability reference link: [wikipedia](<https://en.wikipedia.org/wiki/CUDA#GPUs_supported>)

## Sample Usages

#### ETH

- **ethermine:** nbminer -a ethash -o ethproxy+tcp://asia1.ethermine.org:4444 -u 0x12343bdgf.worker
- **sparkpool:** nbminer -a ethash -o ethproxy+tcp://cn.sparkpool.com:3333 -u 0x12343bdgf.worker
- **f2pool:** nbminer -a ethash -o ethproxy+tcp://eth.f2pool.com:8008 -u 0x12343bdgf.worker
- **beepool:** nbminer -a ethash -o ethproxy+tcp://eth-pool.beepool.org:9530 -u 0x12343bdgf.worker
- **nanopool:** nbminer -a ethash -o ethproxy+tcp://eth-asia1.nanopool.org:9999 -u 0x12343bdgf.worker
- **herominers:** nbminer -a ethash -o ethproxy+tcp://ethereum.herominers.com:10201 -u 0x12343bdgf.worker
- **nicehash:** nbminer -a ethash -o nicehash+tcp://daggerhashimoto.eu.nicehash.com:3353 -u btc_address.worker
- **miningpoolhub**: nbminer -a ethash -o nicehash+tcp://asia.ethash-hub.miningpoolhub.com:20535 -u username.worker

#### ETH+ZIL:

- **ezil**: nbminer -a ethash -o stratum+tcp://cn.ezil.me:5555 -u ETH_WALLET.ZIL_WALLET.WORKER --enable-dag-cache
- **shardpool**: nbminer -a ethash -o stratum+tcp://ch1-zil.shardpool.io:3333 -u ETH_WALLET.WORKER -p ZIL_WALLET@cn.sparkpool.com:3333 -enable-dag-cache

#### Grin32

- **goblinpool**: nbminer -a cuckatoo32 -o stratum+tcp://grin32.goblinpool.com:3344 -u username.worker:passwd
- **f2pool:** nbminer -a cuckatoo32 -o stratum+tcp://grin32.f2pool.com:13654 -u username.worker:passwd
- **herominers:** nbminer -a cuckatoo32 -o stratum+tcp://grin.herominers.com:10301 -u username.worker:passwd
- **nicehash:** nbminer -a cuckatoo32 -o nicehash+tcp://grincuckatoo32.hk.nicehash.com:3383 -u btc_address.worker

#### AE

- **f2pool**: nbminer -a cuckoo_ae -o stratum+tcp://ae.f2pool.com:7898 -u ak_xxxxxxx.worker:passwd
- **beepool**: nbminer -a cuckoo_ae -o stratum+tcp://ae-pool.beepool.org:9505 -u ak_xxxx.worker:passwd
- **nicehash**: nbminer -a cuckoo_ae -o nicehash+tcp://cuckoocycle.eu.nicehash.com:3376 -u btc_address.test

#### SERO

- **beepool**: nbminer -a progpow_sero -o stratum+tcp://sero-pool.beepool.org:9515 -u wallet_address.worker:pswd
- **f2pool**: nbminer -a progpow_sero -o stratum+tcp//sero.f2pool.com:4200 -u wallet_address.worker:pswd

#### RVN

- **beepool**: nbminer -a kawpow -o  stratum+tcp://rvn-pool.beepool.org:9531 -u wallet.worker:passwd
- **f2pool**: nbminer -a kawpow -o  stratum+tcp://raven.f2pool.com:3636 -u wallet.worker:passwd
- **minermore**: nbminer -a kawpow -o stratum+tcp://us.rvn.minermore.com:4501 -u wallet.worker:paswd
- **bsod**: nbminer -a kawpow -o stratum+tcp://pool.bsod.pw:2640 -u wallet.worker:passwd
- **woolypooly**: nbminer -a kawpow -o stratum+tcp://rvn.woolypooly.com:55555 -u wallet.worker:passwd 

#### BEAM

- **sparkpool**: nbminer -a beamv3 -o stratum+ssl://beam.sparkpool.com:2222 -u wallet.worker:passwd
- **beepool**: nbminer -a beamv3 -o stratum+ssl://beam-pool.beepool.org:9507 -u wallet.worker:passwd
- **leafpool**: nbminer -a beamv3 -o stratum+ssl://beam-eu.leafpool.com:3333 -u wallet.worker:passwd
- **herominers**: nbminer -a beamv3 -o stratum+ssl://beam.herominers.com:10231 -u wallet.worker:passwd
- **nicehash**: nbminer -a beamv3 -o stratum+tcp://beamv3.eu.nicehash.com:3387 -u btc_address.worker

#### CONFLUX

- **beepool**: nbminer -a octopus -o stratum+tcp://cfx-pool.beepool.org:9555 -u wallet.worker
- **poolflare**: nbminer -a octopus -o stratum+tcp://cfx.ss.poolflare.com:3366 -u wallet.worker
- **f2pool**: nbminer -a octopus -o stratum+tcp://cfx.f2pool.com:6800 -u username.worker
- **woolypooly**: nbminer -a octopus -o  stratum+tcp://cfx.woolypooly.com:3094 -u wallet.worker
- **nicehash**: nbminer -a octopus -o stratum+tcp://octopus.eu.nicehash.com:3389 -u btc_address.worker

#### ERGO

- **herominers**: nbminer -a ergo -o stratum+tcp://ergo.herominers.com:10250 -u wallet.worker
- **woolypooly**: nbminer -a ergo -o stratum+tcp://erg.woolypooly.com:3100 -u wallet.worker
- **nanopool**: nbminer -a ergo -o stratum+tcp://ergo-eu1.nanopool.org:11111 -u wallet.worker
- **666pool**: nbminer -a ergo -o stratum+tcp://ergo.666pool.cn:9556 -u wallet.worker
- **nicehash**: nbminer -a ergo -o stratum+tcp://autolykos.eu-west.nicehash.com:3390 -u wallet.worker

## CMD options：

**nbminer -a algo -o protocol+socket_type://pool_host:pool_port -u wallet_address.worker -p passwd**

  * -h, --help    Displays this help.
  * -v, --version    Displays version information.
  * -c, --config \<config file path>    Use json format config file rather than cmd line options.
  * -a, --algo \<algo>    Select mining algorithm
  * --api  \<host:port>    The endpoint for serving REST API.
  * -o, --url \<url>    Mining pool url.
  * -u, --user \<user>    User used in Mining pool, wallet address or username.
  * -o1, --url1 \<url> url for backup mining pool 1.
  * -u1, --user1 \<user> username for backup mining pool 1.
  * -o2, --url2 \<url> url for backup mining pool 2.
* -u2, --user2 \<user> username for backup mining pool 2.
* -p,  --password \<password>  password for mining pool
* -p1,  --password1 \<password>  password for backup mining pool1
* -p2,  --password2 \<password>  password for backup mining pool2
* -d, --devices \<devices>    Specify GPU list to use. Format: "-d 0,1,2,3" to use first 4 GPU.
* -i, --intensity \<intensities>    Comma-separated list of intensities (1 -100).
* --strict-ssl    Check validity of certificate when use SSL connection.
* --proxy    Socks5 proxy used to eastablish connection with pool, E.g. 127.0.0.1:1080
* --cuckoo-intensity \<intensity>    Set intensity of cuckoo, cuckaroo, cuckatoo, [1, 12]. Smaller value means higher CPU usage to gain more hashrate. Set to 0 means autumatically adapt. Default: 0.
* --cuckatoo-power-optimize    Set this option to reduce the range of power consumed by rig when minining with algo cuckatoo. This feature can reduce the chance of power supply shutdown caused by overpowered. Warning: Setting this option may cause drop on minining performance.
* --temperature-limit, --tl \<temp-limit>    Set temperature limit of GPU, if exceeds, stop GPU.
* --temperature-start, --ts \<temp-start>    Set cool-down temperature target if GPU is stopped by `temperature-limit`, default to \<temp-limit> - 5.
* --log    Generate log file named `logs/log_<timestamp>.txt`.
* --log-file \<filename>    Generate custom log file. Note: This option will override `--log`.
* --no-nvml    Do not query cuda device health status.
* --fidelity-timeframe \<timeframe>    Set timeframe for the calculation of fidelity, unit in hour. Default: 24.
* --long-format    Use 'yyyy-MM-dd HH:mm:ss,zzz' for log time format.
* --verbose    Print communication data between miner and pool in log file.
* --device-info    Print device cuda information.
* --fee \<fee>    Change devfee in percentage, [0-5]. Set to '0' to turn off devfee with lower hashrate. Otherwise, devfee = max(set_value, def_value).
* --generate-config \<filename>    Generate a sample config json file.
* --no-watchdog    Disable watchdog process.
* --platform \<platform>    Choose platform，0: NVIDIA+AMD (default), 1: NVIDIA only, 2: AMD only
* --share-check \<value>    If \<value> minutes without share, reboot miner, set 0 to disable. Default: 30
* --no-interrupt    set this option will disable miner interrupting current GPU jobs when a new job coming from pool, will cause less power supply issue, but might lead to a bit higher stale ratio and reject shares.
* --enable-igpu    AMD igpu is disabled by default, set this option to enable.
* **--mt, --memory-tweak \<mode>    Memory timings optimize for Nvidia GDDR5 & GDDR5X gpus. range [1-6]. Higher value equals higher hashrate. Individual value can be set via comma seperated list. Power limit may need to be tuned up to get more hashrate. Higher reject share ratio can happen if mining rig hits high temperature, set lower value of `-mt` can reduce reject ratio. Under windows, a custom driver need to be installed when using `-mt`, can installed manually by option  `--driver`, or run nbminer.exe with admin privilege to perform auto-install. Under linux, admin priviledge is needed to run, `sudo ./nbminer -mt x`. `OhGodAnETHlargementPill` is not needed anymore if `-mt` is enabled when mining on 1080 & 1080ti GPUs.**
* **--driver \<action>    Windows only option, install / uninstall driver for `memory tweak`. Run with admin priviledge. install: `nbminer.exe --driver install`, uninstall: `nbminer.exe --driver uninstall`. **
* **-lhr \<value>    Partially unlock hashrate for Nvidia LHR GPUs. [-1, 100]. 0: auto, -1: off. Others: set to 60 means trying to reach 60% of nonlocked max hashrate.**

## API Reference

### Web Monitor

Open http://api_host:port/ in your browser to use web monitor.

### Request

GET http://api_host:port/api/v1/status

### Response

``` json
{
    "miner": {
        "devices": [
            {
                "accepted_shares": 2,
                "accepted_shares2": 0,
                "core_clock": 1620,
                "core_utilization": 100,
                "fan": 47,
                "fidelity1": 5.859799716605649,
                "fidelity2": 0,
                "hashrate": "217.1 M",
                "hashrate2": "36.19 M",
                "hashrate2_raw": 36190716.266428046,
                "hashrate_raw": 217144297.59856823,
                "id": 0,
                "info": "GeForce RTX 2070",
                "mem_clock": 6801,
                "mem_utilization": 86,
                "pci_bus_id": 1,
                "power": 188,
                "rejected_shares": 0,
                "rejected_shares2": 0,
                "temperature": 72
            },
            {
                "accepted_shares": 0,
                "accepted_shares2": 0,
                "core_clock": 1607,
                "core_utilization": 100,
                "fan": 0,
                "fidelity1": 0,
                "fidelity2": 0,
                "hashrate": "168.5 M",
                "hashrate2": "42.11 M",
                "hashrate2_raw": 42113955.19774488,
                "hashrate_raw": 168455820.79097953,
                "id": 1,
                "info": "P102-100",
                "mem_clock": 5508,
                "mem_utilization": 100,
                "pci_bus_id": 4,
                "power": 232,
                "rejected_shares": 0,
                "rejected_shares2": 0,
                "temperature": 57
            }
        ],
        "total_hashrate": "708 M",
        "total_hashrate2": "164.4 M",
        "total_hashrate2_raw": 164395439.13815895,
        "total_hashrate_raw": 708044466.8349969,
        "total_power_consume": 839
    },
    "reboot_times": 0,
    "start_time": 1586944619,
    "stratum": {
        "accepted_shares": 2,
        "accepted_shares2": 0,
        "algorithm": "hns_ethash",
        "difficulty": "8.59 G",
        "difficulty2": "8.59 G",
        "dual_mine": true,
        "latency": 221,
        "latency2": 0,
        "rejected_shares": 0,
        "rejected_shares2": 0,
        "url": "handshake.hk.nicehash.com:3384",
        "url2": "daggerhashimoto.hk.nicehash.com:3353",
        "use_ssl": false,
        "use_ssl2": false,
        "user": "3QHNv52ahdCyeYTGVYDPGjRzMpkknjjfAf.test",
        "user2": "3QHNv52ahdCyeYTGVYDPGjRzMpkknjjfAf.test"
    },
    "version": "30.0"
}
```

## Change Log

#### 39.1(2021-08-21)

- `optimize`: `ethash` improve hashrate of `LHR` mode 1 - 2%，default value of `-lhr`changes from 68 to 69，manually set to 70 is also very promising.
- `fix`: `LHR` mode support on windows driver 471.11
- `fix`: `kawpow` issue of v39.0
- `fix`: `Radeon vii` issue on windows driver 21.6.1+

#### 39.0(2021-08-15)

- `feature`: `ethash` New LHR mode for ETH mining on RTX 30 series LHR GPUs, supports Windows & Linux, able to get ~70% of maximum unlocked hashrate.
  - This mode can be tuned by argument `-lhr`, only works for `ethash` right now.
  - `-lhr` default to 0, meaning even if `-lhr` is not set, LHR mode with `-lhr 68` will be applied to LHR GPUs if certain GPUs are detected.
  - Tune LHR mode by setting `-lhr <value>`, a specific value will tell miner **try to reach** `value` percent of maximum unlocker hashrate, e.g. `-lhr 68` will expect to get 68% of hashrate for same model non-LHR GPU.
  - Higher `-lhr` value will results in higher hashrate, but has higher possibility to run into lock state, which will leads to much less hashrate.
  - A good start tuning value is 68, which has been tested to be stable on most rig configurations.
  - `-lhr` value can be set for each GPU by using comma separeted list, `-lhr 65,68,0,-1`, where `-1` means turn off LHR mode.

#### v38.2(2021-07-27)

- `fix`: AMD kernel error on certain GPUs with 21.6.1+ drivers under windows.

#### v38.1(2021-06-29)

- `fix`: high CPU usage in v38.0

#### v38.0(2021-06-29)

- `feature`: `ergo` add `mining.extranonce.subscribe` support.
- `fix`: eliminate memory leak by NVML library for Nvidia driver 460+ on windows.
- `fix`: `--enable-dag-cache` causes crash on certain situation.

#### v37.6(2021-06-03)

- `fix`: `ethash` `--enable-dag-cache` cause crash on AMD GPUs when switch DAG file.
- `fix`: `ergo` support on `AMD Vega` GPUs.

#### v37.5(2021-05-21)

​    changes from 37.3

- `new algo`: `ergo` for AMD GPU, can be faster with ETH mining timings
- `optimize`: `ergo` slightly improce hashrate on Nvidia GPUs
- `feature`: use `--temperature-limit` & `--temperature-start` to protect GPU from overheat, detail in readme.md

#### v37.3(2021-05-06)

- `feature`: add option `--enable-dag-cache` to allow an extra `DAG` for different `epoch` cached in GPU memory, useful for `ETH+ZIL` mining and mining on `NiceHash`.

#### v37.2(2021-04-24)

- `feature`: add option `-p -p1 -p2` for setting `password` of mining pool, old format `-u wallet.worker:passwd` is disabled，`:` can be added as part of worker or wallet
- `optimize`: `ethash` minor hashrate improvement on RDNA GPUs
- `fix`: compatibility issue on lasted AMD `21.4.1` driver.

#### v37.1(2021-03-25)

- `fix`: `ergo` high reject ratio on 10 series Nvidia GPUs
- `fix`: `ergo` pool compatibility
- Recommend miners with `p106-90` & `1060 3G` to mine `ERGO`, hashrate will be increased significantly with `-mt` option.

#### v37.0(2021-03-19)

- `new algo`: `ergo` for mining `ERGO` coin on Nvidia GPUs.
- `delete algo`: `bfc` `cuckarood` for Nvidia, `octopus` for AMD
- `fix`: `octopus` support `CFX` new address format
- `fix`: 'clBuildProgram error' issue on Vega for versions 35.0 - 36.1
- `feature`: disable AMD iGPU by default, can be enabled back by setting `--enable-igpu`
- `other`: minor bug fix, improve overall stability

####  v36.1(2021-01-11)

- `optimize`: `octopus` Lower power comsumption for 20、30 series Nvidia GPU, improve hashrate 2% on 16 series Nvidia GPU
- `fix`: `ethash` Fix performance  degradation  under win8 & win8.1 for Nvidia 10 series GPUs.
- `fix`: `ethash` Slightly reduce stale ratio.
- `fix`: A random crash bug fix, improve overall stability
- `feature`: Add `detail datetime` & `cpu usage` in summary log
- `feature`: `ethash` If DAG verification failed, display corresponding GPU name in red in summary.

#### v36.0(2020-12-28)

- `fix`: `kawpow` crash on some GPUs in versions `35.x`
- `fix`: `ethash` performance  degradation  under win7 for Nvidia 10 series GPUs.
- `delete algo`: `eaglesong`, `eaglesong_ethash`, `trb`, `trb_ethash`, `hns`, `hns_ethash`, `sipc`, `cuckaroo`, `cuckaroo_swap`
- `feature`: smaller binary size

#### v35.2(2020-12-22)

**Compared to v35.0**

- `optimize`: `ethash` More stable under high OC for Nvidia 16、20、30 series GPUs.
- `optimize`: `octopus` Improve hashrate 1-3% for 16, 20, 30 Nvidia GPUs
- `feature`: `ethash` DAG verification after creation, if miner showed log in red font: `Verification failed, invalid 2.0%`, please consider lower GPU overclock

#### v35.1(2020-12-21)

- `optimize`: `ethash` More stable under high OC for Nvidia GPUs
- `optimize`: `octopus` Improve hashrate 1-3% for 16, 20, 30 Nvidia GPUs

#### v35.0(2020-12-14)

- `feature`: `ethash` Add statistics for `invalid shares`, in cmd log, api and web monitor.
- `feature`: Turn off limitation for not allowing to run under Virtual Machine.
- `feature`: Add statistics for Health information of AMD GPU
- `fix`: More detail error information of OpenCL api
- `fix`: Reduce CPU usage.

#### v34.5(2020-12-05)

- `optimize`: `ethash` Improve hashrate 1% on certain Nvidia GPUs
- `optimize`: `octopus` Minor improvement on certain 20 & 30 series Nvidia GPUs
- `feature`: `-mt` More effective and compatibility on Geforce Pascal GPUs
- `fix`: `kawpow` `progpow_sero` Fix crash on certain AMD & Nvidia rigs

#### v34.4(2020-12-02)

- `optimize`: `octopus` Improve hashrate 1-5% on Nvidia 16, 20, 30 series GPUs, 29.2M on 1660s

#### v34.3(2020-12-01)

- `fix`: `etchash` error on swiching epoch, `ETC` miners should upgrade to this version.
- `fix`: support for AMD 20.11.x driver version
- `fix`: `ethash` more stable hashrate under windows

#### v34.2(2020-11-29)

- `fix`: `ethash` Reduce stale share ratio.

#### v34.1(2020-11-28)

- `fix`: `ethash` Fix display hashrate only half of normal hashrate on certain windows rigs.

#### v34.0(2020-11-28)

- `optimize`: `ethash` Improve hashrate on Nvidia 10 series GPUs，3% higher hashrate under same PowerLimit, or same hashrate with 5%-10% lower PowerLimit.

#### v33.8(2020-11-25)

- `feature`: `octopus`Add support for mining on `NiceHash`

#### v33.7(2020-11-23)

- `feature`: Add an option `-no-interrupt`, set this option will disable miner interrupting current GPU jobs when a new job coming from pool, will cause less power supply issue, but might lead to a bit higher stale ratio and reject shares.
- `feature`: Add `effiecieny` display in console, showing `hashrate per watt` for each GPU
- `feature`: Add 10min 4h 24h pool hashrate display in web monitor.

#### v33.6(2020-11-21)

- `optimize`: `octopus` improve hashrate: +10% on 16 20 30 series Nvidia GPUs, 27.5M on 1660s.
- `note`: `octopus` From this version, GPUs that has higher core performance than memory performance, need to overclock memory to get higher hashrate, e.g. 2080 3070

#### 33.5(2020-11-21)

- `optimize`: `octopus` improve hashrate: +90% on 16 20 30 series Nvidia GPUs, at least +100%  on all other GPUs

#### v33.4(2020-11-12)

- `optimize`: `octopus` improve hashrate: +35% on 16 20 30 series Nvidia GPUs, +20% on all other GPUs
- `new algo`: `etchash` for upcoming ETC upgrade
- `feature`: add effective pool hashrate on console & api, 10min 4h 24h.

#### v33.3(2020-11-04)

- `optimize`: `octopus` improve hashrate: Nvidia, +3% on 10 series, +20% on 16, 20, 30 series
- `new algo`: `octopus` for AMD support.
- `fix`: crash upon start on certain Nvidia rigs.

#### v33.2(2020-11-01)

- `optimize`: `octopus` improve hashrate: +150% on 10 series, +80% on 16, 20, 30 series
- `fix`: `--share-check 0` cause high CPU usage
- `fix`: Added back `Uptime` in console summary

#### v33.1(2020-10-29)

- `fix`: some format error on console print
- `optimize`: `octopus` lower CPU usage
- `feature`: add new option `--share-check`, if no share found in a set period of time, miner will reboot. default to 30 minutes. SOLO miners should set this option to `0` to turn off check.

#### v33.0(2020-10-28)

- `new algo`: `octopus` for mining`conflux`，support both solo mining and pool mining, need Nvidia GPU above 6G
- `optimize`: `ethash` improve performance on Vega & Navi GPUs
- `optimize`: `beamv3` improve performance on high end 10xx Nvidia GPUs
- `feature`: modify summary output on console, add share statistics for each GPU.
- `fix`: `ethash` fix zero hashrate on certain cases for AMD GPUs

#### v32.1(2020-10-05)

- `bug fix`: Fix AMD device initialization failure on some rigs.

#### v32.0(2020-09-30)

- `new algo`: `beamv3` for mining `BEAM` with Nvidia 3GB+ GPUs
- `new algo`: `cuckatoo32` add support for Nvidia 6GB GPU
- `optimize`: `ethash` for AMD RX 4xx, 5xx, Vega series 8GB+ GPUs 
- `feature`: `ethash` support mining up to epoch 800

#### v31.1(2020-06-24)

- `new algo`: `cuckatoo32`  for `Grin32` on Nvidia 8G above GPUs
- `kawpow`: support for `NiceHash`'s `extranonce.subscribe` protocol

#### v30.2(2020-05-05)

- `windows`: Auto install driver if `--memory-tweak` is set and driver is not installed.
- `windows`: Fix `driver install failed` issue on some windows rigs.
- `kawpow`: Fix `duplicate share` issue on some pools.

#### v30.1(2020-05-03)

- Reduce `ethash` `kawpow` startup time.
- Fix a possible crash on certain rigs of reason `invalid kernel image`.
- Do not apply memory tweak if `-mt` is set to 0 on corresponding gpu.
- Print system information on start.

#### v30.0(2020-04-30)

- Add option `--memory-tweak` , optimize memory timings of Nvidia GD5 & GD5X GPUs. Detail describe can be found in readme.md
- Add option `--verbose`, print pool communucation log.
- Add option `--proxy`, user can using socks5 proxy to set up connection with pool.
- Add number of shares per GPU in both log print and api.
- Minor bug fix and improvements.

#### v29.1(2020-04-09)

- Fix low hashrate of `kawpow` on AMD RDNA GPU.
- Improve kawpow hashrate on AMD GPU.

#### v29.0(2020-04-03)

- Add support for RVN new algo `kawpow` mining on Nvidia & AMD gpus.

#### v28.1(2020-03-30)

- Support HNS & HNS+ETH mining on NiceHash

#### v28.0(2020-03-28)

- Add support for mining TRB & TRB+ETH on Nvidia GPU
- Add support for mining ETH on `miningrigrentals`.
- Minor improvements and fixes.

#### v27.7(2020-03-15)

- Fix ETH mining on NiceHash
- Fix NVML initialization failure on certain cases.

#### v27.6(2020-03-14)

- Improve HNS & HNS+ETH on Nvidia GPU.

#### v27.5(2020-03-05)

- Fix high ETH reject rate on certain pools when mining HNS+ETH
- Slightly improve mining HNS+ETH on Nvidia GPU.

#### v27.4(2020-02-28)

- Fix support the certain AMD Vega GPUs.
- Fix a potential bug when mining under AMD+Nvidia mixed rig.

#### v27.3(2020-02-27)

- Add HNS+ETH mining on AMD GPU
- Improve HNS+ETH performance on Nvidia GPU
- **Note**: `-di` calculation is changed in this version for HNS+ETH.
  - The value of `-di`  = `work_size_of_hns` / `work_size_of_eth`
  - E.g, `-di 5`  on a stock freq 1070ti will get 26M for eth & 130M for hns.

#### v27.2(2020-02-20)

- Improve HNS performance on AMD GPU

#### v27.1(2020-02-19)

- Improve HNS performance on Nvidia GPU
- Add support for HNS mining for AMD GPU

#### v27.0(2020-02-18)

- Add support for HNS & HNS_ETH mining for NVIDIA GPU
- Minor bug fix and improvements.

#### v26.2(2019-11-21)

- Improve CKB+ETH performance on AMD GPU.
- Fix bug of 26.1: Launch crash on certain AMD rigs.

#### v26.1(2019-11-15)

- Add support for mining CKB+ETH on AMD GPU.
- Improve performance for mining CKB on Nvidia GPU.

#### v26.0(2019-10-11)

- Add support for BFC mininig on Nvidia GPU.
- Fix CKB compatibility on AMD GPU.
- Fix cuckcoocycle on nicehash.

#### v25.5(2019-10-05)

- Fix a bug when mining CKB+ETH.
- Fix a compatibility issue in CKB stratum protocol.

#### v25.4(2019-10-04)

- Improve CKB mining performance on both NVIDIA & AMD cards.
- Improve CKB+ETH performance on NVIDIA cards.
- Add support for mining SERO on AMD cards.
- Add a new option `--platform` to allow users to choose GPU platform.

#### v25.2(2019-09-10)

- Add support for `CKB` mining on AMD cards under linux.
- Bug fix.

#### v25.1(2019-09-07)

- Add support for `CKB` mining on AMD cards.

#### v25.0(2019-09-05)

- Add support for `CKB` mining & `CKB`+`ETH` dual mining.
- Enhance `-di` parameter to support comma separated list to specify `-di` value for each card.
- The default value of `-di` for `CKB`+`ETH` mining ranges from 4 ~ 8 depending on GPU model, valid value range in [1, 10], higher value means higher intensity for `ETH`.
- The best value of `-di` differs by GPU model, overclock and power limitation.

#### v24.4(2019-08-16)

- Fix SIPC dxpool compatibility.
- **1080 & 1080ti  users should use `OhGodAnETHlargementPill` to boost SIPC performance.**

#### v24.3(2019-08-15)

- Add support for mining SIPC.
- Fix high CPU usage mining SERO with 24.1 & 24.2
- Fix Grin intensity.

#### v24.2(2019-07-17)

- Disable the auto-switch from cuckaroo -> cuckarood
- Slightliy improve RTX2060 Grin29 performance under win10
- Fix startup stuck issue on some linux distro.
- Add new option `--generate-config` to generate a sample config file.
- **Note: Linux sero mining need to set a env before start if run with --no-watchdog, please check `start_sero.sh`**

#### v24.1(2019-07-16)

- Fix lower hashrate than previous version for Grin29 & AE on 10xx 6GB cards
- Fix mining Grin29 AE on Turing 6GB Cards on Win10.
- Fix the disfunction of auto-reboot when GPU error happens.
- Fix start using json config file.
- Change the GPU MEM size display upon launch from Total Size to Available Size.

#### v24.0(2019-07-15)

- Support Grin29 fork on 17th, July.
  - When using algo `cuckaroo`, v24.0 will do an automatically switch to `cuckarood` on height 262080.
  - Add a temporary option `-grin29-fork-height`, user can test the auto-switch by setting this option to lower height value.
- Improve performance on Grin29 & AE.
- Add support for mining `SERO`, algo `progpow_sero`.
- Add option `-intensity` to set the intensity level for each GPU.
- Add option `-fidelity-timeframe` to customize the timeframe for fidelity calculation.
- Add option `-log-file` to set a specified log filename.
- Add option `-no-nvml` to close the periodical query for GPU status.
- Add new method to turn on NiceHash protocol, `nicehash+tcp://`
  - Also compatible with previous url based method.
- Minor improvement and bug fix.

#### v23.3(2019-06-14)

- Fix mining AE (cuckoocycle) on NiceHash.
- Add option to set a temperature limit on GPU.

#### v23.2(2019-05-09)

- Improve Grin & AE & SWAP performance.
- Add support for mining AE on NiceHash.
- Add display output of Fidelity.
- Minor improvement and bug fix.

#### v22.2(2019-04-15)

- Improve compatiblity for mining Grin31 on windows 8GB cards.
- Set default `--cuckoo-intensity` to 4, lower CPU usage on default settings when mining Grin & AE.

#### v22.1(2019-04-12)

- Add support for mining Swap (XWP).
- Improve Grin29 & AE performance.
- Improve Windows compatibility on Grin & AE, significant boost on performance.

#### v21.4(2019-04-03)

- Improve Grin31 performance.
- Improve performance of Grin29 & AE on RTX cards.
- Fix Grin31 compatibility on Win7 with 8G cards.
- New option to reduce the range of power consumption by multi-gpu rig.
- Add miner Up Time print in cmd outputs.

#### v21.3(2019-03-20)

- Fix bug: Occasionlly lower local hashrate than previously version.
- Do not run GPU if mining pool not connected when mining Grin & AE.

#### v21.2(2019-03-15)

- Fix bug: `"GPU hung detected"` happens under some normal conditions.

#### v21.1(2019-03-14)

- Improve Grin29 performance
- Add support for mining Grin & AE on Turing cards.
- Add detection for GPU hung.
- Increase chance of accept share when mining Grin on NiceHash.
- Fix ETH mining on NiceHash.
- Fix "accecpt share checking" bug  when using backup mining pools.

#### v21.0(2019-03-06)

- Add support for AE (Aeternity)
- Improve performance on Grin29 & Grin31
- Improve miner stability.

#### v20.0(2019-02-21)

- Add support for Grin31
- Add support for mining Grin on NiceHash
- Add new option to tune CPU usage when mining Grin.
- Improve BTM+ETH performance on RTX cards.
- FIx bug of lower hashrate when mining BTM on rigs with mixed 10 series and 20 series cards.
- Do not add a default worker name if no worker name specified by user.

#### v14.0(2019-01-30)

- BTM mining, improve over 200% on RTX cards.
- Improve Grin mining.

#### v13.2(2019-01-17)

- Add support mining Grin on 1066-win10.
- Fix support for Solo mining using grin-server.

#### v13.1(2019-01-15)

- Add support for mining Grin coin (cuckaroo29).
- Minor bug fix and improvement.

#### v12.4(2018-01-05)

- Improve hashrate of BTM+ETH dual mining about 6%.

#### v12.3(2018-12-30)

- Fix a bug that could cause many reject shares when epoch changes under ETH dual mining .

#### v12.2(2018-12-26)

- Fix high stale share and reject share ratio when use big `-di` for dual mining BTM+ETH.
- Fix the support of web monitor for dual mining.
- Minor bug fixs and improvements.

#### v12.1(2018-12-24)

- Fix support ETH PPS+ mode on F2pool
- Add support for ETH on NiceHash (with protocol header `ethnh`)
- Fix rest api when dual mining.
- Minor bug fixs.

#### v12.0(2018-12-19)

- **New `BTM+ETH` dual mining mode.**
- Decrease the required driver version to 377.
- Temporarily remove support for XMR mining.
- Fix start using config file.
- Add a default protocol header if not specified.

#### v11.0(2018-12-12)

- Improve BTM hashrate.
- Add support for ETH and XMR mining.
- Optimize handle for new job, increase profit on mining pool.
- Colorful output on console.
- Add support for backup mining pools.
- Decrease dev fee of BTM to 2%.

#### v10.0(2018-10-03)

- Improve hashrate

#### v9.0(2018-08-28)

- Improve hashrate ~30%
- Improve stability

#### v8.0(2018-08-17)

- Improve hashrate 10% - 15%
- Lower skipped share rate, increase actual hashrate on mining pool.
- Added display for mining pool latency.
- Added display for mining pool difficulty.
- Improve API web monitor.
