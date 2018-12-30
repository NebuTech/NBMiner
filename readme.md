# NBMiner
Nvidia GPU Miner for `Bytom(BTM)`, `Ethereum(ETH)` mining.

Previously named `BTMiner_NebuTech`.

## 中文说明

[查看中文说明](/readme_zh.md)

## Download

[Download here](https://github.com/NebuTech/BTMiner_NebuTech/releases)

## Features：

* **Support `BTM+ETH dual mining`** , 20% more profit than single mining.
* Support Bytom (BTM) mining, tensority algorithm.
  * Hashrate under default frequency: P106  1900H/s, 1070ti  3400H/s
  * Support Nvidia 10xx & 20xx GPUs.
* Support Ethereum (ETH) mining.
  * Highest profit on mining pools.
  * Support mining pools using ethproxy protocol.
* Support Windows & Linux.
* Support backup mining pool configuration.
* Support SSL connection to mining pools.
* Dev Fee: BTM+ETH 3%, BTM 2%, ETH 0.65%

## Usage：

- **Driver version: >= 377**.
- BTM Mining:
  - Edit `start_btm.bat`, modify mining pool url after `-o` and username or wallet address after `-u`. 
- ETH Mining:
  - Edit `start_eth.bat`, modify mining pool url after `-o` and username or wallet address after `-u`. 
  - For users using 1080, 1080ti, 1060-5X cards, which equiped with GDDR5X memory, remember to start `OhGodAnETHlargementPill-r2.exe`  patch before mining and keep it running background.
- BTM+ETH Dual Mining:
  -  Edit `start_btm_eth.bat`
  -  Set mining pool for BTM after option `-o`, set username for BTM pool after option `-u`
  -  Set mining pool for ETH after option `-do`, set username for ETH pool after option `-du`
  -  There is an option `-di` (secondary-intensity) stands for the relative intensity of mining ETH.  Tuning this option to get best performance on different cards.

## CMD options：

**Typical usage** ：

- BTM: nbminer -a tensority -o stratum+tcp://btm.f2pool.com:9221 -u bm1xxxxxxxxxxxx.worker
- ETH: nbminer -a ethash -o **ethproxy**+tcp://eth.f2pool.com:8008 -u 0xxxxxxxxxx.worker
- BTM+ETH: nbminer -a tensority_ethash -o stratum+tcp://btm.f2pool.com:9221 -u btm_wallet_address.worker -do ethproxy+tcp://eth.f2pool.com:8008 -du 0x_eth_wallet_address.worker

Options：

  * -h, --help    Displays this help.
  * -v, --version    Displays version information.
  * -c, --config \<config file path>    Use json format config file rather than cmd line options.
  * -a, --algo \<algo>    Select algorithm, `tensority` for BTM, `ethash` for ETH, `cryptonightv8` for XMR.
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
* **-di, --secondary-intensity \<intensity>    The relative intensity for ETH when dual mining. recommend: 8 - 24, default to 16.**
* -do, --secondary-url \<url>    ETH mining pool when dual mining.
* -du, --secondary-user \<user>    ETH username when dual mining.
* -do1, --secondary-url1 \<url>    Backup 1 ETH mining pool when dual mining.
* -du1, --secondary-user1 \<user>    Backup 1 ETH username when dual mining.
* -do2, --secondary-url2 \<url>    Backup 2 ETH mining pool when dual mining.
* -du2, --secondary-user2 \<user>    Backup 2 ETH username when dual mining.
* -d, --devices \<devices>    Specify GPU list to use. Format: "-d 0,1,2,3" to use first 4 GPU.
* --strict-ssl    Check validity of certificate when use SSL connection.
* --log    Generate log file named `log_<timestamp>.txt`.
* --long-format    Use 'yyyy-MM-dd HH:mm:ss,zzz' for log time format.

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

## Thanks

@earthGavinLee

## Change Log

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
