# Clarules_mine

## 文件还是需要分开写：
- mac 指定出口网卡，tun不自动指定
- win
- android 目前自动指定出口没问题
- nas 可能需隐藏端口到高位

## 简介

该仓库功能：

1. Clash配置文件迭代记录
2. 在线的自定义配置文件，为配置文件提供在线的自定义功能列表
3. 提供通过模板自动生成 `box.config` 并发布release的功能

   1. push模板 或者 pkg_list后，自动生成release
   2. 模板中，可使用
      1. #开头的注释
      2. 空白行分割

## Clash配置文件


### 若是代理出现不走核心，建议重新找端口号试试

### 最新配置链接:

https://secure-raw.212676.xyz/transfer/ClashFile/main/latest.yaml?token=114514&info=loadConfig

### 检测网站

dns+ip: [ipleak](https://ipleak.net/)

dns leak test: [dns leak test](https://browserleaks.com/dns)

ip+cdn+连通性测试:[ip.skk.moe](https://ip.skk.moe/)

### 版本一览

| 版本           | Features                                                                                              |        | Todo                                                                                              |
| -------------- | ----------------------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------- |
| Loc_1.0        | 基础的本地订阅合并                                                                                    | 240813 | \                                                                                                 |
| Online_1.0     | 基础的网络合并                                                                                        | 240805 | \                                                                                                 |
| Loc_2.0_mihomo | <br />高级语法实现代理自动分组<br />变更dns逻辑,配合surfing实现手机端透明代理<br />更新规则集         | 241021 | ~~ipleak.net检测到仍有部分v6 DNS,需要修复~~<br />~~尝试转为网络合并方便更新~~<br />添加分组轮询 |
| Loc_3.0_mihomo | ipleak.net检测到v6 DNS<br />更新自定义仓库链接                                                        | \      | \                                                                                                 |
| v4.0           | 配合托管链接更新<br />尝试转为网络合并方便更新                                                        | \      | \                                                                                                 |
| v5.0           | 改为自动引用所有节点<br />改变远程库文件格式<br />更新文件结构                                        | \      | \                                                                                                 |
| v6.0           | 配合box 实现tun使用exclude-packages                                                                   | \      | \                                                                                                 |
| v7.0           | 配合box4magisk的core模式现tun使用exclude-packages<br />更新dns,更新tun设备名称,避免通过网卡的代理检测 | 241102 | \                                                                                                 |

### 补充日志

Loc_2.0_mihomo:

添加了在线的自定义规则内容提供,详见仓库 [前置自定义在线规则仓库](https://github.com/NiuHK/Clarules_mine)

添加广告拦截



## [域名通配符](https://wiki.metacubex.one/handbook/syntax/#_8)[¶](https://wiki.metacubex.one/handbook/syntax/#_8 "Permanent link")

### [通配符 `*`](https://wiki.metacubex.one/handbook/syntax/#_9)[¶](https://wiki.metacubex.one/handbook/syntax/#_9 "Permanent link")

vue的通配符 `*` 一次只能匹配一级域名

`*.baidu.com` 只匹配 `tieba.baidu.com` 而不匹配 `123.tieba.baidu.com` 或者 `baidu.com`

`*`只匹配 localhost 等没有 `.`的主机名

### [通配符 `+`](https://wiki.metacubex.one/handbook/syntax/#_10)[¶](https://wiki.metacubex.one/handbook/syntax/#_10 "Permanent link")

通配符 ＋ 类似 DOMAIN-SUFFIX, 可以一次性匹配多个级别

`＋.baidu.com` 匹配 `tieba.baidu.com` 和 `123.tieba.baidu.com` 或者 `baidu.com`

通配符 `＋` 只能用于域名前缀匹配

### [通配符 `.`](https://wiki.metacubex.one/handbook/syntax/#_11)[¶](https://wiki.metacubex.one/handbook/syntax/#_11 "Permanent link")

通配符 . 可以一次性匹配多个级别

`.baidu.com` 匹配 `tieba.baidu.com` 和 `123.tieba.baidu.com`, 但不能匹配 `baidu.com`

通配符 `.` 只能用于域名前缀匹配

### [使用示例](https://wiki.metacubex.one/handbook/syntax/#_12)[¶](https://wiki.metacubex.one/handbook/syntax/#_12 "Permanent link")

使用通配符时，应当使用引号 `' '`或 `" "`将内容包裹起来

```
fake-ip-filter:
-".lan"
-"xbox.*.microsoft.com"
-"+.xboxlive.com"
-localhost.ptlogin2.qq.com
```

|  |  |
| - | - |

- localhost.ptlogin2.qq.com
