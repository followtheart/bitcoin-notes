# bitcoin-notes 比特币源码简单分析
<a target="_blank" href="http://shang.qq.com/wpa/qunwpa?idkey=0fef5aa161c5074030c3f2e99c6d564a4c68d469f187c08530d270e15714e7c2"><img border="0" src="https://pub.idqqimg.com/wpa/images/group.png" alt="zaobi.org官方群" title="zaobi.org官方群">130313918</a>

<img border="0" height="300px" src="./images/Q.jpg">
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
<table>
  <tr>
    <th width=33%, bgcolor=gray >文件名</th>
    <th width=10%, bgcolor=gray>状态</th>
  </tr>
  <tr>
    <td> [addrman.h](addrman.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [alert.h](alert.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [allocators.h](allocators.h.adoc) </td>
    <td bgcolor=OrangeRed > × </td>
  </tr>
  <tr>
    <td> [base58.h](base58.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [bignum.h](bignum.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [bitcoinrpc.h](bitcoinrpc.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [bloom.h](bloom.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [checkpoints.h](checkpoints.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [checkqueue.h](checkqueue.h.adoc) </td>
    <td bgcolor=yellow> ... </td>
  </tr>
  <tr>
    <td> [clientversion.h](clientversion.h.adoc) </td>
    <td bgcolor=yellow> ... </td>
  </tr>
    <tr>
    <td> [compat.h](compat.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [crypter.h](crypter.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [db.h](db.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [hash.h](hash.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [init.h](init.h.adoc) </td>
    <td bgcolor=yellow> ... </td>
  </tr>
    <tr>
      <td> [key.h](key.h.adoc) </td>
      <td bgcolor=SpringGreen> √ </td>
    </tr>
    <tr>
      <td> [keystore.h](keystore.h.adoc) </td>
      <td bgcolor=SpringGreen> √ </td>
    </tr>
    <tr>
      <td> [leveldb.h](leveldb.h.adoc) </td>
      <td bgcolor=SpringGreen> √ </td>
    </tr>
    <tr>
      <td> [limitedmap.h](limitedmap.h.adoc) </td>
      <td bgcolor=SpringGreen> √ </td>
    </tr>
  <tr>
    <td> [main.h](main.h.adoc) </td>
    <td bgcolor=OrangeRed> × </td>
  </tr>
  <tr>
    <td> [mruset.h](mruset.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [netbase.h](netbase.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [net.h](net.h.adoc) </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> [protocol.h](protocol.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [script.h](script.h.adoc) </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>  
  <tr>
      <td> [ui_interface.h](ui_interface.h.adoc) </td>
      <td bgcolor=OrangeRed > X </td>
    </tr>
  <tr>
    <td> [serialize.h](serialize.h.adoc) </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> [sync.h](sync.h.adoc) </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> [threadsafety.h](threadsafety.h.adoc) </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> [txdb.h](txdb.h.adoc) </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> [uint256.h](uint256.h.adoc) </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> [util.h](util.h.adoc) </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> [version.h](version.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [walletdb.h](walletdb.h.adoc) </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> [wallet.h](wallet.h.adoc) </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
</table>

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
