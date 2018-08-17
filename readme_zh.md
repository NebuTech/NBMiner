# BTM GPU挖矿软件（BTMiner_NebuTech）

用于Nvidia显卡的`Bytom(比原链)`挖矿软件。

## 下载地址

[从这里下载](https://github.com/NebuTech/BTMiner_NebuTech/releases)

## 功能特点

- 支持Win7、Win10、Linux
- 支持标准stratum协议的矿池
- 不占用CPU和PCI-E带宽，现有6卡、8卡矿机适用
- **从v5.0开始只支持10代及以后的N卡，前代卡请使用3.3版本**
- 包含3%开发手续费，可以通过选项关闭

## 使用方法

1. **驱动版本，Windows大于等于385, Ubuntu大于384**
2. 编辑`start_cmd.bat`文件(Linux系统修改`start_cmd.sh`)，修改`-url`后面的矿池地址和`-user`后面的钱包地址或用户名。如果有密码，添加`-p`参数和密码。
3. Windows双击运行`start_cmd.bat`开始挖矿, Linux通过命令行运行`start_cmd.sh`开始挖矿。

## 参考显卡性能

- **注：以下参数均为显卡默认频率功耗下的测试数据**

| 显卡    | 参考算力（H/s） |
| ------- | --------------- |
| 1030    | 235             |
| 1050    | 410             |
| 1050Ti  | 500             |
| 1060-3G | 780             |
| 1060-6G | 850             |
| 1070    | 1250            |
| 1070Ti  | 1550            |
| 1080    | 1700            |
| 1080Ti  | 2350            |

## 命令行参数

BTMiner_NebuTech [参数]

**典型用法**：BTMiner_NebuTech -url btm.f2pool.com:9221 -user bm1xxxxxxxxxxxx.rigName

参数：

- -?, -h, --help    显示帮助信息.
- -v, --version    显示版本号.
- -c, --config \<config file path>    通过配置文件启动挖矿程序.
- --api \<host:port>    REST API监听端口.
- -B, --browser    自动打开网页监控页面。仅适用于windows。
- -o, --url \<url>    矿池地址.
- -u, --user \<user>    挖矿使用的用户名或钱包地址.
- -p, --passwd \<password>    挖矿使用的密码.
- -d, --devices \<devices>    指定使用哪些显卡来挖矿. 比如: "-d 0,1,2,3" 使用前4个显卡.
- -S, --ssl    使用SSL连接矿池（需矿池支持）
- --log    生成日志文件，文件名为 `log_<时间戳>.txt`.
- --long-format    使用更长的日期时间格式
- --no-fee    关闭开发者手续费，同时会关闭部分优化，算力有所下降。

## API查询接口

### 网页监控

在浏览器中打开 http://api_host:port/ 启动网页监控.

### 请求

GET http://api_host:port/api/v1/status

### 返回

```json
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
        "user": "bmxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.test",
        "difficulty": "0003ffff",
        "latency": 65
    },
    "version": "v8.0"
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
- 由于主要依赖核心，因此矿工在实际挖矿中可以通过将显存调整为-500，基本不会影响BTM的挖矿算力（以实测为准）。
- 如果限制了功耗在100%以下，此时降低显存频率甚至可以带来算力的提升（因为功耗限制，降显存频率以后可以有更多的电能共给到GPU核心）。

## 开发计划

- 尽量提高算力
- 不再进行GUI版本开发，推荐使用集成了我们的BTMiner，功能更加丰富的软件：[深圳矿工](http://www.szkg.top/)（WIndows）、[矿山系统](http://40451.net/)（Linux）、[MinerOS](https://www.mineros.cn/#/)（Linux）

## 致谢

@earthGavinLee

## 修改记录

#### v8.0(2018-08-17)

- 提升算力10%-15%
- 优化本地提交Skip率过高造成本地与矿池算力差距较大的问题，提升矿池实际算力1%-2%
- 增加矿池延迟显示
- 增加矿池难度显示
- 完善API监控页面

#### v7.0(2018-08-03)

- 提高20%左右算力
- 增加长日期时间格式输出的选项
- 增加日志文件输出的选项
- 取消`-M`选项
- 稳定性修复

#### v6.0(2018-07-23)

- 增加状态查询的API接口
- 增加状态监控的web页面
- 增加更多的GPU状态信息查询：功耗、核心频率、核心使用率
- 底层参数调整，部分机器2-3%的算力提升
- 运行时检查对矿池提交对应的应答数，防止矿池无响应现象出现
- 优化控制台日志输出格式

#### v5.1(2018-07-07)

* 禁用CMD快速编辑模式，防止进程被冻结
* 禁止程序崩溃时弹出windows错误报告

#### v5.0(2018-07-03)

- 大幅提高算力
- 可使用配置文件启动
- 增加使用SSL矿池连接的选项
- 增加关闭手续费的选项
- 取消CPU模式的选项
- 取消GUI壳程序（后续不在更新）

#### v3.3(2018-06-16)

- GUI界面增加配置自动保存恢复功能
- (GUI)Add auto saving config
- 修复经常崩溃的bug，提升稳定性。 
- Fix Crash, 

#### v3.0(2018-06-09)

- 大幅提升算力
- 自动优化选择上个版本的`-i`参数
- 增加`-M`选项，应对多卡时可能出现的`CUDA out of memory error`
- Windows增加图形界面壳程序，便于新手操作
- 图形界面增加公告，获取最新版本通知
- 修复已知BUG，提升稳定性。

#### v2.0(2018-06-04)

- 进一步降低CPU使用率。
- 增加针对高端CPU及高PCIE带宽的加速模式。
- 支持Linux
- 修复已知BUG，提升稳定性。

#### v1.3(2018-06-03)

- 第一版。
- 支持Windows。
- 优化CPU、PCI-E带宽占用。
- 优化挖矿速度。
- 支持标准stratum协议。