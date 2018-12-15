# NBMiner GPU挖矿软件

用于Nvidia显卡的`Bytom(比原链)`、`Ethereum(以太坊)`、`Monero(门罗币)`挖矿软件。

之前名为`BTMiner_NebuTech`.

## 下载地址

[从这里下载](https://github.com/NebuTech/BTMiner_NebuTech/releases)

## 功能特点

- 支持比原链（Bytom, BTM）挖矿（Tensority算法）
  - 默认频率下算力，P106达到1900H/s，1070ti达到3400H/s
  - 支持英伟达GTX 10xx，RTX 20xx系列显卡
- 支持以太坊（Ethereum, ETH）挖矿（ETHash算法）
  - 最高的矿池收益
  - 支持ethproxy协议的矿池
- 支持门罗（Monero, XMR）挖矿（CryptoNightV8算法）
- 支持Windows和Linux
- 支持备用矿池的设置
- 支持SSL方式连接矿池
- 开发手续费：BTM 2%，ETH 0.65%，XMR 0.65%

## 使用方法

- **驱动版本，Windows大于等于397, Linux大于396**
- BTM挖矿：
  - 编辑`start_btm.bat`文件，修改`-o` 参数后的矿池地址和`-u` 参数后的钱包地址或用户名。双击`start_btm.bat` 开始挖矿。
- ETH挖矿：
  - 编辑`start_eth.bat` 文件，修改`-o` 参数后的矿池地址和`-u` 参数后的钱包地址或用户名。双击`start_eth.bat` 开始挖矿。
  - 若使用1080、1080ti、1060-5X等使用GDDR5X显存的用户，在挖矿之前先用管理员权限运行`OhGodAnETHlargementPill-r2.exe` 补丁，并保持在后台运行。
- XMR挖矿：
  - 对于windows用户，由于XMR挖矿内核的特殊性，会造成GPU单次调用时间过长。在windows下会造成系统认为GPU无响应进而杀掉进程。因此需要延长系统对该判断的时间。第一次进行门罗挖矿需先运行`modify_tdr_delay.reg` ，修改注册表后重启系统。
  - 编辑`start_xmr.bat` 文件，修改`-o`后面的矿池地址和`-u`后面的钱包地址或用户名。双击`start_xmr.bat` 开始挖矿。

## 命令行参数

nbminer [参数]

**典型用法**：

- BTM: nbminer -a tensority -o stratum+tcp://btm.f2pool.com:9221 -u bm1xxxxxxxxxxxx.worker
- ETH: nbminer -a ethash -o ethproxy+tcp://eth.f2pool.com:8008 -u 0xxxxxxxxxx.worker
- XMR: nbminer -a cryptonightv8 -o -o stratum+tcp://xmr-jp1.nanopool.org:14444 -u 4xxxxxxxxx.worker

参数：

- -?, -h, --help    显示帮助信息.
- -v, --version    显示版本号.
- -c, --config \<config file path>    通过配置文件启动挖矿程序.
- -a, --algo \<algo>    选择挖矿算法（BTM用`tensority`, ETH用`ethash`, 门罗用`cryptonightv8`）
- --api \<host:port>    REST API监听端口.
- -o, --url \<url>    矿池地址.
  - BTM: stratum+tcp://btm.f2pool.com:9221
  - BTM with SSL: stratum+ssl://btm.f2pool.com:9443
  - ETH: ethproxy+tcp://eth.f2pool.com:8008
  - XMR: stratum+tcp://xmr.f2pool.com:13531
- -u, --user \<user>    挖矿使用的用户名或钱包地址.
  - 格式：[用户名|钱包地址].矿机名:密码
  - 举例：bmxxxxxx.worker       mypc.worker:password
- -o1, --url1 \<url> 备用矿池1的URL
- -u1, --user1 \<user> 备用矿池1的用户名
- -o2, --url2 \<url> 备用矿池2的URL
- -u2, --user2 \<user> 备用矿池2的用户名
- -d, --devices \<devices>    指定使用哪些显卡来挖矿. 比如: "-d 0,1,2,3" 使用前4个显卡.
- --strict-ssl    使用SSL连接时验证矿池证书
- --log    生成日志文件，文件名为 `log_<时间戳>.txt`.
- --long-format    使用更长的日期时间格式

## API查询接口

### 网页监控

在浏览器中打开 http://api_host:port/ 启动网页监控.

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

#### 为什么我的矿池算力比本地算力低?

- `矿池的显示算力` = `本地实际算力` x (`1.0` - `手续费比例0.03` - `本地跳过提交的过期share率`) x (`1.0` - `矿池过期拒绝率` ± `误差率`)
- `本地实际算力`：挖矿程序中显示的`Hashrate`
- `本地跳过提交的过期share率`：源于挖矿程序中对`nonce`值计算采用批处理，若在批处理任务计算完成后，有可以提交的share，但此时矿池已经下发新的任务（`New Job`），则会跳过该过期share的提交（`Skip expired submit`）,即使提交到矿池也会被拒绝掉（`reject`）。跳过的share数量占全部share的比例即为本地跳过提交的过期share率。
- `矿池的过期拒绝率`：从挖矿程序发现share向矿池提交，到矿池验证完成这段时间内，若矿池任务有更新，会导致本次提交的share过期被拒绝。从其产生的原因看，若要改善矿池的过期拒绝率，需用户优化网络部署，减小矿机到矿池之间的网络延迟；同时矿池也需要尽量快的做nonce值的验证。
- `误差率`：矿池的显示算力，来源于矿池根据其设定的挖矿难度以及用户矿机提交的有效share数推算而得。而挖矿过程中，发现有效`nonce`获得share在短期内有运气成分，造成误差（偏高偏低都有可能），理论上挖矿时间越长误差率越低。所以对比矿池算力和本地算力应采用`矿池24小时的平均算力`来减小运气因素导致的差别。

#### 为什么会出现CUDA错误导致内核重启?

- 驱动版本过低会导致`CUDA error: insufficient driver`，请更新驱动版本，满足[使用方法](#使用方法)部分的版本要求。
- 当核心超频过度，或者显卡本身的核心体质不好时，会因为显卡内部计算错误，导致出现各种的CUDA错误。此时应该尝试降低核心频率、降低功耗，再做尝试。

#### 显卡超频参数应如何设置才能更好的挖BTM?

- Bytom挖矿主要依靠GPU核心（相对而言，ETH挖矿则更依靠显存带宽），因此若需超频应该增大核心频率，一般建议核心+100~+200。
- 由于主要依赖核心，因此矿工在实际挖矿中可以通过将显存调整为-500，基本不会影响BTM的挖矿算力（仅供参考，以实测为准）。
- 如果限制了功耗在100%以下，此时降低显存频率甚至可以带来算力的提升（因为功耗限制，降显存频率以后可以有更多的电能共给到GPU核心）。

## 致谢

@earthGavinLee

## 修改记录

####v11.0(2018-12-12)

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
