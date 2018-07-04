# BTM GPU挖矿软件（NebuTech BTMiner）

用于Nvidia显卡的BTM（比原链）挖矿软件。

## 下载地址

[从这里下载](https://github.com/NebuTech/BTMiner_NebuTech/releases)

## 功能特点：

- 支持Win7、Win10、Linux
- 支持标准stratum协议的矿池，测试过：[f2pool](https://www.f2pool.com/)、[antpool](https://www.antpool.com/)、[btcc](https://btccpool.info/) 、[蜘蛛矿池](https://pool.zhizhu.top/)、[91pool](http://www.91pool.com)
- 不占用CPU和PCI-E带宽，现有6卡、8卡矿机适用
- 从v5.0开始只支持10代及以后的N卡，前代卡请使用老版本软件
- 包含3%开发手续费，可以通过选项关闭

## 使用方法：

1. **驱动版本，Windows大于等于385, Ubuntu大于384**
2. 编辑`start_cmd.bat`文件(Linux系统修改`start_cmd.sh`)，修改`-url`后面的矿池地址和`-user`后面的钱包地址或用户名。如果有密码，添加`-p`参数和密码。
3. Windows双击运行`start_cmd.bat`开始挖矿, Linux通过命令行运行`start_cmd.sh`开始挖矿。

## 参考显卡性能

- **注：以下参数均为显卡默认频率功耗下的测试数据**

| 显卡    | 参考算力（H/s） |
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

## 命令行参数 CMD command ：

BTMiner_NebuTech [参数]

典型用法 Simple ：BTMiner_NebuTech -url btm.f2pool.com:9221 -user bm1xxxxxxxxxxxx.rigName

参数：

- -?, -h, --help      显示帮助信息.
- -v, --version       显示版本号.
- -c, --config        通过配置文件启动挖矿程序.
- -o, --url <url>     矿池地址.
- -u, --user <user>   挖矿使用的用户名或钱包地址.
- -p, --passwd <password>	挖矿使用的密码.
- -d, --devices <devices>	指定使用哪些显卡来挖矿. 比如: "-d 0,1,2,3" 使用前4个显卡.
- -M, --more-gpu      使用这个选项可避免"cuda out of memory error"，可能会有小部分的算力损失.
- -S, --ssl           使用SSL连接矿池（需矿池支持）
- --no-fee            关闭开发者手续费，同时会关闭部分优化，算力有所下降。

## 开发计划

- 完善对显卡异常的处理
- 提供API接口，方便集成和批量管理
- 提高算力
- 不再进行GUI版本开发，推荐使用集成了我们的BTMiner，功能更加丰富的软件：[深圳矿工](http://www.szminer.net/)（WIndows）、[矿山系统](http://40451.net/)（Linux）

## 致谢 Thanks

@earthGavinLee

## 修改记录

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