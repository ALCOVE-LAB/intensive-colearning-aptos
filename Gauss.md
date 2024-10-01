---
timezone: Asia/Shanghai
---

> 请在上边的 timezone 添加你的当地时区，这会有助于你的打卡状态的自动化更新，如果没有添加，默认为北京时间 UTC+8 时区
> 时区请参考以下列表，请移除 # 以后的内容

timezone: Pacific/Honolulu # 夏威夷-阿留申标准时间 (UTC-10)

timezone: America/Anchorage # 阿拉斯加标准时间 (UTC-9)

timezone: America/Los_Angeles # 太平洋标准时间 (UTC-8)

timezone: America/Denver # 山地标准时间 (UTC-7)

timezone: America/Chicago # 中部标准时间 (UTC-6)

timezone: America/New_York # 东部标准时间 (UTC-5)

timezone: America/Halifax # 大西洋标准时间 (UTC-4)

timezone: America/St_Johns # 纽芬兰标准时间 (UTC-3:30)

timezone: America/Sao_Paulo # 巴西利亚时间 (UTC-3)

timezone: Atlantic/Azores # 亚速尔群岛时间 (UTC-1)

timezone: Europe/London # 格林威治标准时间 (UTC+0)

timezone: Europe/Berlin # 中欧标准时间 (UTC+1)

timezone: Europe/Helsinki # 东欧标准时间 (UTC+2)

timezone: Europe/Moscow # 莫斯科标准时间 (UTC+3)

timezone: Asia/Dubai # 海湾标准时间 (UTC+4)

timezone: Asia/Kolkata # 印度标准时间 (UTC+5:30)

timezone: Asia/Dhaka # 孟加拉国标准时间 (UTC+6)

timezone: Asia/Bangkok # 中南半岛时间 (UTC+7)

timezone: Asia/Shanghai # 中国标准时间 (UTC+8)

timezone: Asia/Tokyo # 日本标准时间 (UTC+9)

timezone: Australia/Sydney # 澳大利亚东部标准时间 (UTC+10)

timezone: Pacific/Auckland # 新西兰标准时间 (UTC+12)

---

# {你的名字}

1. 自我介绍

我是gauss，希望通过本次共学能学习到更多关于web3的知识
   
2. 你认为你会完成本次残酷学习吗？

我会尽力的:D

# 项目概述：Liquidity_NFT

**项目目标**：将NFT与流动性交换（swap）结合，为用户在提供流动性时生成一个动态NFT，旨在提升用户的投资体验。

**NFT信息内容**：
- **持有时间**：记录用户提供流动性多久。
- **可提取费用**：展示用户能从流动性池中提取的费用数量。
- **LP Token持有比例**：反映用户在流动性池中的份额占比。

**动态更新机制**：
当持有时间、可提取费用或LP Token持有比例满足特定条件时，NFT会自动更新其内容和外观，提供实时反馈。

**用户体验**：
该项目旨在提供直观且互动的投资体验，降低DeFi的学习门槛，通过创新设计激励用户长期参与，同时为NFT赋予更广泛的实用性和交易价值。这种结合不仅增强了用户的参与感，还能提升市场流动性和NFT的市场价值。

操作示例：

1.铸造要使用的FA

