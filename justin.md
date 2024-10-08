---
timezone: Asia/Shanghai
---

---

# justin

1. 自我介绍 <br>
   我是justin
2. 你认为你会完成本次残酷学习吗？<br>
   可以

Aptos 殘酷共學營項目提交情況表:

請填寫共學倉庫 Repo 中的個人 markdown 文件名:
justin

請填寫參與共學的 Github 賬戶
fantasyni

請填寫一個屬於您自己的 ETH 地址
0xC91d7d862EaEF5472513d376497b9015C82e7374

請填寫一個屬於您自己的 APT 地址
0x9b2916b5f46b5600d72c3a32624794d05bbad5e50de62853baeaad97887c386d

請填寫項目名稱:
wormhole-aptos-native-token-transfer

請填寫項目詳情:
wormhole ntt aptos 合约实现

請填寫項目 Github 與相關鏈接:
https://github.com/fantasyni/wormhole-aptos-native-token-transfer

對共學、學習方式、目標、Aptos 文檔等建議:
暂无

## Notes

<!-- Content_START -->

### 2024.09.06
了解Aptos残酷共学的规则，并报名。

### 2024.09.07
参与了aptos 101会议分享，了解了大致学习资料和内容

### 2024.09.08

学习aptos文档 https://aptos.dev/en/network/blockchain

### 2024.09.09

学习 aptos 账户

aptos 账户
有两个first-class features
1. 更改认证密钥 类似于web2的改密码
2. 原生多签支持

三种类型的账户
1. 标准账户 Standard account
带有public/private keys
2. Resource账户
没有private key，开发者用来存储资源或者发布模块到链上
3. Object
一系列资源存储在一个地址上

### 2024.09.10
Signer 里面有一个address
module 0x1::signer {
    struct signer has drop { a: address }
}

signer::address_of(&signer): address
signer::borrow_address(&signer): &address

Global Storage
move_to<T>(&signer, T)
move_from<T>(address): T
borrow_global_mut<T>(address): &mut T
borrow_global<T>(address): &T
exists<T>(address): bool

### 2024.09.11
Move Objects 
可以往地址转入object

module my_addr::object_playground {
  use std::signer;
  use std::string::{Self, String};
  use aptos_framework::object::{Self, ObjectCore};
  
  struct MyStruct1 {
    message: String,
  }
  
  struct MyStruct2 {
    message: String,
  }
 
  entry fun create_and_transfer(caller: &signer, destination: address) {
    // Create object
    let caller_address = signer::address_of(caller);
    let constructor_ref = object::create_object(caller_address);
    let object_signer = object::generate_signer(constructor_ref);
    
    // Set up the object by creating 2 resources in it
    move_to(&object_signer, MyStruct1 {
      message: string::utf8(b"hello")
    });
    move_to(&object_signer, MyStruct2 {
      message: string::utf8(b"world")
    });
 
    // Transfer to destination
    let object = object::object_from_constructor_ref<ObjectCore>(
      &constructor_ref
    );
    object::transfer(caller, object, destination);
  }
}

### 2024.09.12
创建object
有三种类型
1. normal Object 
可删除、随机地址
let caller_address = signer::address_of(caller);
let constructor_ref = object::create_object(caller_address);

2. named Object
自定义名字的object
不可删除、固定地址
const NAME: vector<u8> = b"MyAwesomeObject";

entry fun create_my_object(caller: &signer) {
    let caller_address = signer::address_of(caller);
    let constructor_ref = object::create_named_object(caller, NAME);
    // ...
}

3. sticky Object
不可删除、随机地址
let caller_address = signer::address_of(caller);
let constructor_ref = object::create_sticky_object(caller_address);

### 2024.09.13
通过object::generate_signer可以创建singer来允许你往object传递资源过去
let caller_address = signer::address_of(caller);

// Creates the object
let constructor_ref = object::create_object(caller_address);

// Retrieves a signer for the object
let object_signer = object::generate_signer(&constructor_ref);

// Moves the MyStruct resource into the object
move_to(&object_signer, MyStruct { num: 0 });

### 2024.09.16
扩展性 ExtendRef
ContructorRef 只有创建object的时候存在，后面就销毁了
ExtendRef可以作为资源发给object储存下来，后面可以继续拿出来对object进行新的操作

// 往object传入一个extend_ref资源
let extend_ref = object::generate_extend_ref(&constructor_ref);
move_to(&object_signer, ObjectController { extend_ref });

### 2024.09.18
aptos sdk学习
async mintCoin(minter: AptosAccount, receiverAddress: HexString, amount: number | bigint): Promise<string> {
    const rawTxn = await this.generateTransaction(minter.address(), {
      function: "0x1::managed_coin::mint",
      type_arguments: [`${minter.address()}::justin_coin::JustinCoin`],
      arguments: [receiverAddress.hex(), amount],
    }, customOpts);

    await this.simulateTransaction(minter, rawTxn).then((sims) =>
      sims.forEach((tx) => {
        if (!tx.success) {
          throw new Error(`Transaction failed: ${tx.vm_status}\n${JSON.stringify(tx, null, 2)}`);
        }
      }),
    );

    const bcsTxn = await this.signTransaction(minter, rawTxn);
    const pendingTxn = await this.submitTransaction(bcsTxn);

    return pendingTxn.hash;
  }

