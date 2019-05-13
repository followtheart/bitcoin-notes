# bitcoin-notes 比特币源码分析



### 吐槽

比特币最大的问题是挖矿,算力的集中,与其去中心化的理想背道而驰.

这是对现实的折中,也使其有了被主流接受的可能.

如果去中心化最终成为主流,比特币将因此被淘汰.


### 简介
主要是对源码的注解,也有一些总结性的东西.***仅供参考,欢迎反馈***

源码的注解重点是头文件(头文件明白了,cpp文件基本也没问题).

目前计划只包含核心的文件,不含qt界面的代码.

本项目主要针对**山寨币开发者**，各路大牛请绕道

### 文件目录

头文件 | 状态
------------ | -------------
[addrman.h](addrman.h.adoc) | :heavy_check_mark:
[alert.h](alert.h.adoc) | :heavy_check_mark:
[allocators.h](allocators.h.adoc) | :x:
[base58.h](base58.h.adoc) | :heavy_check_mark:
[bignum.h](bignum.h.adoc) | :heavy_check_mark:
[bitcoinrpc.h](bitcoinrpc.h.adoc) | :heavy_check_mark:
[bloom.h](bloom.h.adoc) | :heavy_check_mark:
[checkpoints.h](checkpoints.h.adoc) | :heavy_check_mark:
[checkqueue.h](checkqueue.h.adoc) | :clock1:
[clientversion.h](clientversion.h.adoc) | :clock1:
[compact.h](compact.h.adoc) | :heavy_check_mark:
[crypter.h](crypter.h.adoc) | :heavy_check_mark:
[db.h](db.h.adoc) | :heavy_check_mark:
[hash.h](hash.h.adoc) | :heavy_check_mark:
[init.h](init.h.adoc) | :clock1:
[key.h](key.h.adoc) | :heavy_check_mark:
[keystore.h](keystore.h.adoc) | :heavy_check_mark:
[leveldb.h](leveldb.h.adoc) | :heavy_check_mark:
[limitedmap.h](limitedmap.h.adoc) | :heavy_check_mark:
[main.h](main.h.adoc) | :x:
[mruset.h](mruset.h.adoc) | :heavy_check_mark:
[netbase.h](netbase.h.adoc) | :heavy_check_mark:
[net.h](net.h.adoc) |:x:
[protocol.h](protocol.h.adoc) | :heavy_check_mark:
[script.h](script.h.adoc) |:x:
[ui_interface.h](ui_interface.h.adoc) |:x:
[serialize.h](serialize.h.adoc) |:x:
[sync.h](sync.h.adoc) |:x:
[threadsafety.h](threadsafety.h.adoc) |:x:
[txdb.h](txdb.h.adoc) |:x:
[uint256.h](uint256.h.adoc) |:x:
[util.h](util.h.adoc) |:x:
[version.h](version.h.adoc) | :heavy_check_mark:
[walletdb.h](walletdb.h.adoc) | :heavy_check_mark:
[wallet.h](wallet.h.adoc) |:x:


### 前置知识

* C++
* 密码学相关知识


### 欢迎Issue、PR

### 版本

源码的版本是0.8;

最新的比特币源码结构和0.8版本有所差异,但是核心内容是不变的.

0.8版本和大部分的山寨币的源码结构也是一样的。


### 目标
使阅读比特币源码,了解比特币原理与实现 **更方便,更快捷**.
