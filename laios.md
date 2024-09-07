# laios
1. 自我介绍
大家好，我是 laios
2. 你认为你会完成本次残酷学习吗？
 我可以
## Notes

<!-- Content_START -->

### 2024.09.07

**Aptos区块链概述**

Aptos区块链使用拜占庭容错（BFT）共识协议，验证节点通过该协议就已完成的交易和其执行结果达成一致。验证节点决定哪些交易将被添加到区块链以及其顺序，并在本地维护最新的区块链状态。

验证节点在一个私有网络中直接相互通信，而完整节点则充当已确认交易历史的外部验证或传播资源。完整节点可重新执行交易以验证其正确性，并在发现问题时提供证据，防止验证节点的腐败或串通。

AptosBFT共识协议能够容忍最多三分之一的恶意验证节点。

验证节点的主要组件

- Mempool：一个存储尚未达成共识或执行的交易的内存缓冲区。通过mempool，各节点间可以共享这些待处理的交易。mempool还负责验证新交易的合法性，并防止拒绝服务攻击（DOS）。
- 共识（Consensus）：负责在网络中各验证节点之间达成共识，确定交易块的排序并就执行结果达成一致。临时成为领导者的验证节点从mempool中提取交易，提出新的交易块，并广播给其他验证节点。
- 执行（Execution）：负责协调交易块的执行并维护暂时状态，直到共识达成并提交块到分布式数据库。执行组件与虚拟机协作，以确保交易的执行。
- 虚拟机（VM）：运行每笔交易中的Move程序，决定执行结果。mempool使用虚拟机进行交易的初步验证，而执行组件使用虚拟机来实际执行交易。
- 存储（Storage）：用于将达成共识的交易块及其执行结果持久化到本地数据库。
- 状态同步器（State Synchronizer）：确保节点能够“追赶”区块链的最新状态并保持最新。



### 2024.09.08 

#### 环境配置

rust 下载并配置

[Install the Aptos CLI on Windows | Aptos Docs (en)](https://aptos.dev/en/build/cli/install-cli/install-cli-windows)



#### hello world

- 创建项目

```
aptos move init --name lesson1
aptos init 
```

- 配置powershell代理v2ray

```
$env:HTTP_PROXY="http://127.0.0.1:10809"
$env:HTTPS_PROXY="http://127.0.0.1:10809"
curl www.google.com
```

- 测试代码

```move
module Lesson1::HelloWorld{
    use std::debug::print;
    use std::string::utf8;

    #[test]
    fun test_hello_world(){
        print(&utf8(b"hello world"));
    }

    
}

aptos move test
```



#### 变量



```move
module 0x42::Lesson2{
    use std::debug::print;
    use std::string::utf8;

    struct Wallet has drop {
        balance: u64
    }

    #[test]
    fun test_hello_world(){
        let wallet = Wallet{ balance: 100 };
        let wallet2 = wallet;

        
        print( &wallet2.balance );
    }

    
}

module 0x43::Lesson3{
    use std::debug::print;
    use std::string::{utf8,String};


    #[test]
    fun test_num(){
        let num_u8: u8 = 42;
        let num_u8_2 = 48u8;
        print(&num_u8);
        print(&num_u8_2);

        let num_256: u256 = 100_000;
        print(&num_256);

        let num_sum: u256 = (num_u8 as u256) + num_256;
        print(&num_sum);
    }

    #[test]
    fun test_bool(){

        let bool_true: bool = true;
        let bool_false: bool = false;

        print(&bool_false);
        print(&bool_true);
        print(&( bool_true ||bool_false ));
    }

    #[test]
    fun test_string(){
        let str: String = utf8(b"hello world");
        print(&str);
    }

    #[test]
    fun test_address(){
        let addr: address = @0x2a;
        let addr2: address = @0x0a;
        print(&addr);
        print(&addr2);
    }
    
}
```











#### move by example







