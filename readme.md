# BTM GPU挖矿软件（NebuTech BTMiner）

用于Nvidia显卡的BTM（比原链）挖矿软件。

## 下载地址

[从这里下载](https://github.com/NebuTech/BTMiner_NebuTech/releases)

## 特点：

支持Windows

支持标准stratum协议的矿池，测试过：antpool、f2pool、btcc

几乎不占用CPU和PCI-E带宽，现有6卡、8卡矿机适用

优化算力

## 安装：

1. 更新到最新版本的Nvidia显卡驱动，不支持旧版本驱动。（目前驱动版本是397.64）
2. 使用记事本打开`挖矿.bat`文件，修改`-url`后面的矿池地址和`-user`后面的钱包地址或用户名。如果有密码，添加`-p`参数和密码。
3. 双击运行run.bat开始挖矿。

## 使用方法：

BTMiner_NebuTech.exe [参数]

典型用法：BTMiner_NebuTech.exe -url btm.f2pool.com:9221 -user bm1xxxxxxxxxxxx.rigName -p x

参数：

  * -?, -h, --help				显示帮助信息.
  * -v, --version				显示版本号.
  * -u, --url <url>			矿池地址.
  * -U, --user <user>		挖矿使用的用户名或钱包地址.
  * -p, --passwd <password>	挖矿使用的密码.
  * -d, --devices <devices>	指定使用哪些显卡来挖矿. 比如: "-d 0,1,2,3" 使用前4个显卡.
  * **-i, --intensity <intensity>	挖矿强度，默认256，不同显卡达到最高算力的强度不同，1080ti一般在1024左右，1070强度512，可自行测试选择最佳.**

## 修改记录：

v1.3(2018-06-03)

第一版。

支持Windows。

优化CPU、PCI-E带宽占用。

优化挖矿速度。

支持标准stratum协议。