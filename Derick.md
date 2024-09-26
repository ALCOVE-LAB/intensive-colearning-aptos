### Derick
- web3开发者
- 希望通过这次共学能使用move在aptos部署一个应用


## Notes

<!-- Content_START -->

### 2024.09.07
 -  [x] 推荐的aptos钱包  ：https://petra.app/
 -  [x] 在jbIDE中安装move on aptos
 -  [x] move[学习文档](https://aptos.dev/en/build/smart-contracts/why-move)
 -  [x] aptos[浏览器](https://explorer.aptoslabs.com/analytics?network=mainnet)
 -  [ ] aptos讨论区：https://github.com/aptos-labs/aptos-developer-discussions/discussions
- Move 合约升级的特点
- 包（Package）为单位: Move 合约是以包为单位进行组织和部署的。升级时，需要重新部署整个包。
- 严格的类型系统: Move 的严格类型系统确保了合约升级的安全性，防止意外的数据损坏或逻辑错误。
- 资源的移动和销毁: Move 中的资源不能被随意复制，只能通过明确的移动操作进行传递。这使得在升级过程中对资源的管理更加安全。
- 灵活的升级方式: Move 提供了多种升级方式，可以根据不同的需求选择合适的升级策略。
- Move 合约升级的常见方式
- 重新部署:

- 直接覆盖: 将新的包部署到相同的地址，覆盖旧的包。这种方式简单直接，但需要注意，所有状态数据都会丢失。
- 数据迁移: 在部署新包之前，将旧包中的状态数据迁移到新的包中。这种方式比较复杂，但可以保留原有的数据。
- 分阶段升级:

- 逐步升级: 将升级分成多个阶段，每个阶段只修改部分功能，以降低风险。
- 兼容性考虑: 在升级过程中，需要确保新旧版本之间的兼容性，避免出现不兼容的问题。
### 2024.09.08
Aptos采用了一种改进的BFT(拜占庭容错)共识机制,称为AptosBFT或DiemBFT,具有以下几个关键特点来确保网络安全:

1. 领导者轮换机制改进:
   AptosBFT增加了节点信誉系统(State-Machine Replication, SMR),通过检查链上数据来跟踪活跃节点,并从中选举领导者. 这可以避免故障节点被选为领导者,提高网络稳定性.

2. 快速区块确认:
   通过改进的协议,区块只需两次网络往返即可提交,实现亚秒级的最终确定性. 这大大缩短了交易确认时间.

3. 容错能力:
   AptosBFT可以容忍最多1/3的验证者节点出现故障或恶意行为. 只要有2/3以上的诚实节点,网络就能正常运行.

4. 主动起搏器:
   AptosBFT添加了主动起搏器,使用超时来同步验证器,比等待增加的超时更快.

5. 安全性验证:
   AptosBFT的共识协议已经过审计和正式验证,确保其安全性.

6. 网络活性与安全分离:
   Aptos的协议将网络活性与安全性清晰分开,即使网络中断,只要BFT机制的诚实保证得到维护,就不需要分叉区块链.

### 2024.09.09
 -  [ ] 学习[Move Tutorial](https://github.com/aptos-labs/aptos-core/tree/main/aptos-move/move-examples/move-tutorial) 前三章
### 2024.09.10
```
module 0xCAFE::basic_coin {
    struct Coin has key {
        value: u64,
    }

    public entry fun mint(account: &signer, value: u64) {
        move_to(account, Coin { value })
    }
}
```
- 创建一个move合约，定义了一个名为 basic_coin 的模块，属于地址 0xCAFE。在 Move 中，模块是代码的基本组织单位。
- 名为 Coin 的结构体。它有一个 key 能力，意味着它可以作为全局存储中的顶级资源。结构体包含一个名为 value 的字段，类型为 u64（64位无符号整数）。
- 定义了一个名为 mint 的公共入口函数。它有两个参数：account: &signer：代表交易发送者的签名者引用。 value: u64：要铸造的代币数量。函数体使用 move_to 操作将新创建的 Coin 资源移动到 account 的存储中。这effectively "铸造"了新的代币并将其分配给指定账户。
### 2024.09.11
```
#[test(account = @0xC0FFEE)]
fun test_mint_10(account: &signer) acquires Coin {
    let addr = signer::address_of(account);
    mint(account, 10);
    assert!(borrow_global<Coin>(addr).value == 10, 0);
}
```
- #[test(account = @0xC0FFEE)] 声明这是一个测试，并为测试提供一个地址为 0xC0FFEE 的签名者。
acquires Coin 表示这个函数会访问 Coin 资源。
测试逻辑：
获取账户地址
调用 mint 函数铸造 10 个代币
使用 assert! 检查该地址下的 Coin 资源的 value 是否为 10
### 2024.09.12
```
public fun mint(module_owner: &signer, mint_addr: address, amount: u64) acquires Balance { .. }
这个函数用于铸造代币。只有模块所有者可以调用此函数。它需要访问 Balance 资源。
public fun balance_of(owner: address): u64 acquires Balance { .. }
这个函数用于查询指定地址的余额。它需要访问 Balance 资源。
public fun transfer(from: &signer, to: address, amount: u64) acquires Balance { .. }
这个函数用于转账。它需要访问 Balance 资源。
```
### 2024.09.13
aptos-Move区块链的状态结构具有清晰的层级关系，主要由以下几个部分组成：

## 全局存储（Global Storage）

全局存储是Move区块链状态的最顶层结构，作为整个状态的根节点。它包含了所有的地址和与之相关的数据。

## 地址（Addresses）

地址是全局存储的直接子节点，用十六进制表示（如0x1, 0x2, 0x42等）。每个地址代表区块链上的一个账户或合约。地址的作用是：
- 唯一标识区块链上的实体
- 存储该实体相关的资源和模块

## 资源（Resources）

资源存储在特定地址下，代表该地址拥有的数字资产或状态。例如，图中展示了地址0x42下的"BasicCoin"资源，包含"Balance"和"value"等属性。资源的作用是：
- 存储用户的资产信息
- 维护账户相关的状态数据

## 模块（Modules）

模块也存储在特定地址下，包含智能合约的字节码。如图中地址0x42下的"BasicCoin"模块。模块的作用是：
- 定义资源的结构和操作逻辑
- 实现智能合约的功能
- 控制资源的创建、修改和销毁

这种层级结构的设计有以下优点：

1. 清晰的所有权：每个资源和模块都有明确的所有者（地址）。
2. 模块化：将代码（模块）和数据（资源）分离，提高了系统的灵活性和可维护性。
3. 安全性：通过地址和模块的组合，可以实现精细的访问控制。
4. 可扩展性：这种结构允许轻松添加新的地址、资源和模块，便于系统的扩展。

### 2024.09.14
根据Aptos白皮书的描述,Aptos区块链在交易处理过程中采用了流水线和模块化的方法,主要包括以下几个关键阶段:

1. 交易传播 - 将交易广播到网络中的其他节点

2. 区块元数据排序 - 对区块中交易的元数据进行排序

3. 并行交易执行 - 利用Block-STM并行执行引擎并行处理交易

4. 批量存储 - 将执行结果批量写入存储

5. 账本认证 - 对账本历史和状态进行认证

这些阶段同时运行,充分利用了所有可用的物理资源,提高了硬件效率,实现了高度并行的执行。

### 2024.09.15
Aptos区块链采用的是基于HotStuff的拜占庭容错(BFT)共识机制,具有以下主要特点:

1. 领导者轮换机制:每个共识回合都会选出一个新的领导者节点来提议区块,避免单点故障。

2. 节点信誉系统:通过跟踪节点的活跃度和有效性来选举领导者,提高效率。

3. 三阶段投票:包括提议、预投票和预提交三个阶段,确保共识的安全性。

4. 并行执行:使用Block-STM技术实现交易的并行执行,提高吞吐量。

5. 快速恢复:当领导者节点出现问题时,可以快速选出新的领导者继续工作。

6. 高容错性:只要有2/3以上的诚实节点,网络就可以正常运行。

7. 最终一致性:一旦达成共识,交易就不可逆转。

8. 高效验证:使用聚合签名等技术提高验证效率。

这种共识机制旨在实现高吞吐量、低延迟和强一致性,同时保持良好的去中心化和安全性。它是Aptos实现高性能的关键技术之一。

### 2024.09.16
Sui区块链采用了几种机制来降低交易延迟:

1. 对象存储模型:Sui将数据存储为独立的对象,每个对象都有唯一标识符。这种模型允许并行执行和水平扩展,提高了处理效率。

2. 并行执行:Sui可以并行处理不同对象的交易,大大提高了吞吐量。

3. Mysticeti共识机制:这是一种基于拜占庭容错(BFT)的共识机制,专门优化了低延迟和高吞吐量。它允许多个验证器并行提出区块,充分利用网络带宽。

4. 快速路径执行:对于只涉及"自有对象"的简单交易(如点对点转账),Sui可以通过快速路径执行,无需达成共识,从而大大缩短处理时间。

5. 流水线处理:Sui将交易处理分为多个阶段并行执行,如传播、元数据排序、批处理存储等,最大限度地提高了效率。

6. 无领导协议:Sui采用无领导协议来处理交易,避免了单点故障,提高了整体性能。

7. 优化的验证器通信:Mysticeti协议仅需三轮消息即可从DAG中提交区块,减少了验证器之间的通信开销。

通过这些机制的综合应用,Sui能够实现极低的交易延迟,据报道可以达到每秒处理数万笔交易,端到端延迟远低于一秒。

### 2024.09.17
 -  [ ] 
### 2024.09.18
今天参加分享会，学习创建代币FAUCET，并了解了FA
Aptos中的FA (Fungible Asset)是一种可替代资产的实现,具有以下主要特点:

1. 可替代性: FA代表的是可互换的资产,每个单位都是等价的,比如代币。这与非同质化代币(NFT)不同。

2. 标准化接口: Aptos提供了标准的FA接口,包括铸造、转账、销毁等操作,便于开发者创建和管理自定义代币。

3. 灵活性: 开发者可以自定义FA的属性,如名称、符号、精度等。

4. 安全性: FA的实现包含了各种安全机制,如访问控制、资产隔离等。

5. 与主要存储集成: FA可以与Aptos的主要存储(primary store)系统集成,简化了资产管理。

6. 元数据: 可以为FA附加元数据,提供额外信息。

7. 引用系统: 通过MintRef、TransferRef、BurnRef等引用来控制资产的各种操作权限。

8. 与Aptos生态系统兼容: FA可以在Aptos的各种DApp和服务中使用。

在实际应用中,FA可用于创建各种类型的代币,如稳定币、治理代币、奖励积分等。它为Aptos上的DeFi、GameFi等应用提供了基础设施支持。

FA为Aptos提供了一个灵活、安全、标准化的可替代资产框架,使开发者能够轻松创建和管理各种类型的数字资产。

### 2024.09.19
 -  [x] 编写第一个aptos move合约
 -  [ ] https://explorer.aptoslabs.com/txn/0xa19cedda225355eb4fa5cfc15c5c5d3bd00cd5fc7cdd43b667e44e16152ef471/userTxnOverview?network=testnet 
### 2024.09.20
```
#[event]
struct MessageChange has drop, store {
    account: address,
    from_message: string::String,
    to_message: string::String,
}
```
这定义了一个名为MessageChange的事件结构。#[event]属性表明这是一个事件。它包含三个字段：触发事件的账户地址，以及消息更改前后的内容。
### 2024.09.21
```
#[view]
public fun get_message(addr: address): string::String acquires MessageHolder {
    assert!(exists<MessageHolder>(addr), error::not_found(ENO_MESSAGE));
    borrow_global<MessageHolder>(addr).message
}
```
这是一个公共函数get_message：
#[view]属性表示这是一个只读函数。
函数接受一个地址参数，返回一个字符串。
acquires MessageHolder表示这个函数会访问MessageHolder资源。
函数首先检查指定地址是否存在MessageHolder资源，如果不存在则抛出错误。
如果存在，函数返回该地址下MessageHolder资源中的message字段。
### 2024.09.22
在Aptos Move中编写单元测试的主要步骤如下:

1. 在Move文件中使用 `#[test]` 注解标记测试函数:

```move
#[test]
fun test_function() {
    // 测试代码
}
```

2. 测试函数通常是私有的(`fun`)而不是公开的(`public fun`)。

3. 使用 `assert!` 宏来验证测试结果:

```move
#[test]
fun test_addition() {
    let result = 2 + 2;
    assert!(result == 4, 0);
}
```

4. 可以使用 `#[expected_failure]` 注解来测试预期会失败的情况:

```move
#[test]
#[expected_failure]
fun test_division_by_zero() {
    let _ = 1 / 0;
}
```

5. 使用 `#[test_only]` 注解标记只在测试中使用的辅助函数或结构:

```move
#[test_only]
fun setup_test_coin(account: &signer) {
    // 初始化测试用的代币
}
```


### 2024.09.23
- 继续学习aptos move的单元测试
6. 可以使用 `aptos move test` 命令运行测试:

```
$ aptos move test
```

7. 测试可以访问模块中的私有函数,这有助于更全面的测试覆盖。

8. 可以使用 `--filter` 选项只运行特定的测试:

```
$ aptos move test --filter test_function_name
```

9. 使用 `assert!` 时提供有意义的错误消息,以便更容易调试失败的测试。

10. 考虑边界情况和异常情况,不仅测试正常路径。

### 2024.09.24
 -  [ ] 
### 2024.09.25
 -  [ ] 尝试写一个发红包合约
- 主要功能如下
1. create_red_packet: 创建一个新的红包。创建者指定总金额、红包数量和有效期。
2. claim_red_packet: 允许用户领取红包。每次领取的金额是剩余金额除以剩余数量。
3. refund_red_packet: 允许创建者在红包过期后收回未领取的金额。
- 主要特点:
1. 使用 AptosCoin 作为红包的货币。
2. 红包信息存储在 RedPacket 结构中。
3. 包含基本的错误检查,如余额不足、红包过期、无剩余红包等。
4. 使用 timestamp 模块来处理时间相关的逻辑。
### 2024.09.26
```
module redpacket::redpacket {
    use std::signer;
    use aptos_framework::coin;
    use aptos_framework::aptos_coin::AptosCoin;
    use aptos_framework::timestamp;
    use aptos_framework::account;

    struct RedPacket has key {
        creator: address,
        total_amount: u64,
        remaining_amount: u64,
        total_count: u64,
        remaining_count: u64,
        expiration_time: u64,
    }

    const E_NOT_CREATOR: u64 = 1;
    const E_INSUFFICIENT_BALANCE: u64 = 2;
    const E_EXPIRED: u64 = 3;
    const E_NO_REMAINING: u64 = 4;

    public entry fun create_red_packet(
        creator: &signer,
        total_amount: u64,
        total_count: u64,
        duration: u64
    ) {
        let creator_addr = signer::address_of(creator);
        assert!(coin::balance<AptosCoin>(creator_addr) >= total_amount, E_INSUFFICIENT_BALANCE);

        coin::transfer<AptosCoin>(creator, @redpacket, total_amount);

        let expiration_time = timestamp::now_seconds() + duration;
        
        move_to(creator, RedPacket {
            creator: creator_addr,
            total_amount,
            remaining_amount: total_amount,
            total_count,
            remaining_count: total_count,
            expiration_time,
        });
    }

    public entry fun claim_red_packet(claimer: &signer, creator: address) acquires RedPacket {
        let red_packet = borrow_global_mut<RedPacket>(creator);
        
        assert!(timestamp::now_seconds() <= red_packet.expiration_time, E_EXPIRED);
        assert!(red_packet.remaining_count > 0, E_NO_REMAINING);

        let claim_amount = red_packet.remaining_amount / red_packet.remaining_count;
        
        red_packet.remaining_amount = red_packet.remaining_amount - claim_amount;
        red_packet.remaining_count = red_packet.remaining_count - 1;

        let claimer_addr = signer::address_of(claimer);
        coin::transfer<AptosCoin>(@redpacket, claimer_addr, claim_amount);
    }

    public entry fun refund_red_packet(creator: &signer) acquires RedPacket {
        let creator_addr = signer::address_of(creator);
        let red_packet = borrow_global_mut<RedPacket>(creator_addr);
        
        assert!(creator_addr == red_packet.creator, E_NOT_CREATOR);
        assert!(timestamp::now_seconds() > red_packet.expiration_time, E_EXPIRED);

        if (red_packet.remaining_amount > 0) {
            coin::transfer<AptosCoin>(@redpacket, creator_addr, red_packet.remaining_amount);
            red_packet.remaining_amount = 0;
            red_packet.remaining_count = 0;
        }
    }
}
```
### 2024.09.27
 -  [ ] 

<!-- Content_END -->
