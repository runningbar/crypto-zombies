# crypto-zombies

`crypto-zombies`是一个基于以太坊区块链的加密僵尸游戏。

受教于`LoomNetwork`推出的[**CRYPTOZOMBIES**课程](https://cryptozombies.io/)

# 特性

* 基于`Infura`和`MetaMask`和以太坊合约进行交互，以开发dapp前端

    * `call()`
    * `send()`：带支付功能
    * 使用`websocket`订阅`event`，并结合`indexed`过滤事件

* 合约的`ABI`

* 实现`OpenZeeplin`对`ERC721`规范的数字收藏品标准

* 对`library`的使用：使用`OpenZeeplin`的`SafeMath`库，防止计算中溢出

* 合约继承：大量使用多重继承特性，拆分代码逻辑，管理工程文件

* 带有冷却时间的僵尸对战机制

* 使用`transfer`从合约中提款`ETH`

* 大量使用`modifier`自定义修饰符，以限定某些函数的执行条件：比如只允许合约部署者才能调用该函数

* 函数可见性控制：`public`, `private`, `external`, `internal`

* 使用`payable`制造可付款函数：该函数只有接受到指定数量的`ETH`才会执行

* 僵尸升级，僵尸改名，修改僵尸DNA

* 合约事件`event`：重要时刻可以随时推送给`dapp`前台

* 只读的函数修饰符：`view`, `pure`

* 节省gas的技巧：多使用廉价的`event`，少使用昂贵的`storage`，尽量使用基础性数据的`storage`衍生出各种功能，合适的时候可以使用`view`,`pure`修饰符免费使用以太坊

* 跨合约调用：声明接口和其它合约的地址，对其他合约的函数进行调用。【区块链的魅力】

* 喂食僵尸，创造新僵尸

* 创造随机数：使用`keccak256()`在区块链上生成随机数。

* 构造函数：与合约同名，合约部署时即自动执行，可以用来确权等。