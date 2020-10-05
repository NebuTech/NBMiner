![](/logo.png)

# NBMiner

NVIDIA、AMD显卡的`ETH`, `RVN`,  `GRIN`, `BEAM`, `TRB`, `CKB`,`AE`, `BTM`, `SERO`, `HNS`, `BFC`, `SIPC`挖矿软件。

## 下载地址

[从这里下载](https://github.com/NebuTech/BTMiner_NebuTech/releases)

## 社区支持

官方QQ群：795224121

## 参考算力（默认频率）

| 算法             |  币种   |  P106-100  |  P104-8G   |   1070ti   |  1080ti  |   2080   | RX580 2048sp |
| :--------------- | :-----: | :--------: | :--------: | :--------: | :------: | :------: | :----------: |
| tensority        |   BTM   |   1,900    |    3000    |   3,400    |  5,000   |  11,500  |      X       |
| ethash           |   ETH   |   21.2M    |   34.5M    |   26.9M    |   46M    |  35.5M   |     24M      |
| tensority_ethash | BTM+ETH | 950+15.5M  | 1600+26.5M |  1350+22M  | 2450+40M | 7000+28M |      X       |
| cuckaroo         | GRIN29  |    3.45    |    5.6     |    5.25    |   8.1    |   8.9    |      X       |
| cuckarood        | GRIN29  |    3.45    |    5.6     |    5.25    |   8.1    |   9.1    |      X       |
| cuckatoo         | GRIN31  |     X      |    0.89    |    0.94    |   1.56   |   1.65   |      X       |
| cuckatoo32       | GRIN32  |   0.215    |    0.38    |    0.41    |   0.63   |   0.65   |      X       |
| cuckoo_ae        |   AE    |    3.35    |    5.5     |    5.15    |   7.9    |   8.75   |      X       |
| cuckaroo_swap    |  SWAP   |    3.45    |    5.6     |    5.25    |   8.1    |   8.9    |      X       |
| progpow_sero     |  SERO   |   10.3M    |   17.5M    |   13.3M    |  22.5M   |  25.8M   |     10M      |
| sipc             |  SIPC   |    600k    |    940k    |    780k    |  1170k   |  1050k   |      X       |
| eaglesong        |   CKB   |    430M    |    640M    |    740M    |  1150M   |  1160M   |     350M     |
| eaglesong_ethash | CKB+ETH | 203M+20.5M |  275M+34M  | 415M+26.5M | 600M+44M | 790M+36M |   200M+22M   |
| bfc              |   BFC   |     80     |    130     |    120     |   190    |   210    |      X       |
| hns              |   HNS   |    170M    |    255M    |    300M    |   455M   |   425M   |     145M     |
| hns_ethash       | HNS+ETH |  76M+19M   |  120M+30M  | 158M+26.2M | 176M+44M | 305M+34M |  68M+22.5M   |
| trb              |   TRB   |    280M    |    435M    |    510M    |   750M   |   880M   |      X       |
| trb_ethash       | TRB+ETH | 122M+20.3M |  170M+34M  | 240M+26.7M | 315M+45M |    -     |      X       |
| kawpow           |   RVN   |   10.3M    |   17.5M    |   13.3M    |  22.5M   |  25.8M   |     11M      |
| beamv3           |  BEAM   |    12.5    |    19.6    |    18.6    |    26    |   30.5   |      X       |

## 功能特点

- 支持Windows和Linux
- 支持备用矿池的设置
- 支持SSL方式连接矿池
- 开发手续费:
  - tensority(Pascal) 2%, tensority(Turing) 3%, tensority_ethash 3%
  - ethash 1%
  - cuckaroo & cuckarood & cuckatoo & cuckatoo32 & cuckoo_ae & cuckaroo_swap 2%
  - progpow_sero 2%
  - sipc 2%
  - eaglesong 2%, eaglesong_ethash 3%
  - bfc 3%
  - hns 2%, hns_ethash 3%
  - trb 2%, trb_ethash 3%
  - kawpow 2%
  - beamv3 2%

## 配置需求

- **NVIDIA显卡驱动版本，大于等于377**
- 显卡参数需求:

| 算法             |  币种   | Compute Capability | 显存 (Win7 & Linux) | 显存 (Win10) |
| :--------------- | :-----: | :----------------: | :-----------------: | :----------: |
| tensority        |   BTM   |   6.1, 7.0, 7.5    |         1GB         |     1GB      |
| ethash           |   ETH   | 6.0, 6.1, 7.0, 7.5 |         4GB         |     4GB      |
| tensority_ethash | BTM+ETH |   6.1, 7.0, 7.5    |         4GB         |     4GB      |
| cuckaroo(d)      | GRIN29  | 6.0, 6.1, 7.0, 7.5 |         5GB         |     6GB      |
| cuckatoo         | GRIN31  | 6.0, 6.1, 7.0, 7.5 |         8GB         |     10GB     |
| cuckatoo32 | GRIN32 | 6.0, 6.1, 7.0, 7.5 | 8GB | 10GB |
| cuckoo_ae        |   AE    | 6.0, 6.1, 7.0, 7.5 |         5GB         |     6GB      |
| cuckaroo_swap    |  SWAP   | 6.0, 6.1, 7.0, 7.5 |         5GB         |     6GB      |
| progpow_sero     |  SERO   |     6.0 - 7.5      |         2GB         |     2GB      |
| sipc             |  SIPC   | 6.0, 6.1, 7.0, 7.5 |         1GB         |     1GB      |
| eaglesong        |   CKB   | 6.0, 6.1, 7.0, 7.5 |        0.1GB        |    0.1GB     |
| eaglesong_ethash | CKB+ETH | 6.0, 6.1, 7.0, 7.5 |         4GB         |     4GB      |
| bfc              |   BFC   | 6.0, 6.1, 7.0, 7.5 |         5GB         |     6GB      |
| hns              |   HNS   | 6.0, 6.1, 7.0, 7.5 |         0.1GB         |      0.1GB  |
| hns_ethash       | HNS+ETH | 6.0, 6.1, 7.0, 7.5 |          4GB          |      4GB       |
| trb              |   TRB   | 6.0, 6.1, 7.0, 7.5 |         0.1GB         |     0.1GB      |
| trb_ethash       | TRB+ETH | 6.0, 6.1, 7.0, 7.5 |          4GB          |      4GB       |
| kawpow | RVN | 6.0, 6.1, 7.0, 7.5 | 3GB | 3GB |

- \* Compute Capability 查询参考链接: [维基百科](<https://en.wikipedia.org/wiki/CUDA#GPUs_supported>)

## 使用样例

#### BTM

- **f2pool:** nbminer -a tensority -o stratum+tcp://btm.f2pool.com:9221 -u bm1xxxxxxxxxx.worker
- **antpool:** nbminer -a tensority -o stratum+tcp://stratum-btm.antpool.com:6666 -u username.worker
- **matpool.io:** nbminer -a tensority -o stratum+tcp://btm.matpool.io:8118 -u bm1xxxxxxxxxxx.worker

#### ETH

- **ethermine:** nbminer -a ethash -o ethproxy+tcp://asia1.ethermine.org:4444 -u wallet.worker
- **sparkpool:** nbminer -a ethash -o ethproxy+tcp://cn.sparkpool.com:3333 -u wallet.worker
- **f2pool:** nbminer -a ethash -o ethproxy+tcp://eth.f2pool.com:8008 -u wallet.worker
- **nanopool:** nbminer -a ethash -o ethproxy+tcp://eth-asia1.nanopool.org:9999 -u wallet.worker
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

#### Grin32

- **sparkpool**: nbminer -a cuckatoo32 -o stratum+tcp://grin.sparkpool.com:6665 -u 123@qq.com/worker
- **f2pool:** nbminer -a cuckatoo32 -o stratum+tcp://grin32.f2pool.com:13654 -u username.worker:passwd
- **nicehash:** nbminer -a cuckatoo32 -o nicehash+tcp://grincuckatoo32.hk.nicehash.com:3383 -u btc_address.worker

#### AE

- **f2pool**: nbminer -a cuckoo_ae -o stratum+tcp://ae.f2pool.com:7898 -u ak_xxxxxxx.worker:passwd
- **beepool**: nbminer -a cuckoo_ae -o stratum+tcp://ae-pool.beepool.org:9505 -u ak_xxxx.worker:passwd
- **uupool**: nbminer -a cuckoo_ae -o stratum+tcp://ae.uupool.cn:6210 -u ak_xxxxxx.worker:passwd
- **nicehash**: nbminer -a cuckoo_ae -o nicehash+tcp://cuckoocycle.eu.nicehash.com:3376 -u btc_address.worker

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

#### HNS+ETH

- **f2pool**: nbminer -a hns_ethash -o stratum+tcp://hns.f2pool.com:6000 -u wallet.worker -do stratum+tcp://eth.f2pool.com:8008 -du wallet.worker

#### TRB

- **uupool**: nbminer -a trb -o stratum+tcp://trb.uupool.cn:11002 -u wallet.worker
- **hashpool**: nbminer -a trb -o stratum+tcp://pplns.trb.stratum.hashpool.com:8208 -u wallet.worker

#### TRB+ETH

- **uupool**: nbminer -a trb_ethash -o stratum+tcp://trb.uupool.cn:11002 -u wallet.worker -do stratum+tcp://eth.uupool.cn:8008 -du wallet.worker

#### RVN

- **beepool**: nbminer -a kawpow -o  stratum+tcp://rvn-pool.beepool.org:9531 -u wallet.worker:passwd
- **f2pool**: nbminer -a kawpow -o  stratum+tcp://raven.f2pool.com:3636 -u wallet.worker:passwd
- **minermore**: nbminer -a kawpow -o stratum+tcp://us.rvn.minermore.com:4501 -u wallet.worker:paswd
- **bsod**: nbminer -a kawpow -o stratum+tcp://pool.bsod.pw:2640 -u wallet.worker:passwd
- **woolypooly**: nbminer -a kawpow -o stratum+tcp://rvn.woolypooly.com:55555 -u wallet.worker:passwd 

#### BEAM

- **sparkpool**: nbminer -a beamv3 -o stratum+ssl://beam.sparkpool.com:2222 -u wallet.worker:passwd
- **leafpool**: nbminer -a beamv3 -o stratum+ssl://beam-eu.leafpool.com:3333 -u wallet.worker:passwd
- **nicehash**: nbminer -a beamv3 -o stratum+tcp://beamv3.eu.nicehash.com:3387 -u btc_address.worker

## 命令行参数

**nbminer -a algo -o 协议+连接类型://矿池地址:矿池端口 -u 钱包地址或用户名.矿工名:密码可选**

- -?, -h, --help    显示帮助信息.
- -v, --version    显示版本号.
- -c, --config \<config file path>    通过json格式配置文件启动挖矿程序.
- -a, --algo \<algo>    选择挖矿算法
- --api \<host:port>    REST API监听端口.
- -o, --url \<url>    矿池地址.
- -u, --user \<user>    挖矿使用的用户名或钱包地址.
  - 格式：[用户名|钱包地址].矿机名:密码
- -o1, --url1 \<url> 备用矿池1的URL
- -u1, --user1 \<user> 备用矿池1的用户名
- -o2, --url2 \<url> 备用矿池2的URL
- -u2, --user2 \<user> 备用矿池2的用户名
- -di, --secondary-intensity \<intensity>    双挖时相对挖矿强度
- -do, --secondary-url \<url>    双挖时ETH的矿池地址
- -du, --secondary-user \<user>    双挖时ETH的用户名
- -do1, --secondary-url \<url>    双挖备用矿池1的矿池地址
- -du1, --secondary-user \<user>    双挖备用矿池1的用户名
- -do2, --secondary-url \<url>    双挖备用矿池2的矿池地址
- -du2, --secondary-user \<user>    双挖备用矿池2的用户名
- -d, --devices \<devices>    指定使用哪些显卡来挖矿. 比如: "-d 0,1,2,3" 使用前4个显卡.
- -i, --intensity \<intensities>    GPU使用强度列表 (1 -100)，默认100.
- --strict-ssl    使用SSL连接时验证矿池证书
- --proxy    使用Socks5代理连接矿池，例如: 127.0.0.1:1080
- --cuckoo-intensity \<intensity>    设置挖Grin时的CPU负载，取值范围[1,12]，值越小挖矿算力越高，相对应的CPU负载也会更高。设置为0软件从1开始自适应调整。默认为0
- --cuckatoo-power-optimize    减小多卡矿机挖Grin31的总功耗波动，避免电源过载关机（设置该选项可能导致算力略微降低，请测试后谨慎使用）
- --temperature-limit \<temp-limit>    设置显卡温度上限，一旦超过，停止挖矿10s后继续
- --log    生成日志文件，文件名为 `log_<时间戳>.txt`.
- --log-file \<filename>    自定义日志文件名，该选项将覆盖`--log`.
- --no-nvml    不周期性地查询GPU的温度功耗等状态.
- --fidelity-timeframe \<timeframe>    设置保真度计算的时间范围，以小时为单位，默认24.
- --long-format    使用更长的日期时间格式
- --verbose    在日志中输出与矿池的通信数据
- --device-info    打印显卡的CUDA信息.
- --generate-config \<filename>    生成一个样例配置文件.
- --no-watchdog    不启动看门狗进程.
- --platform \<platform>    选择平台，0: NVIDIA+AMD (默认), 1: 只启用NVIDIA, 2: 只启用AMD
- --coin \<coin>    设置ethash算法的币种，如 eth、etc
- **--mt, --memory-tweak \<mode>    Nvidia GDDR5 & GDDR5X 显卡时序优，取值 [1-6]，值越大算力越高。可以通过逗号分隔的列表针对每张卡单独设置，如：`-mt 4,5,6` 分别将0,1,2号卡的mt值设为4,5,6。可能需要提高功耗限制以达到更高的算力。如果你的矿机温度较高，可能会出现更高的拒绝率，此时可以降低数值再尝试。windows下使用该命令需使用`--drver`参数进行驱动安装，或使用管理员权限开启挖矿，会自动安装。linux下使用，需加`sudo`使用管理员权限运行。使用该命令后，1080、1080ti挖ETH不再需要OhGodAnETHlargementPill**
- **--driver \<action>    windows独有选项，如果要使用`-mt`，可使用该选项手动安装和卸载驱动。管理员权限运行`nbminer.exe --driver install` 安装驱动，卸载使用`nbminer.exe --driver uninstall`**

## API查询接口

### 网页监控

在浏览器中打开 http://api_host:port/ 启动网页监控.

### 请求

GET http://api_host:port/api/v1/status

### 返回

```json
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

## 修改记录

#### v32.1(2020-10-05)

- `bug修复`: 修复在部分AMD矿机上设备初始化失败的bug

#### v32.0(2020-09-30)

- `新增算法`: `beamv3` 用于`BEAM`挖矿，支持Nvidia 3GB+ 显卡
- `新增算法`: `cuckatoo32` 新增对Nvidia 6GB显卡的支持
- `优化`: `ethash` 对于AMD RX 4xx、5xx、Vega 系列8GB+显卡优化
- `特性`: `ethash`支持挖矿时间到epoch 800

#### v31.1(2020-06-24)

- `新增算法`: `cuckatoo32` 用于Grin32，支持Nvidia 8G及以上显卡
- `kawpow`: 增加对`NiceHash`的`extranonce.subscribe`协议支持

#### v30.2(2020-05-05)

- `windows`: 若设置了`--memory-tweak`参数，自动尝试安装驱动
- `windows`: 修复在部分windows系统上无法安装时序驱动的问题
- `kawpow`: 修复在部分矿池出现`dupulicate share`的情况

#### v30.1(2020-05-03)

- 缩短 `ethash` & `kawpow`算法的启动时间
- 修复 30.0 版本有小概率出现`invalid kernel image` 崩溃的情况
- 当`-mt`设置为 0 的时候，对应显卡不启用时序调整功能
- 在启动时打印系统信息

#### v30.0(2020-04-30)

- 新增`--memory-tweak`选项，用于优化Nvidia GD5和GD5X的显卡时序。详细说明见readme_zh.md
- 新增`--verbose`选项，可打印与矿池的通信数据
- 新增`--proxy` 选项，用户可设置通过socks5代理与矿池进行连接
- 在日志和api中新增单个GPU的share数量统计
- 细节修复和改进

#### v29.1(2020-04-09)

- 修复kawpow在RDNA 系列显卡上算力过低的bug
- 提升kawpow在AMD显卡上的算力

#### v29.0(2020-04-03)

- 对RVN即将分叉算法kawpow的支持，Nvidia & AMD

#### v28.1(2020-03-30)

- 添加HNS、HNS+ETH在NiceHash挖矿的支持

#### v28.0(2020-03-28)

- 新增TRB、TRB+ETH在Nvidia显卡的支持
- 细节改进和修复

#### v27.7(2020-03-15)

- 修复ETH Nicehash协议
- 修复部分情况下NVML初始化失败的问题

#### v27.6(2020-03-14)

- 提升N卡 HNS单挖、HNS+ETH双挖的算力

#### v27.5(2020-03-05)

- 修复在部分矿池双挖时ETH拒绝率、延迟率较高的问题
- 略微提升N卡双挖HNS的算力

#### v27.4(2020-02-28)

- 修复对部分AMD Vega卡的支持
- 修复在A、N卡混插下的一个可能的索引bug

#### v27.3(2020-02-27)

- 新增 HNS+ETH 双挖在AMD显卡的支持
- 提高 HNS+ETH 双挖在Nvidia显卡上的算力
- **备注**: 该版本对HNS+ETH的双挖强度参数`-di`的计算方式有所改变
  - `-di` = `HNS工作量` / `ETH工作量`
  - 例如，在默认参数工作的1070ti，`-di 5` 可以得到 26M ETH 算力和 130M HNS算力

#### v27.2(2020-02-20)

- 提高HNS在AMD显卡上的算力

#### v27.1(2020-02-19)

- 提高HNS在Nnvidia显卡上的算力
- 新增HNS在AMD显卡上的支持

#### v27.0(2020-02-18)

- 增加在NVIDIA显卡上 HNS单挖 以及 HNS_ETH 双挖的支持

#### v26.2(2019-11-21)

- 提高CKB+ETH在A卡的算力
- 修复26.1在部分AMD矿机上无法启动的bug

#### v26.1(2019-11-15)

- 新增CKB+ETH在A卡的支持
- 提高CKB在N卡上的单挖算力

#### v26.0(2019-10-11)

- 新增N卡BFC挖矿
- 修复CKB在AMD显卡上的兼容性

#### v25.5(2019-10-05)

- 修复CKB+ETH双挖异常的bug
- 修复CKB与矿池的协议兼容性

#### v25.4(2019-10-04)

- 提高CKB在NVIDIA、AMD的算力
- 提高CKB+ETH的算力
- 新增SERO在AMD卡上挖矿的支持
- 新增选项`--platform`选择启用的平台（NVIDIA或AMD）

#### v25.2(2019-09-10)

- A卡单挖CKB支持linux系统
- 修复25.1版本N卡挖矿的问题

#### v25.1(2019-09-07)

- 新增A卡单挖`CKB`

#### v25.0(2019-09-05)

- 增加对`CKB`单挖以及`CKB`+`ETH`双挖的支持
- 双挖强度参数`-di`支持逗号列表分别指定每张卡的`-di`值
- CKB+ETH双挖时，双挖强度 `-di` 根据卡不同默认4 ~ 8，取值范围 1 - 10，值越大ETH占比越高
- 对于不同卡的不同超频参数，最佳的`-di`值不同，用户需自行尝试

#### v24.4(2019-08-16)

- 修复SIPC在dxpool挖矿的支持
- **1080 & 1080ti用户应启用`OhGodAnETHlargementPill`以提高SIPC算力**

#### v24.3(2019-08-15)

- 增加对SIPC挖矿的支持
- 修复24.1，24.2版本挖SERO时CPU占用过高的问题
- 修复Grin的intensity参数

#### v24.2(2019-07-17)

- cuckaroo不再自动切换到cuckarood，挖Grin29请使用cuckarood算法
- 略微提高2060在win10下的Grin29算力
- 修复部分linux发行版启动卡住的情况
- 新增选项`--generate-config`可生成样例配置文件
- **在linux挖sero的用户，如果要关闭看门狗，注意样例脚本中的环境变量设置**

#### v24.1(2019-07-16)

- 修复10系6G及以下卡Grin29、AE算力较之前版本低的情况
- 修复20系6G卡无法在win10挖Grin29、AE的情况
- 修复部分情况下错误无法自动重启内核的问题
- 修复24.0版本无法使用config文件启动的问题
- 启动时打印的显存容量由总容量改为可用容量

#### v24.0(2019-07-15)

- 支持Grin29分叉
  - 此版本cuckaroo算法会在262080块自动切换为cuckarood算法，也可分叉后手动指定。
  - 此版本新增临时选项`-grin29-fork-height`，可通过其修改预设的`262080`高度进行自动切换测试。
- 提升Grin29、AE算力
- 新增对SERO挖矿的支持
- 新增选项-`intensity`可调节显卡挖矿强度
- 新增选项`-fidelity-timeframe`可自定义保真度计算时间范围
- 新增选项`-log-file`可指定log文件名
- 新增选项`-no-nvml`可关闭温度等显卡状态查询，
- 细节改进和修复

#### v23.3(2019-06-14)

- 修复AE在NiceHash上的挖矿
- 增加选项限制显卡温度

#### v23.2(2019-05-09)

- 提高Grin、AE算力
- 增加保真度（幸运值）显示
- 细节改进和修复

#### v22.3(2019-04-15)

- 提高Grin31在1080ti和2080ti上的算力.

#### v22.2(2019-04-15)

- 提高Grin31对Windows 8G卡的兼容性
- 默认设置Grin、AE的`--cuckoo-intensity`参数为4，降低默认情况下CPU使用

#### v22.1(2019-04-12)

- 增加对Swap（XWP）的支持
- 提高Grin29、AE的算力
- 优化Grin、AE在windows上的兼容性，算力提升明显

#### v21.4(2019-04-03)

- 提高Grin31的算力
- 提高Grin29、AE在20系列卡的算力
- 修复Grin31在win7对于 8G卡的兼容性
- 新增选项，可降低挖Grin31的总功耗波动，减少电源过载的概率
- 命令行输出增加内核挖矿时间(Up Time).

#### v21.3(2019-03-20)

- 修复可能出现的本地显示算力较低的情况
- Grin、AE在矿池连接失效时不进行GPU运算

#### v21.2(2019-03-15)

- 修复在部分正常情况下出现 `"GPU hung detected"` 异常

#### v21.1(2019-03-14)

- 提高Grin29算力
- 增加Grin、AE对20系卡的支持
- 新增GPU挂起状态检测
- 提高Grin在Nicehash上的share接受率
- 修复ETH对NiceHash的支持
- 修复备用矿池使用时的bug

#### v21.0(2019-03-06)

- 新增对AE的支持
- 提高Grin29、Grin31的算力
- 修复部分小概率出现的bug，提高程序稳定性

#### v20.0(2019-02-21)

- 新增对Grin31的支持
- 新增Grin对NiceHash的支持
- Grin新增调整CPU负载选项 --cuckoo-intensity
- 优化20系卡BTM+ETH双挖
- 修复在10和20系列卡混插平台进行BTM挖矿时，10系卡算力降低的bug
- 当用户不指定矿工名时，不再增加默认default矿工名

#### v14.0(2019-01-30)

- **针对RTX卡优化BTM，提升算力超过200%**
- 提升Grin29算力

#### v13.2(2019-01-17)

- 支持Grin在win10 1066的挖矿
- 修复对Grin Solo矿池协议的支持

#### v13.1(2019-01-15)

- 加入对Grin（Cuckaroo29）的支持
- 其他细节改进

#### v12.4(2018-01-05)

- 提高BTM+ETH双挖算力6%左右

#### v12.3(2018-12-30)

- 修复双挖时ETH一定概率出现较多拒绝share的情况

#### v12.2(2018-12-26)

- 修复双挖强度`-di`较大时，ETH延迟拒绝率较高的问题
- 完善web监控页面对双挖的显示
- 修复部分潜在的bug

#### v12.1(2018-12-24)

- 完善ETH协议对鱼池pps+模式的支持
- 新增ETH对NiceHash协议的支持（url协议头用`ethnh`）
- rest api增加双挖的算力内容(网页监控暂时还没有)
- 修复部分潜在的bug

#### v12.0(2018-12-19)

- **新增BTM+ETH双挖**
- 降低对显卡驱动版本的要求，最低可用377版本驱动
- 暂时去掉对XMR挖矿的支持
- 完善配置文件启动
- 矿池参数增加默认协议头

#### v11.0(2018-12-12)

- 大幅提升BTM算力
- 加入对ETH、XMR挖矿的支持
- 优化新任务的处理，提高矿池端实际收益
- 带颜色的日志输出
- 加入对备用矿池的支持
- BTM开发手续费降为2%

#### v10.0(2018-10-03)

- 提升算力

#### v9.0(2018-08-28)

- 提升算力30%左右
- 稳定性提升

#### v8.0(2018-08-17)

- 提升算力10%-15%
- 优化本地提交Skip率过高造成本地与矿池算力差距较大的问题，提升矿池实际算力1%-2%
- 增加矿池延迟显示
- 增加矿池难度显示
- 完善API监控页面