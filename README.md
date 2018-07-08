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
    <td> <a href="addrman.h.adoc">addrman.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="alert.h.adoc">alert.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="allocators.h.adoc">allocators.h</a> </td>
    <td bgcolor=OrangeRed > × </td>
  </tr>
  <tr>
    <td> <a href="base58.h.adoc">base58.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="bignum.h.adoc">bignum.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="bitcoinrpc.h.adoc">bitcoinrpc.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="bloom.h.adoc">bloom.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="checkpoints.h.adoc">checkpoints.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="checkqueue.h.adoc">checkqueue.h</a> </td>
    <td bgcolor=yellow> ... </td>
  </tr>
  <tr>
    <td> <a href="clientversion.h.adoc">clientversion.h</a> </td>
    <td bgcolor=yellow> ... </td>
  </tr>
    <tr>
    <td> <a href="compat.h.adoc">compat.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="crypter.h.adoc">crypter.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="db.h.adoc">db.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="hash.h.adoc">hash.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="init.h.adoc">init.h</a> </td>
    <td bgcolor=yellow> ... </td>
  </tr>
    <tr>
      <td> <a href="key.h.adoc">key.h</a> </td>
      <td bgcolor=SpringGreen> √ </td>
    </tr>
    <tr>
      <td> <a href="keystore.h.adoc">keystore.h</a> </td>
      <td bgcolor=SpringGreen> √ </td>
    </tr>
    <tr>
      <td> <a href="leveldb.h.adoc">leveldb.h</a> </td>
      <td bgcolor=SpringGreen> √ </td>
    </tr>
    <tr>
      <td> <a href="limitedmap.h.adoc">limitedmap.h</a> </td>
      <td bgcolor=SpringGreen> √ </td>
    </tr>
  <tr>
    <td> <a href="main.h.adoc">main.h</a> </td>
    <td bgcolor=OrangeRed> × </td>
  </tr>
  <tr>
    <td> <a href="mruset.h.adoc">mruset.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="netbase.h.adoc">netbase.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="net.h.adoc">net.h</a> </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> <a href="protocol.h.adoc">protocol.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="script.h.adoc">script.h</a> </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>  
  <tr>
      <td> <a href="ui_interface.h.adoc">ui_interface.h</a> </td>
      <td bgcolor=OrangeRed > X </td>
    </tr>
  <tr>
    <td> <a href="serialize.h.adoc">serialize.h</a> </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> <a href="sync.h.adoc">sync.h</a> </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> <a href="threadsafety.h.adoc">threadsafety.h</a> </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> <a href="txdb.h.adoc">txdb.h</a> </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> <a href="uint256.h.adoc">uint256.h</a> </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> <a href="util.h.adoc">util.h</a> </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> <a href="version.h.adoc">version.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="walletdb.h.adoc">walletdb.h</a> </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> <a href="wallet.h.adoc">wallet.h</a> </td>
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