### 2024.09.19
async transferCoin(sender: AptosAccount, receiverAddress: HexString, amount: number | bigint): Promise<string> {
    const rawTxn = await this.generateTransaction(sender.address(), {
      function: "0x1::aptos_account::transfer_coins",
      type_arguments: [`${sender.address()}::justin_coin::JustinCoin`],
      arguments: [receiverAddress.hex(), amount],
    });

    const bcsTxn = await this.signTransaction(sender, rawTxn);
    const pendingTxn = await this.submitTransaction(bcsTxn);

    return pendingTxn.hash;
  }
  
### 2024.09.20
Global Storage
move_to<T>(&signer, T)
move_from<T>(address): T
borrow_global_mut<T>(address): &mut T
borrow_global<T>(address): &T
exists<T>(address): bool

T要求有key的能力

Global Storage返回的ref不能作为函数的参数返回

acquires 要求类型
m::f 要求 acquires T 
1. m::f 包含 move_from<T> borrow_globnal_mut<T> borrow_global<T>
2. m::f 调用的 m::g 在同一个模块中acquires T

### 2024.09.21
const client = new AptosClient(NODE_URL);
  const faucetClient = new FaucetClient(NODE_URL, FAUCET_URL);

  // Generates key pair for a new account
  const account1 = new AptosAccount();
  await faucetClient.fundAccount(account1.address(), 100_000_000);
  let resources = await client.getAccountResources(account1.address());
  let accountResource = resources.find((r) => r.type === aptosCoinStore);
  let balance = parseInt((accountResource?.data as any).coin.value);
  assert(balance === 100_000_000);
  console.log(`account1 coins: ${balance}. Should be 100000000!`);

  const account2 = new AptosAccount();
  // Creates the second account and fund the account with 0 AptosCoin
  await faucetClient.fundAccount(account2.address(), 0);
  resources = await client.getAccountResources(account2.address());
  accountResource = resources.find((r) => r.type === aptosCoinStore);
  balance = parseInt((accountResource?.data as any).coin.value);
  assert(balance === 0);

### 2024.09.22
研究aptos前端动态发token

### 2024.09.23
public entry fun deploy_derived(
    deployer: &signer,
    metadata_serialized: vector<u8>,
    code: vector<vector<u8>>,
    seed: vector<u8>
) acquires DeployingSignerCapability {
    let deployer_address = signer::address_of(deployer);
    let resource = account::create_resource_address(&deployer_address, seed);
    let resource_signer: signer;
    if (exists<DeployingSignerCapability>(resource)) {
        let deploying_cap = borrow_global<DeployingSignerCapability>(resource);
        resource_signer = account::create_signer_with_capability(&deploying_cap.signer_cap);
    } else {
        let signer_cap: account::SignerCapability;
        (resource_signer, signer_cap) = account::create_resource_account(deployer, seed);
        move_to(&resource_signer, DeployingSignerCapability { signer_cap, deployer: deployer_address });
    };
    code::publish_package_txn(&resource_signer, metadata_serialized, code);
}

### 2024.09.24
public fun create_primary_store_enabled_fungible_asset(
    constructor_ref: &ConstructorRef,
    // This ensures total supply does not surpass this limit - however, 
    // Setting this will prevent any parallel execution of mint and burn.
    maximum_supply: Option<u128>,
    // The fields below here are purely metadata and have no impact on-chain.
    name: String,
    symbol: String,
    decimals: u8,
    icon_uri: String,
    project_uri: String,
)

### 2024.09.25
 use aptos_std::smart_table;
 
public entry fun main() {
    let table = smart_table::new<u64, u64>();
    smart_table::add(&mut table, 1, 100);
    smart_table::add(&mut table, 2, 200);

    let length = smart_table::length(&table);
    assert!(length == 2, 0);

    let value1 = smart_table::borrow(&table, 1);
    assert!(*value1 == 100, 0);

    let value2 = smart_table::borrow(&table, 2);
    assert!(*value2 == 200, 0);

    let removed_value = smart_table::remove(&mut table, 1);
    assert!(removed_value == 100, 0);

    smart_table::destroy_empty(table);
}

### 2024.09.26
use std::vector;

public entry fun main() {
    let v = vector::empty<u64>();
    vector::push_back(&mut v, 10);
    vector::push_back(&mut v, 20);

    let length = vector::length(&v);
    assert!(length == 2, 0);

    let first_elem = vector::borrow(&v, 0);
    assert!(*first_elem == 10, 0);

    let second_elem = vector::borrow(&v, 1);
    assert!(*second_elem == 20, 0);

    let last_elem = vector::pop_back(&mut v);
    assert!(last_elem == 20, 0);

    vector::destroy_empty(v);
}

<!-- Content_END -->
