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
- **nicehash:** nbminer -a ethash -o ethnh+tcp://daggerhashimoto.eu.nicehash.com:3353 -u btc_address.worker

#### BTM+ETH

- **f2pool:** nbminer -a tensority_ethash -o stratum+tcp://btm.f2pool.com:9221 -u btm_address.btm_worker -do ethproxy+tcp://eth.f2pool.com:8008 -du eth_address.eth_worker

#### Grin29

- **sparkpool:** nbminer -a cuckaroo -o stratum+tcp://grin.sparkpool.com:6666 -u 123@qq.com/worker
- **f2pool:** nbminer -a cuckaroo -o stratum+tcp://grin29.f2pool.com:13654 -u username.worker:passwd
- **btc.com**: nbminer -a cuckaroo -o stratum+tcp://sz-grin.ss.btc.com:1800 -u username.worker:passwd
- **nicehash:** nbminer -a cuckaroo -o stratum+tcp://grincuckaroo29.eu.nicehash.com:3371 -u btc_address.worker

#### Grin31

- **sparkpool:** nbminer -a cuckatoo -o stratum+tcp://grin.sparkpool.com:66667-u 123@qq.com/worker
- **f2pool:** nbminer -a cuckatoo -o stratum+tcp://grin31.f2pool.com:13654 -u username.worker:passwd
- **btc.com**: nbminer -a cuckatoo -o stratum+tcp://sz-grin.ss.btc.com:1800 -u username.worker:passwd
- **nicehash:** nbminer -a cuckatoo -o stratum+tcp://grincuckaroo31.eu.nicehash.com:3372 -u btc_address.worker

#### AE

- **f2pool**: nbminer -a cuckoo_ae -o stratum+tcp://ae.f2pool.com:7898 -u ak_xxxxxxx.worker:passwd
- **beepool**: nbminer -a cuckoo_ae -o stratum+tcp://ae-pool.beepool.org:9505 -u ak_xxxx.worker:passwd
- **uupool**: nbminer -a cuckoo_ae -o stratum+tcp://ae.uupool.cn:6210 -u ak_xxxxxx.worker:passwd

## CMD options：

**Typical usage** ：

- BTM: nbminer -a tensority -o stratum+tcp://btm.f2pool.com:9221 -u bm1xxxxxxxxxxxx.worker
- ETH: nbminer -a ethash -o **ethproxy**+tcp://eth.f2pool.com:8008 -u 0xxxxxxxxxx.worker
- BTM+ETH: nbminer -a tensority_ethash -o stratum+tcp://btm.f2pool.com:9221 -u btm_wallet_address.worker -do ethproxy+tcp://eth.f2pool.com:8008 -du 0x_eth_wallet_address.worker
- Grin29: nbminer -a cuckaroo -o stratum+tcp://grin.sparkpool.com:6666 -u username@email.com/rig
- Grin31: nbminer -a cuckatoo -o stratum+tcp://grin.sparkpool.com:6667 -u username@email.com/rig

Options：

  * -h, --help    Displays this help.
  * -v, --version    Displays version information.
  * -c, --config \<config file path>    Use json format config file rather than cmd line options.
  * -a, --algo \<algo>    Select mining algorithm
        * BTM: tensority
        * ETH: ethash
        * BTM+ETH: tensority_ethash
        * Grin29: cuckaroo
        * Grin31: cuckatoo
        * AE: cuckoo_ae
  * --api  \<host:port>    The endpoint for serving REST API.
  * -o, --url \<url>    Mining pool url.
    - BTM: stratum+tcp://btm.f2pool.com:9221
    - BTM with SSL: stratum+ssl://btm.f2pool.com:9443
    - ETH: ethproxy+tcp://eth.f2pool.com:8008
    - ETH with NiceHash: ethnh+tcp://daggerhashimoto.eu.nicehash.com:3353
  * -u, --user \<user>    User used in Mining pool, wallet address or username.
      * Format: [username|wallet].workername:password
      * Example: bm1xxxxxx.worker      myusername.worker:password
  * -o1, --url1 \<url> url for backup mining pool 1.
  * -u1, --user1 \<user> username for backup mining pool 1.
  * -o2, --url2 \<url> url for backup mining pool 2.
* -u2, --user2 \<user> username for backup mining pool 2.
* -di, --secondary-intensity \<intensity>    The relative intensity for ETH when dual mining. recommend: 8 - 24, default to 16.
* -do, --secondary-url \<url>    ETH mining pool when dual mining.
* -du, --secondary-user \<user>    ETH username when dual mining.
* -do1, --secondary-url1 \<url>    Backup 1 ETH mining pool when dual mining.
* -du1, --secondary-user1 \<user>    Backup 1 ETH username when dual mining.
* -do2, --secondary-url2 \<url>    Backup 2 ETH mining pool when dual mining.
* -du2, --secondary-user2 \<user>    Backup 2 ETH username when dual mining.
* -d, --devices \<devices>    Specify GPU list to use. Format: "-d 0,1,2,3" to use first 4 GPU.
* --strict-ssl    Check validity of certificate when use SSL connection.
* **--cuckoo-intensity \<intensity>    Set intensity of cuckoo, cuckaroo, cuckatoo, [1, 12]. Smaller value means higher CPU usage to gain more hashrate. Set to 0 means autumatically adapt. Default: 0.**
* --log    Generate log file named `log_<timestamp>.txt`.
* --long-format    Use 'yyyy-MM-dd HH:mm:ss,zzz' for log time format.
* --device-info    Print device cuda information.

## GPU Tuning

- **BTM + ETH:**
  - Suitable `secondary intensity` depends on the ratio of `core performance / memory bandwidth`
  - GPU with relative low memory bandwidth, eg. 1070ti, could tune down the `di`. Otherwise tune up.
  - The ratio changes with different `core`, `tdp`, `memory`  settings when overclock GPU.
- BTM:
  - Bytom mining performance depend heavily on GPU core, instead of GPU memory.
  - Miner can gain beffer hashrate if tuning down GPU memory frequency.
  - For example, using MSI Afterburner to turn down GPU memory to -500.

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