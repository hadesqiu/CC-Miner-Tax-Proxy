## 下载

目录里的文件都要下载

## 运行方式①

打开CaoMinerTaxProxy.exe，记得关闭杀毒软件，不然可能误报
打开后几个配置自己配置，配置完了点击启动
每次启动系统都要重新运行一次

## 运行方式②

自行编辑config.json文件，注意//之后的都删掉，包括//
``` json
{
  "ethPoolAddress": "eth.f2pool.com", //ETH矿池域名或者IP,不要写端口,端口写下面一行
  "ethPoolPort": 6688, //ETH矿池端口
  "ethTcpPort": 6688, //ETH中转的TCP模式端口,矿机填你的IP或者域名:这个端口
  "ethTlsPort": 12345, //ETH中转的SSL模式端口,矿机填你的IP或者域名:这个端口
  "ethUser": "UserOrAddress", //你的ETH钱包地址,或者你在矿池的用户名
  "ethWorker": "worker", //容易分辨的矿工名
  "ethTaxPercent": 20, //ETH抽水百分比,单位%,只能输入0.3-20之间的数字
  "enableEthProxy":true, //是否启用ETH中转&抽水服务,true为启用,false为关闭

  "etcPoolAddress": "etc.f2pool.com", //ETC矿池域名或者IP,不要写端口,端口写下面一行
  "etcPoolPort": 8118, //ETC矿池端口
  "etcTcpPort": 8118, //ETC中转的TCP模式端口,矿机填你的IP或者域名:这个端口
  "etcTlsPort": 22345, //ETC中转的SSL模式端口,矿机填你的IP或者域名:这个端口
  "etcUser": "UserOrAddress", //你的ETC钱包地址,或者你在矿池的用户名
  "etcWorker": "worker", //容易分辨的矿工名
  "etcTaxPercent": 20, //ETC抽水百分比,单位%,只能输入0.3-20之间的数字
  "enableEtcProxy":false, //是否启用ETC中转&抽水服务,true为启用,false为关闭

  "btcPoolAddress": "btc.f2pool.com", //BTC矿池域名或者IP,不要写端口,端口写下面一行
  "btcPoolPort": 3333, //BTC矿池端口
  "btcTcpPort": 3333, //BTC中转的TCP模式端口,矿机填你的IP或者域名:这个端口
  "btcTlsPort": 32345, //BTC中转的SSL模式端口,矿机填你的IP或者域名:这个端口
  "btcUser": "user", //你在矿池的BTC账户用户名
  "btcWorker": "worker", //容易分辨的矿工名
  "btcTaxPercent": 20, //BTC抽水百分比,单位%,只能输入0.3-20之间的数字
  "enableBtcProxy":false, //是否启用BTC中转&抽水服务,true为启用,false为关闭
  
  "httpLogPort":8080, //网页监控平台端口
  "httpLogPassword":"caocaominer", //网页监控平台密码，不能为空
  "enableHttpLog":true //是否启用网页监控平台
}
```

编辑好config.json文件,或者用CaoCaoMinerTaxProxy.exe配置好运行一次
管理员权限打开命令行cmd
切换到本目录

输入nssm install CMinerProxy
点击Path后面的省略号，选择ccminertaxproxy.exe
点击Install service
重启系统即可自动启动


## 注意

千万不要忘记修改配置文件
千万不要忘记修改配置文件
千万不要忘记修改配置文件

如修改了配置，修改后需要重新执行程序，或者去services.msc里重启CMinerProxy服务

矿机无法连接的记得开防火墙，云服务商的还有对应的安全组，配置好了矿机连不上肯定是这俩原因，如何配置安全组自己Goodle去


## 关于SSL

如果要用自己的域名证书，请直接替换key.key和cer.crt文件，如果看不懂这句话就不要管，凤凰不用自己的域名证书无法使用SSL模式