我们先[铸造](https://explorer.aptoslabs.com/account/0x71dfdf10572f2d5ba5a66ccbf6e7a785d201fdb4bda312a870deeec3d8fd2f96/modules/run/launchpad1?network=testnet)两种FA各1000个用于提供流动性和进行swap

decimal = 6
- FA1_Metadata: 0x7f2bf107ba43b8f16332aa88d43713b811dc24f4abc8c68bb73ac44613559476
- FA2_Metadata: 0x1c71da02f726fa948d0d790d215401020a701ee5e1968b8329a2fcdb032315ad

[![pA31MUx.png](https://s21.ax1x.com/2024/10/01/pA31MUx.png)](https://imgse.com/i/pA31MUx)

[![pA311PK.png](https://s21.ax1x.com/2024/10/01/pA311PK.png)](https://imgse.com/i/pA311PK)

2.创建流动性池

用这两个FA的Metadata创建流动性池，稳定币选项填false

[![pA3138O.png](https://s21.ax1x.com/2024/10/01/pA3138O.png)](https://imgse.com/i/pA3138O)

3. 添加流动性

填入两种FA的Metadata来确定流动性池，稳定币选项是false，两种代币分别添加100个，以及两种代币分别的期望最小添加数（这是为了保护LP，避免因添加比例不同或其他计算因素导致的添加数量过少）为了方便演示我们填1

[![pA31Q56.png](https://s21.ax1x.com/2024/10/01/pA31Q56.png)](https://imgse.com/i/pA31Q56)

我们减少了对应数量的FA，并获得了 LP Token和 LP NFT

[![pA337ff.jpg](https://s21.ax1x.com/2024/10/01/pA337ff.jpg)](https://imgse.com/i/pA337ff)

4. 用另一个账户添加流动性

切换到另一个账户，这次两种代币分别添加75个，可以看到，由于 LP Token 持有的份额不同，NFT的样式也是不一样的

[![pA33R6e.png](https://s21.ax1x.com/2024/10/01/pA33R6e.png)](https://imgse.com/i/pA33R6e)

5. 进行swap

填入要进行swap的数量100，期望最小收到代币的值1，源代币Metadata，目标代币Metadata，稳定币选项false，接收人地址

[![pA33WOH.png](https://s21.ax1x.com/2024/10/01/pA33WOH.png)](https://imgse.com/i/pA33WOH)

继续进行swap使LP的手续费快速累积，当可提取的手续费达到一定阈值的时候，NFT的样式也会改变（你可以一眼看出你获得的手续费已经积累了很多了）

[![pA336fK.jpg](https://s21.ax1x.com/2024/10/01/pA336fK.jpg)](https://imgse.com/i/pA336fK)

6. 移除流动性

移除所有的 LP Token

[![pA332lD.png](https://s21.ax1x.com/2024/10/01/pA332lD.png)](https://imgse.com/i/pA332lD)

LP Token为0时，LP NFT 也被销毁了

[![pA33yY6.png](https://s21.ax1x.com/2024/10/01/pA33yY6.png)](https://imgse.com/i/pA33yY6)



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

在Aptos区块链中，账户代表对一组资产（如链上货币和NFT）的访问控制。这些资产由Move语言中的一种原语（称为资源）表示，强调了访问控制和稀缺性。

**账户类型和特点**

标准账户：对应于一个地址和公钥/私钥对的普通账户。

资源账户：不与任何私钥相关的自主账户，用于开发者存储资源或发布链上模块。

对象：在单一地址内存储的一组复杂资源，表示单个实体。

Aptos中的账户是显式的，需要在执行交易之前被创建。

账户创建可以通过显式调用或通过向账户地址转入Aptos代币（APT）进行隐式创建。

**账户的独特功能**

旋转认证密钥：账户的认证密钥可以更改为由不同的私钥控制，类似于Web2世界中的更改密码。

原生多重签名支持：支持k-of-n多重签名，使用Ed25519和Secp256k1 ECDSA签名方案。

**账户地址**

Aptos中的账户地址是32字节的十六进制字符串，通常显示为64个十六进制字符。

支持使用Aptos Name Service来获取.apt域名，使账户更易于识别和记忆。

**创建账户的步骤**

选择认证方案（如Ed25519或Secp256k1 ECDSA）。

生成新的私钥和公钥对。

将公钥与认证方案结合生成32字节的认证密钥和账户地址。

使用私钥为该账户签署交易。

**认证密钥**

初始的账户地址设为在账户创建时生成的认证密钥。

认证密钥可以在生成新的公私钥对时更改，但账户地址不会改变。

Aptos支持多种认证方案，包括Ed25519、Secp256k1 ECDSA、K-of-N多重签名和多Ed25519方案（遗留方案）。

**多重签名与通用认证**

K-of-N多重签名：有N个签名者，至少K个签名用于认证交易。

通用认证：支持Ed25519和Secp256k1 ECDSA认证方案，允许多种密钥组合。

**密钥旋转**

Aptos账户可以通过account::rotate_authentication_key函数更换密钥，以防止已泄露的密钥被滥用。

**账户状态**

每个账户的状态由代码（Move模块）和数据（Move资源）组成。

Move模块：包含代码（如类型和过程声明），但不包含数据。

Move资源：包含数据，但不包含代码，表示区块链上的全局状态更新规则。

**访问控制与签名者**

在Aptos Move中，交易的发送者由signer表示。signer参数在Move模块的函数中用于访问控制，确保只有授权的账户才能执行某些操作。


### 2024.09.09


**费用组成**  

在Aptos区块链上，交易执行需要支付两部分费用：  

执行和IO成本：这部分费用用于支付交易的瞬时计算资源（如处理交易和在主网上的传播）。该费用以Gas Units（Gas单位）表示，价格会根据网络负载浮动。这部分Gas费用在交易执行后永久销毁。  

存储费用：这部分费用用于持久存储已验证的记录，以固定的APT价格表示，不会随网络负载而波动。存储费用在分配的存储空间被删除时可以退还，目前配置为退还整个生命周期内支付的存储费用。  

**Gas单位与价格**  

Gas单位：表示交易中消耗的瞬时资源的基本单位（如计算或存储访问）。  

Gas价格：用APT（Aptos原生代币）及其子单位Octas表示。总Gas消耗量取决于交易的复杂度。  

**费用明细**  

费用的详细信息通过0x1::transaction_fee::FeeStatement结构体表示，包含以下字段：  

total_charge_gas_units：总Gas费用  

execution_gas_units：执行Gas费用  

io_gas_units：IO Gas费用  

storage_fee_octas：存储费用  

storage_fee_refund_octas：存储费用退款  

**Gas费用与交易优先级**  

Aptos网络通过设置最低Gas单位价格来管理交易费用，市场决定了特定Gas价格的交易被处理的速度。  

提高Gas单位价格可以增加交易的优先级，但仅限于下一个区块的选择。  

在区块内，交易执行的顺序是由系统决定的，并基于交易随机化以提高并行执行效率。  

**交易中指定Gas费用**  

交易需要包含以下Gas字段：  

max_gas_amount：发送方愿意支付的最大Gas单位数。  

gas_price：每个Gas单位的价格，以Octas表示。  

如果消耗的总Gas数量超过max_gas_amount，交易将中止执行。

**存储费用和删除退款**  

存储费用：根据在全局状态中分配的新槽数量和现有槽的大小增长收取。 

存储删除退款：如果删除了状态项，当前配置为退还所有已支付的存储费用。  

**估算Gas消耗**  

可以通过链上模拟或本地使用Aptos CLI的Gas分析功能来估算交易的Gas消耗。结果是估计值，需在实际交易中留出安全余量。  

### 2024.09.10

在Aptos区块链上，链上状态以资源（resources）和模块（modules）进行组织，这些元素存储在各个账户中。这与其他区块链（例如以太坊）不同，在以太坊上，每个智能合约都有自己的存储空间。

**资源与实例的区别**

- 资源（Resources） 是具有key能力的结构体实例（struct instances），它们存储在全局存储或直接在账户中。

- 实例（Instances） 是由Move模块定义的结构体定义，可能包含key或store等能力。

- - key能力允许资源存储在全局存储或账户内。

- - store能力允许结构体实例存储在资源中。例如，CoinStore是一个包含APT代币的资源，而Coin是一个实例。

**定义资源和对象**

所有实例和资源都在一个模块中定义，并存储在一个地址下。例如：

- 0x1234::coin::Coin<0x1234::coin::SomeCoin> 表示在地址0x1234下的模块coin中定义的Coin结构体。

使用虚类型（phantom type）允许存在许多不同类型的CoinStore资源，每种资源具有不同的CoinType参数。

**实例（包括资源）的权限**

- 资源和其他实例的权限由定义结构体的模块决定。虽然可以访问并移除资源中的实例，但无法在未经模块许可的情况下更改实例的内部状态。

- 所有权则由资源存储在账户下或由定义结构体的模块逻辑决定。

**查看资源**

- 资源存储在账户中，可以通过在资源的完整查询路径中搜索拥有账户以及其地址和模块来定位资源。

- 资源可以在Aptos Explorer上查看或直接从全节点的API中获取。

**资源的存储方式**

- 定义结构体的模块指定了实例的存储方式。例如，存储代币的事件可以保存在接收账户或代币模块部署的账户中。

- 在单个用户账户中存储数据可以提高执行效率，因为不同账户之间的交易不会产生状态读写冲突，从而实现并行执行。

### 2024.09.11

Aptos 区块链数据的关键组成部分

**数据类型:**

交易（Transactions）: 表示由账户在区块链上执行的操作，例如资产转移。

状态（States）: 代表当前的账本状态，即所有已执行交易的结果，包括存储在资源中的值。

事件（Events）: 执行交易时生成的附加数据。

**交易（Transactions）:**

Aptos 交易包含发送者地址、认证信息、要执行的操作、所愿支付的 gas 费用等细节。

**交易状态：**

已提交并执行: 交易成功执行并记录在区块链上。

已提交但中止: 交易被记录但由于中止码而失败。

提交时被丢弃: 交易因 gas 不足、格式无效或密钥错误等原因未通过验证。

提交后被丢弃: 交易因超时或其他因素被丢弃。

所有已提交的交易将向发送者账户收取 gas 费用。

**交易内容:**

交易包含签名、发送者地址、公钥、有效载荷、gas 参数、序列号、过期时间等信息。

有效载荷类型：

入口点（Entry Point）: 直接调用特定函数。

脚本有效载荷（Script Payload）: 允许通过调用多个模块中的函数进行更复杂的操作。

**状态（States）:**

账本状态（全球状态）代表 Aptos 区块链上所有账户的状态。

交易通过生成输出（包括操作写入集和事件向量）来修改全球状态。

状态是版本化的，允许验证者跟踪状态变化并响应当前或过去账本状态的查询。

**证明和数据验证:**

Aptos 使用加密证明来验证数据的真实性。

区块链的数据在网络中复制，每次交易执行都会向梅克尔树（Merkle Tree）添加新的叶子，允许进行加密验证。

这些证明确保验证者对状态的共识，并允许客户端在不信任数据来源的情况下验证数据完整性。

**版本化数据库:**

使用无符号 64 位整数来跟踪账本状态的版本（系统执行的交易数量）。

允许在最新状态下执行交易，并提供历史账本数据。

**交易流程与状态变化:**

每个交易的执行遵循一个确定性函数（Apply()），确保状态转换的一致性。

### 2024.09.11

### 创建和配置对象

创建对象涉及两个步骤：

1. **创建对象核心资源组**（有一个地址可供后续引用）。
2. **配置对象的行为**，通过称为 Refs 的权限。

配置对象生成 Refs 必须在创建时完成，之后无法更改。

### 创建对象的三种类型

1. **普通对象**：可删除，具有随机地址。使用 `0x1::object::create_object(owner_address: address)` 创建。
   
   ```move
   entry fun create_my_object(caller: &signer) {
       let caller_address = signer::address_of(caller);
       let constructor_ref = object::create_object(caller_address);
   }
   ```

2. **命名对象**：不可删除，具有确定性地址。使用 `0x1::object::create_named_object(creator: &signer, seed: vector<u8>)` 创建。

   ```move
   const NAME: vector<u8> = b"MyAwesomeObject";
   entry fun create_my_object(caller: &signer) {
       let caller_address = signer::address_of(caller);
       let constructor_ref = object::create_named_object(caller, NAME);
   }
   ```

3. **粘性对象**：不可删除，具有随机地址。使用 `0x1::object::create_sticky_object(owner_address: address)` 创建。

   ```move
   entry fun create_my_object(caller: &signer) {
       let caller_address = signer::address_of(caller);
       let constructor_ref = object::create_sticky_object(caller_address);
   }
   ```

### 定制对象功能

创建对象后，可以使用 `ConstructorRef` 生成额外的 Refs，以启用/禁用对象功能，如转移资源、转移对象或删除对象。

#### 添加资源

使用 `ConstructorRef` 生成一个签名者，允许将资源转移到对象中。

```move
entry fun create_my_object(caller: &signer) {
    let object_signer = object::generate_signer(&constructor_ref);
    move_to(&object_signer, MyStruct { num: 0 });
}
```

#### 添加可扩展性（ExtendRef）

生成 `ExtendRef` 以允许对象在未来进行编辑，控制权限可以通过智能合约逻辑实现。

```move
entry fun add_message(caller: &signer, object: Object<MyStruct>, message: String) acquires ObjectController {
    let extend_ref = borrow_global<ObjectController>(object_address).extend_ref;
    let object_signer = object::generate_signer_for_extending(&extend_ref);
    move_to(object_signer, Message { message });
}
```

#### 禁用/切换转移（TransferRef）

默认情况下，所有对象都是可转移的。通过 `TransferRef` 可以管理转移权限。

```move
entry fun toggle_transfer(caller: &signer, object: Object<ObjectController>) acquires ObjectController {
    let transfer_ref = borrow_global<ObjectController>(object_address).transfer_ref;
    if (object::ungated_transfer_allowed(object)) {
        object::disable_ungated_transfer(&transfer_ref);
    } else {
        object::enable_ungated_transfer(&transfer_ref);
    }
}
```

#### 一次性转移（LinearTransferRef）

生成一次性使用的 `LinearTransferRef` 以实现“灵魂绑定”对象的功能。

```move
entry fun transfer(caller: &signer, object: Object<ObjectController>, new_owner: address) acquires ObjectController {
    let linear_transfer_ref = option::extract(&mut object_controller.linear_transfer_ref);
    object::transfer_with_ref(linear_transfer_ref, new_owner);
}
```

#### 允许删除对象（DeleteRef）

对可删除对象生成 `DeleteRef` 以便后续使用，帮助清理存储。

```move
entry fun delete(caller: &signer, object: Object<ObjectController>) {
    let delete_ref = move_from<ObjectController>(object_address).delete_ref;
    object::delete(delete_ref);
}
```

#### 使对象不可变

通过将合约关联的对象设为不可变，移除扩展或变更对象的能力。

### 2024.09.13

Move语言有两种类型的程序：模块（Modules）和脚本（Scripts）。模块是定义结构类型和操作这些类型的函数的库，而脚本是可执行的入口点，类似于传统语言中的main函数。

1. 模块（Modules）

定义：模块定义结构类型（struct）和操作这些类型的函数。结构类型定义了Move全局存储的模式，模块函数定义了更新存储的规则。

语法：模块的语法为：

```move
module <address>::<identifier> {
    (<use> | <friend> | <type> | <function> | <constant>)*
}
```

<address> 是有效的命名地址或字面地址。
   
内容：模块可以包含use（用于导入其他模块的类型）、friend（信任模块列表）、struct（结构类型）、function（函数）和constant（常量）等。

发布：模块会存储在全局存储中。

2. 脚本（Scripts）

定义：脚本是一个可执行的入口点，通常调用已发布模块的函数来执行对全局存储的更新。脚本是临时代码片段，不会存储在全局存储中。

语法：脚本的结构为：

```move
script {
    <use>*
    <constants>*
    fun <identifier><[type parameters: constraint]*>([identifier: type]*) <function_body>
}
```

脚本块必须从所有的use声明开始，然后是常量声明，最后是主函数的声明。

主函数可以有任意名称、参数数量，但不能返回值。

4. 命名地址

在源语言级别和编译期间可以使用命名地址（例如example_addr）。这些地址在字节码级别会被替换为实际的地址值。

命名地址允许在源代码中以更加语义化的方式管理模块地址。

5. 其他注意事项

模块名称通常以小写字母开头，并保存在相同名称的.move源文件中。

模块中的元素（use、friend、struct、function、constant）可以按任意顺序出现。

### 2024.09.14

Move语言支持六种无符号整数类型：u8、u16、u32、u64、u128 和 u256，每种类型的取值范围从0到相应类型的最大值，具体如下：

类型	  取值范围
u8	   0 到 2^8 - 1
u16	0 到 2^16 - 1
u32	0 到 2^32 - 1
u64	0 到 2^64 - 1
u128	0 到 2^128 - 1
u256	0 到 2^256 - 1

**字面量**

整数字面量可以直接指定（如 112），也可以用十六进制表示（如 0xFF）。可以在数字后添加类型后缀（如 112u8）来指定类型，如果未指定类型，编译器会根据上下文推断，推断失败时默认类型为 u64。

字面量支持通过下划线分隔增加可读性（如 1_000u128）。

如果字面量超出了指定类型的取值范围，将会报错。

**运算操作**

整数类型支持多种运算，包括算术、位运算、位移、比较和相等性检查。每种运算的左右操作数必须是相同的整数类型，否则需要进行类型转换。算术操作如果发生溢出、下溢或除以0等情况会导致程序中止。

算术运算（可能中止）

+：加法（结果超出类型范围会中止）

-：减法（结果小于0时中止）

*：乘法（结果超出类型范围会中止）

%：取模（除数为0时中止）

/：整数除法（除数为0时中止）

位运算（不会中止）

&：按位与

|：按位或

^：按位异或

位移运算（可能中止）

<<：左移（移位数超过类型位数时中止）

>>：右移（移位数超过类型位数时中止）
>>
比较运算（不会中止）

<：小于

>：大于

<=：小于等于

>=：大于等于

**相等性检查**

所有整数类型支持相等性运算（==、!=）。运算数必须是相同类型，或者通过类型转换使其匹配。

**类型转换**

整数类型之间支持显式类型转换，如 x as u8。转换过程中不会截断数据，如果转换结果超出目标类型范围则会中止。

**复制**

整数是隐式可复制的类型，即不需要显式的指令就可以复制整数值。

### 2024.09.15

创建对象
**有三种类型的对象可以创建：**
1. **普通对象**：可删除，具有随机地址，使用 `create_object` 创建。
2. **命名对象**：不可删除，具有确定地址，使用 `create_named_object` 创建。
3. **粘性对象**：不可删除，具有随机地址，使用 `create_sticky_object` 创建。

**使用 Refs 配置对象行为**
对象创建后，可以通过 **Refs** 来控制其行为，如转移资源、转移对象或删除对象。Refs 需要在对象创建过程中生成，常见的 Refs 包括：
1. **ConstructorRef**：不能存储；在对象创建期间用于生成其他 Refs。
2. **TransferRef**：控制对象的可转移性，允许或限制未来的转移操作。
3. **LinearTransferRef**：提供一次性转移功能，用于创建类似“灵魂绑定”的对象。
4. **ExtendRef**：允许对象在创建后进行修改或扩展。
5. **DeleteRef**：允许删除对象（仅适用于可删除对象）。

**对象配置的特性**
1. **添加资源**：使用 `generate_signer` 与 `move_to` 将资源转移到对象中。
2. **禁用/启用转移**：通过 TransferRef 控制对象的可转移性，允许或永久禁用转移。
3. **允许一次性转移**：LinearTransferRef 使得对象只能被转移一次。
4. **删除对象**：可删除的对象可以通过 DeleteRef 被移除。
5. **使对象不可变**：可以通过禁止修改或扩展，使对象不可变。

**权限控制**
通过智能合约逻辑控制权限，允许不同实体执行操作，如添加资源、扩展对象、切换转移功能等。

### 2024.09.16

1. **使用对象作为入口函数参数**
- 对象可以作为函数参数传递。对象类型为 `Object<T>`，其中 `T` 是对象所拥有的资源类型。所有对象都有一个 `ObjectCore` 类型，存储对象的元数据。
- 可以传递对象的地址或引用，在运行时合约会验证该地址上的对象是否存在，并且该对象是否存储了类型 `T` 的资源。

2. **对象类型转换**
- 可以通过 `address_to_object` 函数将一个地址转换为对象，也可以使用 `convert<T>` 在不同的对象类型之间转换，前提是这些资源在对象中存在。

3. **对象的所有权管理**
- 对象可以由任何地址拥有，包括账户、资源账户以及其他对象。验证所有权时，可以检查对象是否由某个账户、资源账户或其他对象拥有。
- 提供了检查函数，如 `object::is_owner`、`object::owns`，可以用于验证所有权链，例如嵌套的对象所有权。

4. **对象的转移**
- 对象默认是可转移的，使用 `object::transfer` 可以将对象转移到另一个地址或对象。
- 如果对象的 `ungated_transfer` 被禁用，则所有的转移操作需要使用 `TransferRef` 或 `LinearTransferRef` 权限进行。

5. **对象中的事件**
- 默认情况下，对象只有 `TransferEvent`，即对象被转移时触发的事件。
- 可以为对象创建更多的事件句柄，例如 `create_guid` 和 `new_event_handle`，并将这些事件句柄分配给对象。

6. **对象的修改与销毁**
- 对象通常只能使用创建时生成的 Refs 进行修改（如扩展资源、删除对象等）。通过 `burn_object` 可以将对象标记为 "burnt" 状态，以隐藏它不再显示在钱包中。也可以通过 `unburn_object` 恢复对象的显示状态。

### 2024.09.17

Aptos 可替代资产标准（Fungible Asset，简称 FA）为 Move 生态系统提供了定义可替代资产的标准和类型安全的方式，取代了以前的 coin 模块。FA 标准允许无缝铸造、转移和自定义各种用途的可替代资产，如货币和真实世界资产（RWA）。它具有更强的自定义能力，并能确保去中心化应用（dApp）一致识别和处理这些资产。

**FA 标准通过两个 Move 对象实现：**
1. **Object<Metadata>**：表示资产的元数据，如名称、符号和小数点位数。
2. **Object<FungibleStore>**：存储账户所拥有的资产数量。

**FA 标准的优势：**
- 与 coin 模块相比，FA 更具自定义性，支持通过智能合约扩展。
- 自动跟踪账户资产余额，无需额外注册资源。

**创建 FA 资产步骤：**
1. 创建不可删除的 Object 持有元数据。
2. 生成权限 Refs，如铸币权限（MintRef）、转移权限（TransferRef）和销毁权限（BurnRef）。
3. 铸造和转移资产。

**事件与操作：**
- **提现**：从主存储取出资产。
- **存款**：向主存储存入资产。
- **转移**：将资产从一个账户转移到另一个账户。
- **余额查询**：检查账户的资产余额。
- **冻结状态查询**：检查账户是否被冻结。

**高级功能：可调度资产**

FA 还支持自定义存取钩子函数，允许资产发行者实现自定义的存取逻辑。

**迁移**

FA 标准兼容 coin 模块，旧的 coin 模块将自动迁移至 FA，并为其创建相应的元数据。

### 2024.09.18

**Global Storage - 全局存储结构**

Move 程序的设计是为了访问和操作树形的持久化全局存储。全局存储由账户地址为根的树形结构组成，每个地址可以存储资源数据值和模块代码。每个地址最多只能存储一个特定类型的资源值和一个特定名称的模块。

**Global Storage - 操作符**

Move 程序可以通过以下五种指令操作全局存储中的资源：
1. `move_to<T>(&signer, T)`：将类型为 T 的资源存储到 `signer.address`，如果该地址已存储了 T 类型资源，则操作中止。
2. `move_from<T>(address): T`：从指定地址移除并返回 T 类型资源，地址上没有 T 则操作中止。
3. `borrow_global_mut<T>(address): &mut T`：返回地址上 T 类型资源的可变引用，若资源不存在则中止。
4. `borrow_global<T>(address): &T`：返回地址上 T 类型资源的不可变引用，若资源不存在则中止。
5. `exists<T>(address): bool`：判断某地址是否存储了 T 类型资源。

所有这些操作都依赖于 `T` 这个类型参数，且必须在当前模块中声明。

**返回全局资源的引用限制**

Move 禁止函数返回指向全局存储的引用，以确保不会出现悬挂指针（dangling references）的问题，保证引用的安全性。

**全局存储操作与泛型**

Move 允许全局存储操作支持泛型，通过类型参数来操作泛型资源。这被称为存储多态性（storage polymorphism）。

**Counter 计数器模块**

该模块展示了如何使用五种全局存储操作：

- 发布计数器资源到账户。
- 读取、检查某个地址的计数器资源是否存在，并可以增加或重置计数器值。
- 删除计数器资源并返回其值。

**acquires注解**

Move 函数如果操作了全局资源（使用 `move_from`、`borrow_global` 或 `borrow_global_mut`），必须使用 `acquires` 注解来声明。这用于保证函数对资源的安全访问，防止悬挂引用问题。

**悬挂引用安全**

Move 通过类型系统和 `acquires` 注解来避免全局存储中出现悬挂引用的情况。如果在获取全局资源引用后删除资源，Move 的类型系统将阻止该程序编译通过。

**存储操作的索引表示法**

Move 2.0 引入了简化存储操作的索引表示法，可以用类似数组下标的方式来访问全局存储中的资源，简化了对资源的借用与修改操作。

### 2024.09.19

泛型（Generics），即通过参数化多态性定义函数和结构体，使其能够处理不同的数据类型。

1. **泛型声明**：函数和结构体可以使用泛型参数（Type Parameters），通过在函数名或结构体名后加上尖括号 `<...>` 来声明。泛型允许代码适用于多种数据类型。

2. **泛型函数**：可以使用泛型参数编写适用于任意数据类型的函数，例如身份函数 `id<T>(x: T): T`，其中 `T` 是类型参数。

3. **泛型结构体**：结构体也可以通过泛型参数使字段使用不同类型。结构体内的字段类型可以是泛型参数，或者是泛型参数的组合形式。

4. **类型参数的使用**：当调用泛型函数或构造泛型结构体时，可以指定类型参数，但 Move 语言的类型推断机制通常会自动推断类型，减少显式标注的需要。

5. **类型参数不匹配**：如果类型参数与实际提供的数据类型不匹配，Move 会报错。

6. **幽灵类型参数（Phantom Type Parameters）**：如果泛型参数没有参与结构体的能力派生，或者只是用作其他幽灵参数的类型参数，可以将其标记为幽灵类型参数。这样可以避免不必要的能力限制。

7. **泛型约束**：通过在类型参数上添加约束（如 `copy`、`drop` 等），可以指定类型需要具备的能力，确保类型系统可以安全地执行某些操作。

8. **递归限制**：虽然 Move 支持泛型函数的递归调用，但禁止泛型结构体包含自身或其他结构体的字段，避免无限类型递归。

### 2024.09.20

Aptos区块链支持Move模块的升级，这允许代码所有者和开发者在一个稳定的账户地址下更新和进化合约。模块升级后，所有使用该模块的用户在下次交互时将自动获得最新版本的代码。

#### 升级策略

Aptos原生支持不同的升级策略，允许Move开发者明确定义代码升级的限制。默认策略是**向后兼容**的，这意味着只有在保证现有资源存储和公共API不被破坏的前提下，升级才会被接受。Move的强类型字节码语义使得这种兼容性检查成为可能。

尽管兼容升级能确保不破坏现有代码，开发者仍需谨慎依赖第三方升级，因为升级可能会影响应用的正常运行，尤其是在模块语义发生变化时。

#### 升级方式

Move代码的升级发生在包（package）层面。升级策略在`Move.toml`文件中定义。例如：

```toml
[package]
name = "MyApp"
version = "0.0.1"
upgrade_policy = "compatible"
```

Aptos会在发布新代码时检查兼容性，若不兼容则事务会中止。

#### 两种升级策略

1. **compatible（向后兼容）**：必须保证旧的结构体声明保持不变，且公共函数的签名不变。
   
2. **immutable（不可变）**：代码无法升级，确保永久保持不变。

策略只能变得更严格，不能变得更弱。例如，**不可变包**不能依赖于**可兼容包**。

#### 兼容性规则

在兼容升级中：
- 现有结构体的字段不能更改。
- 公共和入口函数的签名不能更改，参数名称可以更改。
- `public(friend)` 函数被视为私有函数，可以随意更改其签名。

#### 安全注意事项

依赖可升级包可能带来风险，包括Bug或恶意升级的影响。最安全的做法是依赖**不可变包**，因为它们不会发生变化。对可兼容包的依赖需要特别小心，最好确保该包由去中心化自治组织（DAO）管理。

#### 编程化升级

Aptos通过 `aptos_framework::code` 模块支持在智能合约中发布代码，但代码在当前事务结束前不会被执行。

### 2024.09.21

Aptos的数字资产（DA）标准是一个现代化的非同质化代币（NFT）标准，旨在替代之前的Aptos Token标准。该标准允许NFT作为独特资产存储在链上，并可以在集合中进行管理。与旧标准相比，主要改进包括：

1. **代币扩展性**：由于使用Move Objects实现，代币可以轻松扩展。
2. **直接NFT转移**：无需接收者在链上“选择加入”即可直接转移NFT。
3. **NFT可组合性**：NFT可以拥有其他NFT，实现简单的组合功能。

该标准使用两个对象来实现：**Collections**（集合）和**Tokens**（代币）。代币通常用URI链接指向相关的资产信息（如图像或视频）。代币必须引用其父集合，但父集合并不拥有代币。

### 集合（Collections）

集合有描述、名称、版税和URI等字段，可以是固定供应量或无限供应量的集合。集合创建后，最大供应量不可更改。集合是Move对象，可以通过生成权限Ref来修改特定字段。

### 代币（Tokens）

代币有描述、名称、版税和URI等字段。创建代币有两种方式：命名代币和未命名代币。命名代币地址可通过字符串拼接和哈希计算得出，而未命名代币地址需要通过Aptos Indexer查找。

代币可以转移、燃烧（删除）和修改。修改代币的URI或描述需要生成MutatorRef，并在代币创建时储存。对于扩展需求，可以为代币添加额外的资源或使用Refs来修改对象。

### aptos_token模块

对于不想编写自定义逻辑的NFT创建者，Aptos提供了aptos_token模块，可以用来轻松铸造、管理和转移NFT。该模块支持代币的版税设置、魂绑定（Soulbound）代币的铸造等功能，但不能扩展代币的功能。

### 2024.09.22

Aptos 提供了一个 React Provider 和 Context，用于将 Aptos 钱包连接到 DApp。这个 Provider 允许开发者指定要支持的钱包，能够查询账户信息以及签署交易和消息，提供了一个标准接口来支持所有 Aptos 钱包，并且通过更新 Wallet Adapter 的依赖版本，能够轻松支持新钱包。

主要步骤包括：

1. 安装 @aptos-labs/wallet-adapter-react。
2. 如果要支持“Legacy Standard Compatible”钱包，需安装对应插件；而符合 AIP-62 标准的钱包不需要额外安装插件。
3. 在代码中导入 Aptos Wallet Adapter 以及任何遗留标准钱包的插件。
4. 初始化 `AptosWalletAdapterProvider`，建议设置 `autoConnect` 为 `true`，并在 `plugins` 中添加非 AIP-62 标准的钱包。

开发者还可以选择使用不同的 UI 包，如 Ant Design、MUI 或 shadcn/ui 来简化钱包选择器的创建。

`useWallet` 提供了一些字段和函数，用于获取账户信息、网络状态以及执行钱包操作，包括连接、断开、签署交易、提交交易、签署消息、切换网络等。

### 2024.09.23

Move语言中的 `vector<T>` 是唯一的原生集合类型，它是一个同质集合，可以通过在末端添加或移除元素来动态增长或缩减。`vector<T>` 可以使用任意类型 `T` 进行实例化，如 `vector<u64>`、`vector<address>` 等。

### Vector字面量：

- 空Vector: `vector[]`，表示空的 `vector<T>`。
- 非空Vector: `vector[e1, ..., en]`，表示包含n个元素的向量。

使用字面量时，类型可以通过元素推断，也可以显式指定类型，如 `vector<u8>[]`。

#### 字节数组字面量：

- `vector<u8>` 常用于表示字节数组，比如公钥或哈希值。
- 支持两种特殊字面量：**字节字符串**（如 `b"Hello!"`）和 **十六进制字符串**（如 `x"48656C6C6F210A"`）。

### Vector的操作：

Move标准库的 `std::vector` 模块提供了一些常用操作：

1. **创建和检查空向量**：

   - `vector::empty<T>()`：创建空向量。
   - `vector::is_empty<T>(self: &vector<T>)`：检查向量是否为空。

3. **增删操作**：

   - `vector::push_back<T>(self: &mut vector<T>, t: T)`：向末尾添加元素。
   - `vector::pop_back<T>(self: &mut vector<T>)`：移除并返回最后一个元素。

4. **访问和修改**：

   - `vector::borrow<T>(self: &vector<T>, i: u64)`：返回第i个元素的不可变引用。
   - `vector::borrow_mut<T>(self: &mut vector<T>, i: u64)`：返回第i个元素的可变引用。
   - `vector::swap<T>(self: &mut vector<T>, i: u64, j: u64)`：交换向量中两个索引位置的元素。

5. **销毁和拼接**：
   
   - `vector::destroy_empty<T>(self: vector<T>)`：销毁一个空向量。
   - `vector::append<T>(self: &mut vector<T>, other: vector<T>)`：将另一个向量的元素添加到当前向量末尾。

### 索引操作（Move 2.0）：

支持通过方括号进行索引操作，简化了语法，例如：
- `&v[i]` 等价于 `vector::borrow(&v, i)`。
- `v[i] = x` 等价于 `*vector::borrow_mut(&mut v, i) = x`。

### 特殊行为：

- 如果向量中的元素类型不支持 `drop`，则必须显式销毁向量，不能隐式丢弃。
- 只有当元素类型支持 `copy` 时，向量才能被复制。

### 2024.09.24

https://github.com/WGB5445/teach-aptos-project/tree/main/aptos-object-nft

### 2024.09.25

在 Aptos 的 TypeScript SDK 中，有多种方式可以创建和管理账户：

### 生成账户凭证的方式：
1. **`Account.generate()`**：最常用的方式，默认生成 ED25519 签名方案的密钥对，可以指定其他签名方案，如 Secp256k1Ecdsa 和 Ed25519。

   ```typescript
   const account = Account.generate(); // 默认使用 Legacy Ed25519
   const account = Account.generate({ scheme: SigningSchemeInput.Secp256k1Ecdsa }); // 使用 Secp256k1
   const account = Account.generate({ scheme: SigningSchemeInput.Ed25519, legacy: false }); // 使用 Single Sender Ed25519
   ```

3. **`Account.fromPrivateKey()`**：从私钥导出账户，支持 Legacy 和 Single Sender 两种 Ed25519 签名方案，以及 Secp256k1 签名方案。

   ```typescript
   const privateKey = new Ed25519PrivateKey(privateKeyBytes);
   const account = Account.fromPrivateKey({ privateKey }); // 使用 Legacy Ed25519

   const account = Account.fromPrivateKey({ privateKey, legacy: false }); // 使用 Single Sender Ed25519

   const privateKey = new Secp256k1PrivateKey(privateKeyBytes);
   const account = Account.fromPrivateKey({ privateKey }); // 使用 Secp256k1
   ```

4. **`Account.fromDerivationPath()`**：根据派生路径和助记词生成账户，同样支持多种签名方案。

   ```typescript
   const account = Account.fromDerivationPath({ path, mnemonic, scheme: SigningSchemeInput.Ed25519 }); // 使用 Legacy Ed25519

   const account = Account.fromDerivationPath({ path, mnemonic, scheme: SigningSchemeInput.Ed25519, legacy: false }); // 使用 Single Sender Ed25519

   const account = Account.fromDerivationPath({ path, mnemonic, scheme: SigningSchemeInput.Secp256k1Ecdsa }); // 使用 Secp256k1
   ```

### 账户的其他表示方式：
可以使用私钥或派生路径等信息创建 `Account` 对象，并通过 SDK 管理这些凭证。

### 账户资金：
生成账户后，需要为其注资才能在网络上激活。在测试环境中可以通过 `faucet` 为账户注资：

```typescript
const transaction = await aptos.fundAccount({
  accountAddress: account.accountAddress,
  amount: 100,
});
```

该SDK支持AIP-55标准，提供 Legacy（ED25519 和 MultiED25519）和 Unified（SingleSender 和 MultiSender）认证方式。

### 2024.09.26

1. **作为函数参数**：对象可以作为entry函数的参数，类型为`Object<T>`，在运行时会验证对象的存在和类型。

2. **对象类型**：可以通过`address_to_object`和`convert<T>`函数进行对象类型转换。

3. **结构体中的对象**：可以将对象嵌入结构体中，表示复杂类型。

4. **所有权验证**：在修改对象之前，需要确认调用者是否为对象的所有者，可以通过多种方法验证所有权。

5. **转移所有权**：对象默认可转移，但可以通过生成的`TransferRef`或`LinearTransferRef`来管理转移权限。

6. **事件**：对象转移时会触发`TransferEvent`，可以扩展其他事件。

7. **修改对象**：对象的修改通常需要在创建时生成的Refs，无法在创建后更改对象的基本属性。

### 2024.09.27

### 项目概述：Liquidity_NFT

**项目目标**：将NFT与流动性交换（swap）结合，为用户在提供流动性时生成一个动态NFT，旨在提升用户的投资体验。

**NFT信息内容**：
- **持有时间**：记录用户提供流动性多久。
- **可提取费用**：展示用户能从流动性池中提取的费用数量。
- **LP Token持有比例**：反映用户在流动性池中的份额占比。

**动态更新机制**：
当持有时间、可提取费用或LP Token持有比例满足特定条件时，NFT会自动更新其内容和外观，提供实时反馈。

**用户体验**：
该项目旨在提供直观且互动的投资体验，降低DeFi的学习门槛，通过创新设计激励用户长期参与，同时为NFT赋予更广泛的实用性和交易价值。这种结合不仅增强了用户的参与感，还能提升市场流动性和NFT的市场价值。




<!-- Content_END -->
