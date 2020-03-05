![](/logo.png)

# NBMiner

GPU Miner for `GRIN`, `AE`, `CKB`, `SERO`, `SIPC`, `BTM`, `ETH`, `SWAP`mining.

## 中文说明

[查看中文说明](/readme_zh.md)

## Contact Us

- Email: nebutech@hotmail.com
- Discord: https://discord.gg/ZMejVXj
- BitcoinTalk: https://bitcointalk.org/index.php?topic=5099379

## Download

[Download here](https://github.com/NebuTech/BTMiner_NebuTech/releases)

## Performance (stock frequency)

| Algorithm        |  Coin   |  P106-100  |  P104-8G   |   1070ti   |  1080ti  |   2080   | RX580 2048sp |
| :--------------- | :-----: | :--------: | :--------: | :--------: | :------: | :------: | :----------: |
| tensority        |   BTM   |   1,900    |    3000    |   3,400    |  5,000   |  11,500  |      -       |
| ethash           |   ETH   |   21.2M    |   34.5M    |   26.9M    |   46M    |  35.5M   |      -       |
| tensority_ethash | BTM+ETH | 950+15.5M  | 1600+26.5M |  1350+22M  | 2450+40M | 7000+28M |      -       |
| cuckaroo         | GRIN29  |    3.45    |    5.6     |    5.25    |   8.1    |   8.9    |      -       |
| cuckarood        | GRIN29  |    3.45    |    5.6     |    5.25    |   8.1    |   9.1    |      -       |
| cuckatoo         | GRIN31  |     -      |    0.89    |    0.94    |   1.56   |   1.65   |      -       |
| cuckoo_ae        |   AE    |    3.35    |    5.5     |    5.15    |   7.9    |   8.75   |      -       |
| cuckaroo_swap    |  SWAP   |    3.45    |    5.6     |    5.25    |   8.1    |   8.9    |      -       |
| progpow_sero     |  SERO   |   10.3M    |   17.5M    |   13.3M    |  22.5M   |  25.8M   |     10M      |
| sipc             |  SIPC   |    600k    |    940k    |    780k    |  1170k   |  1050k   |      -       |
| eaglesong        |   CKB   |    430M    |    640M    |    740M    |  1150M   |  1160M   |     350M     |
| eaglesong_ethash | CKB+ETH | 203M+20.5M |  275M+34M  | 415M+26.5M | 600M+44M | 790M+36M |   200M+22M   |
| bfc              |   BFC   |     80     |    130     |    120     |   190    |   210    |      -       |
| hns              |   HNS   |    165M    |    250M    |    295M    |   450M   |   420M   |     145M     |
| hns_ethash       | HNS+ETH |  76M+19M   |  120M+30M  |  130M+26M  | 176M+44M | 305M+34M |  68M+22.5M   |

## Features

* Support Windows & Linux.
* Support backup mining pool configuration.
* Support SSL connection to mining pools.
* Dev Fee: 
  * tensority(Pascal) 2%, tensority(Turing) 3%, tensority_ethash 3%
  * ethash 0.65%
  * cuckaroo & cuckarood & cuckatoo & cuckoo_ae & cuckaroo_swap 2%
  * progpow_sero 2%
  * sipc 2%
  * eaglesong 2%, eaglesong_ethash 3%
  * bfc 3%
  * hns 2%, hns_ethash 3%

## Requirements

- **NVIDIA Driver version: >= 377**.
- GPU Specific Requirements:

| Algorithm        |  Coin   | Compute Capability | Memory (Win7 & Linux) | Memory (Win10) |
| :--------------- | :-----: | :----------------: | :-------------------: | :------------: |
| tensority        |   BTM   |   6.1, 7.0, 7.5    |          1GB          |      1GB       |
| ethash           |   ETH   | 6.0, 6.1, 7.0, 7.5 |          4GB          |      4GB       |
| tensority_ethash | BTM+ETH |   6.1, 7.0, 7.5    |          4GB          |      4GB       |
| cuckaroo(d)      | GRIN29  | 6.0, 6.1, 7.0, 7.5 |          5GB          |      6GB       |
| cuckatoo         | GRIN31  | 6.0, 6.1, 7.0, 7.5 |          8GB          |      10GB      |
| cuckoo_ae        |   AE    | 6.0, 6.1, 7.0, 7.5 |          5GB          |      6GB       |
| cuckaroo_swap    |  SWAP   | 6.0, 6.1, 7.0, 7.5 |          5GB          |      6GB       |
| progpow_sero     |  SERO   |     6.0 - 7.5      |          2GB          |      2GB       |
| sipc             |  SIPC   | 6.0, 6.1, 7.0, 7.5 |          1GB          |      1GB       |
| eaglesong        |   CKB   | 6.0, 6.1, 7.0, 7.5 |         0.1GB         |     0.1GB      |
| eaglesong_ethash | CKB+ETH | 6.0, 6.1, 7.0, 7.5 |          4GB          |      4GB       |
| bfc              |   BFC   | 6.0, 6.1, 7.0, 7.5 |          5GB          |      6GB       |
| hns              |   HNS   | 6.0, 6.1, 7.0, 7.5 |         0.1GB         |      4GB       |
| hns_ethash       | HNS+ETH | 6.0, 6.1, 7.0, 7.5 |          4GB          |      4GB       |

- \* Compute Capability reference link: [wikipedia](<https://en.wikipedia.org/wiki/CUDA#GPUs_supported>)

## Sample Usages

#### BTM

- **f2pool:** nbminer -a tensority -o stratum+tcp://btm.f2pool.com:9221 -u bm1xxxxxxxxxx.worker
- **antpool:** nbminer -a tensority -o stratum+tcp://stratum-btm.antpool.com:6666 -u username.worker
- **matpool.io:** nbminer -a tensority -o stratum+tcp://btm.matpool.io:8118 -u bm1xxxxxxxxxxx.worker

#### ETH

- **ethermine:** nbminer -a ethash -o ethproxy+tcp://asia1.ethermine.org -u 0x12343bdgf.worker
- **sparkpool:** nbminer -a ethash -o ethproxy+tcp://cn.sparkpool.com:3333 -u 0x12343bdgf.worker
- **f2pool:** nbminer -a ethash -o ethproxy+tcp://eth.f2pool.com:8008 -u 0x12343bdgf.worker
- **nanopool:** nbminer -a ethash -o ethproxy+tcp://eth-asia1.nanopool.org:9999 -u 0x12343bdgf.worker
- **nicehash:** nbminer -a ethash -o nicehash+tcp://daggerhashimoto.eu.nicehash.com:3353 -u btc_address.worker

#### BTM+ETH

- **f2pool:** nbminer -a tensority_ethash -o stratum+tcp://btm.f2pool.com:9221 -u btm_address.btm_worker -do ethproxy+tcp://eth.f2pool.com:8008 -du eth_address.eth_worker

#### Grin29

- **sparkpool:** nbminer -a cuckarood -o stratum+tcp://grin.sparkpool.com:6666 -u 123@qq.com/worker
- **f2pool:** nbminer -a cuckarood -o stratum+tcp://grin29.f2pool.com:13654 -u username.worker:passwd
- **btc.com**: nbminer -a cuckarood -o stratum+tcp://sz-grin.ss.btc.com:1800 -u username.worker:passwd
- **nicehash:** nbminer -a cuckarood -o nicehash+tcp://grincuckaroo29.eu.nicehash.com:3371 -u btc_address.worker

#### Grin31

- **sparkpool:** nbminer -a cuckatoo -o stratum+tcp://grin.sparkpool.com:66667-u 123@qq.com/worker
- **f2pool:** nbminer -a cuckatoo -o stratum+tcp://grin31.f2pool.com:13654 -u username.worker:passwd
- **btc.com**: nbminer -a cuckatoo -o stratum+tcp://sz-grin.ss.btc.com:1800 -u username.worker:passwd
- **nicehash:** nbminer -a cuckatoo -o nicehash+tcp://grincuckatoo31.eu.nicehash.com:3372 -u btc_address.worker

#### AE

- **f2pool**: nbminer -a cuckoo_ae -o stratum+tcp://ae.f2pool.com:7898 -u ak_xxxxxxx.worker:passwd
- **beepool**: nbminer -a cuckoo_ae -o stratum+tcp://ae-pool.beepool.org:9505 -u ak_xxxx.worker:passwd
- **uupool**: nbminer -a cuckoo_ae -o stratum+tcp://ae.uupool.cn:6210 -u ak_xxxxxx.worker:passwd
- **nicehash**: nbminer -a cuckoo_ae -o nicehash+tcp://cuckoocycle.eu.nicehash.com:3376 -u btc_address.test

#### SWAP

- **luckypool:** nbminer -a cuckaroo_swap -o stratum+tcp://swap2.luckypool.io:4466 -u wallet_address.test
- **herominers**: nbminer -a cuckaroo_swap -o stratum+tcp://swap.herominers.com:10441 -u wallet_address.test
- **herominers solo**: nbminer -a cuckaroo_swap -o stratum+tcp://swap.herominers.com:10441 -u solo:wallet_address.test:arbitrary

#### SERO

- **beepool**: nbminer -a progpow_sero -o stratum+tcp://sero-pool.beepool.org:9515 -u wallet_address.worker:pswd
- **f2pool**: nbminer -a progpow_sero -o stratum+tcp//sero.f2pool.com:4200 -u wallet_address.worker:pswd

#### SIPC

- **simpool:** nbminer -a sipc -o stratum+tcp://sipc.simpool.vip:8801 -u username.worker:passwd
- **matpool**: nbminer -a sipc -o stratum+tcp://sipc.matpool.io:11100 -u username.worker:passwd

#### CKB

- **sparkpool**: nbminer -a eaglesong -o stratum+tcp://ckb.sparkpool.com:8888 -u user.worker:passwd
- **beepool**: nbminer -a eaglesong -o stratum+tcp://ckb-pool.beepool.org:9550 -u email/worker:passwd
- **uupool**: nbminer -a eaglesong -o stratum+tcp://ckb.uupool.cn:10861 -u user.worker:passwd
- **f2pool**: nbminer -a eaglesong -o stratum+tcp://ckb.f2pool.com:4300 -u wallet.worker:passwd

#### CKB+ETH

- **sparkpool**: nbminer -a eaglesong_ethash -o stratum+tcp://ckb.sparkpool.com:8888 -u user.worker:passwd -do stratum+tcp://cn.sparkpool.com:3333 -du wallet.worker:passwd
- **beepool**: nbminer -a eaglesong_ethash -o stratum+tcp://ckb-pool.beepool.org:9550 -u email/worker:passwd -do stratum+tcp://eth-pool.beepool.org:9530 -du wallet.worker:passwd
- **uupool**: nbminer -a eaglesong_ethash -o stratum+tcp://ckb.uupool.cn:10861 -u user.worker:passwd      -do stratum+tcp://eth.uupool.cn:8008 -du wallet.worker:passwd
- **f2pool**: nbminer -a eaglesong_ethash -o stratum+tcp://ckb.f2pool.com:4300 -u wallet.worker:passwd     -do stratum+tcp://eth.f2pool.com:8008 -du wallet.worker:passwd

#### BFC

- **uupool**: nbminer -a bfc -o stratum+tcp://bfc.uupool.cn:12210 -u username.worker
- **bfcpool**: nbminer -a bfc -o stratum+tcp://ss.bfcpool.com:3333 -u wallet.worker

#### HNS

- **f2pool**: nbminer -a hns -o stratum+tcp://hns.f2pool.com:6000 -u wallet.worker
- **6block**: nbminer -a hns -o stratum+tcp://handshake.6block.com:7701 -u username.worker

#### HNS+ETH:

- **f2pool**: nbminer -a hns_ethash -o stratum+tcp://hns.f2pool.com:6000 -u wallet.worker -do stratum+tcp://eth.f2pool.com:8008 -du wallet.worker

## CMD options：

**nbminer -a algo -o protocol+socket_type://pool_host:pool_port -u wallet_address.worker:passwd**

  * -h, --help    Displays this help.
  * -v, --version    Displays version information.
  * -c, --config \<config file path>    Use json format config file rather than cmd line options.
  * -a, --algo \<algo>    Select mining algorithm
  * --api  \<host:port>    The endpoint for serving REST API.
  * -o, --url \<url>    Mining pool url.
  * -u, --user \<user>    User used in Mining pool, wallet address or username.
      * Format: [username|wallet].workername:password
  * -o1, --url1 \<url> url for backup mining pool 1.
  * -u1, --user1 \<user> username for backup mining pool 1.
  * -o2, --url2 \<url> url for backup mining pool 2.
* -u2, --user2 \<user> username for backup mining pool 2.
* -di, --secondary-intensity \<intensity>    The relative intensity when dual mining.
* -do, --secondary-url \<url>    ETH mining pool when dual mining.
* -du, --secondary-user \<user>    ETH username when dual mining.
* -do1, --secondary-url1 \<url>    Backup 1 ETH mining pool when dual mining.
* -du1, --secondary-user1 \<user>    Backup 1 ETH username when dual mining.
* -do2, --secondary-url2 \<url>    Backup 2 ETH mining pool when dual mining.
* -du2, --secondary-user2 \<user>    Backup 2 ETH username when dual mining.
* -d, --devices \<devices>    Specify GPU list to use. Format: "-d 0,1,2,3" to use first 4 GPU.
* -i, --intensity \<intensities>    Comma-separated list of intensities (1 -100).
* --strict-ssl    Check validity of certificate when use SSL connection.
* --cuckoo-intensity \<intensity>    Set intensity of cuckoo, cuckaroo, cuckatoo, [1, 12]. Smaller value means higher CPU usage to gain more hashrate. Set to 0 means autumatically adapt. Default: 0.
* --cuckatoo-power-optimize    Set this option to reduce the range of power consumed by rig when minining with algo cuckatoo. This feature can reduce the chance of power supply shutdown caused by overpowered. Warning: Setting this option may cause drop on minining performance.
* --temperature-limit \<temp-limit>    Set temperature limit of GPU, if exceeds, stop GPU for 10 seconds and continue.
* --log    Generate log file named `logs/log_<timestamp>.txt`.
* --log-file \<filename>    Generate custom log file. Note: This option will override `--log`.
* --no-nvml    Do not query cuda device health status.
* --fidelity-timeframe \<timeframe>    Set timeframe for the calculation of fidelity, unit in hour. Default: 24.
* --long-format    Use 'yyyy-MM-dd HH:mm:ss,zzz' for log time format.
* --device-info    Print device cuda information.
* --fee \<fee>    Change devfee in percentage, [0-5]. Set to '0' to turn off devfee with lower hashrate. Otherwise, devfee = max(set_value, def_value).
* --generate-config \<filename>    Generate a sample config json file.
* --no-watchdog    Disable watchdog process.
* --platform \<platform>    Choose platform，0: NVIDIA+AMD (default), 1: NVIDIA only, 2: AMD only
* --coin \<coin>    Set coin for ethash algo. E.g, eth, etc

## API Reference

### Web Monitor

Open http://api_host:port/ in your browser to use web monitor.

### Request

GET http://api_host:port/api/v1/status

### Response

``` json
{
    "miner": {
        "devices": [{
            "core_clock": 1556,
            "core_utilization": 100,
            "fan": 36,
            "hashrate": 1499,
            "hashrate2": "23.0 M",
            "hashrate_raw": 1499,
            "hashrate2_raw": 23030000,
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
        "total_hashrate_raw": 2989,
      	"total_hashrate2": "48.3 M",
        "total_hashrate2_raw": 48308746, 
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
        "user": "bmxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.test",
        "difficulty": "0003ffff",
        "latency": 65
    },
    "version": "v10.0"
}
```

## Change Log

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
