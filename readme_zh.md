![](/logo.png)

# NBMiner

用于Nvidia显卡的`Bytom(比原链)`、`Ethereum(以太坊)` 、`Grin`、`AE`、`SWAP(XWP)`挖矿软件。

## 下载地址

[从这里下载](https://github.com/NebuTech/BTMiner_NebuTech/releases)

## 社区支持

官方QQ群：795224121

## 参考算力（默认频率）

| 算法             |  币种   | P106-100  |  P104-8G   |  1070ti  |  1080ti  |   2080   |
| :--------------- | :-----: | :-------: | :--------: | :------: | :------: | :------: |
| tensority        |   BTM   |   1,900   |    3000    |  3,400   |  5,000   |  11,500  |
| ethash           |   ETH   |   21.2M   |   34.5M    |  26.9M   |   46M    |   35M    |
| tensority_ethash | BTM+ETH | 950+15.5M | 1600+26.5M | 1350+22M | 2450+40M | 7000+28M |
| cuckaroo         | GRIN29  |    3.4    |    5.5     |   5.15   |   7.9    |   7.75   |
| cuckatoo         | GRIN31  |     -     |    0.89    |   0.94   |   1.56   |   1.65   |
| cuckoo_ae        |   AE    |   3.35    |    5.45    |   5.1    |   7.7    |   8.6    |
| cuckaroo_swap    |  SWAP   |    3.4    |    5.5     |   5.15   |   7.8    |   7.75   |

## 功能特点

- 支持Windows和Linux
- 支持备用矿池的设置
- 支持SSL方式连接矿池
- 开发手续费:
  - tensority_ethash 3%
  - tensority(Pascal) 2%, tensority(Turing) 3%
  - ethash 0.65%
  - cuckaroo & cuckatoo & cuckoo_ae & cuckaroo_swap 2%

## 配置需求

- **NVIDIA显卡驱动版本，大于等于377**
- 显卡参数需求:

|       算法       |  币种   | Compute Capability | 显存 (Win7 & Linux) | 显存 (Win10) |
| :--------------: | :-----: | :----------------: | :-----------------: | :----------: |
|    tensority     |   BTM   |   6.1, 7.0, 7.5    |         1GB         |     1GB      |
|      ethash      |   ETH   | 6.0, 6.1, 7.0, 7.5 |         4GB         |     4GB      |
| tensority_ethash | BTM+ETH |   6.1, 7.0, 7.5    |         4GB         |     4GB      |
|     cuckaroo     | GRIN29  | 6.0, 6.1, 7.0, 7.5 |         5GB         |     6GB      |
|     cuckatoo     | GRIN31  | 6.0, 6.1, 7.0, 7.5 |         8GB         |     10GB     |
|    cuckoo_ae     |   AE    | 6.0, 6.1, 7.0, 7.5 |         5GB         |     6GB      |
|  cuckaroo_swap   |  SWAP   | 6.0, 6.1, 7.0, 7.5 |         5GB         |     6GB      |

- \* Compute Capability 查询参考链接: [维基百科](<https://en.wikipedia.org/wiki/CUDA#GPUs_supported>)

## 使用样例

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
- **nicehash**: nbminer -a cuckoo_ae -o stratum+tcp://cuckoocycle.eu.nicehash.com:3376 -u btc_address.test

#### SWAP

- **luckypool:** -a cuckaroo_swap -o stratum+tcp://swap2.luckypool.io:4466 -u wallet_address.test
- **herominers**: -a cuckaroo_swap -o stratum+tcp://swap.herominers.com:10441 -u wallet_address.test

## 命令行参数

**nbminer -a algo -o protocol+socket_type://pool_host:pool:port -u wallet_address.worker:passwd**

- -?, -h, --help    显示帮助信息.
- -v, --version    显示版本号.
- -c, --config \<config file path>    通过json格式配置文件启动挖矿程序.
- -a, --algo \<algo>    选择挖矿算法
  - BTM: tensority
  - ETH: ethash
  - BTM+ETH: tensority_ethash
  - Grin29: cuckaroo
  - Grin31: cuckatoo
  - AE: cuckoo_ae
  - SWAP: cuckaroo_swap
- --api \<host:port>    REST API监听端口.
- -o, --url \<url>    矿池地址.
  - BTM: stratum+tcp://btm.f2pool.com:9221
  - BTM with SSL: stratum+ssl://btm.f2pool.com:9443
  - ETH: ethproxy+tcp://eth.f2pool.com:8008
  - ETH NiceHash: ethnh+tcp://daggerhashimoto.eu.nicehash.com:3353
- -u, --user \<user>    挖矿使用的用户名或钱包地址.
  - 格式：[用户名|钱包地址].矿机名:密码
  - 举例：bmxxxxxx.worker       mypc.worker:password
- -o1, --url1 \<url> 备用矿池1的URL
- -u1, --user1 \<user> 备用矿池1的用户名
- -o2, --url2 \<url> 备用矿池2的URL
- -u2, --user2 \<user> 备用矿池2的用户名
- -di, --secondary-intensity \<intensity>    双挖时ETH的相对挖矿强度，默认16，建议在8-24之间调整
- -do, --secondary-url \<url>    双挖时ETH的矿池地址
- -du, --secondary-user \<user>    双挖时ETH的用户名
- -do1, --secondary-url \<url>    双挖备用矿池1的矿池地址
- -du1, --secondary-user \<user>    双挖备用矿池1的用户名
- -do2, --secondary-url \<url>    双挖备用矿池2的矿池地址
- -du2, --secondary-user \<user>    双挖备用矿池2的用户名
- -d, --devices \<devices>    指定使用哪些显卡来挖矿. 比如: "-d 0,1,2,3" 使用前4个显卡.
- --strict-ssl    使用SSL连接时验证矿池证书
- --cuckoo-intensity \<intensity>    设置挖Grin时的CPU负载，取值范围[1,12]，值越小挖矿算力越高，相对应的CPU负载也会更高。设置为0软件从1开始自适应调整。默认为0
- --cuckatoo-power-optimize    减小多卡矿机挖Grin31的总功耗波动，避免电源过载关机（设置该选项可能导致算力略微降低，请测试后谨慎使用）
- --log    生成日志文件，文件名为 `log_<时间戳>.txt`.
- --long-format    使用更长的日期时间格式
- --device-info    打印显卡的CUDA信息.

## API查询接口

### 网页监控

在浏览器中打开 http://api_host:port/ 启动网页监控.

`注：双挖时的网页监控暂时不完善。`

### 请求

GET http://api_host:port/api/v1/status

### 返回

```json
{
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
        "user": "bmxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.test",
        "difficulty": "0003ffff",
        "latency": 65
    },
    "version": "v10.0"
}
```

## FAQ

#### BTM+ETH双挖时如何调整强度？

- 合适的双挖强度取决于 `核心算力/显存带宽` 这个比例。
- 显存带宽占比较低的卡，如1070ti，可以适当降低双挖强度。反之如1060等卡，可以尝试增大双挖强度。
- 显存带宽占比会随着核心和显存超频数值不同而变化。
- 用户需根据卡的型号、超频、电费、当前币价等综合考虑需要采用的双挖强度。

#### 为什么我的矿池算力比本地算力低?

- `矿池的显示算力` = `本地实际算力` x (`1.0` - `手续费比例0.03` - `本地跳过提交的过期share率`) x (`1.0` - `矿池过期拒绝率` ± `误差率`)
- `本地实际算力`：挖矿程序中显示的`Hashrate`
- `本地跳过提交的过期share率`：源于挖矿程序中对`nonce`值计算采用批处理，若在批处理任务计算完成后，有可以提交的share，但此时矿池已经下发新的任务（`New Job`），则会跳过该过期share的提交（`Skip expired submit`）,即使提交到矿池也会被拒绝掉（`reject`）。跳过的share数量占全部share的比例即为本地跳过提交的过期share率。
- `矿池的过期拒绝率`：从挖矿程序发现share向矿池提交，到矿池验证完成这段时间内，若矿池任务有更新，会导致本次提交的share过期被拒绝。从其产生的原因看，若要改善矿池的过期拒绝率，需用户优化网络部署，减小矿机到矿池之间的网络延迟；同时矿池也需要尽量快的做nonce值的验证。
- `误差率`：矿池的显示算力，来源于矿池根据其设定的挖矿难度以及用户矿机提交的有效share数推算而得。而挖矿过程中，发现有效`nonce`获得share在短期内有运气成分，造成误差（偏高偏低都有可能），理论上挖矿时间越长误差率越低。所以对比矿池算力和本地算力应采用`矿池24小时的平均算力`来减小运气因素导致的差别。

#### 为什么会出现CUDA错误导致内核重启?

- 当核心超频过度，或者显卡本身的核心体质不好时，会因为显卡内部计算错误，导致出现各种的CUDA错误。此时应该尝试 检查转接板连接稳定性、降低核心频率、降低功耗，再做尝试。

## 修改记录

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