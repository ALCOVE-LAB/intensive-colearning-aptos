---
timezone: Asia/Shanghai
---

---

# Zemmer

1. 一名程序猿 + 一名自洽的产品。技术栈：web3：solidity相关。web2：vue3、fastapi。
2. 可以完成。

## Notes

<!-- Content_START -->

### 2024.09.07

1、了解了aptos链的历史
2、对比了共识机制
3、下载IDE，安装环境

### 2024.09.08
# move和solidity合约的不同点

## token的账本balance存储在用户账户中

1、ERC20存储在合约中，是一个总账形式。mapping(address => uint256)

2、Aptos的token balance是分账，存储在各自用户的账户中。

3、这么做的原因是因为Aptos中将token视为资源，利用区块交易的确定性，将所有权和资源绑定。

4、当move的合约需要token的总数，这个话题需要之后回答，我觉得可能的形式是单独维护一个总账，或进行链上计算所有的分账？

## 转账需要接收人确认

1、EVM上转账不需要接收人确认。

2、EVM这种机制的问题是可能恶意转账：多次小额转、转没用的资产、转违法收入比如洗钱。

3、Move转账需要接收人确认。


### 2024.09.09
起步，明天开始吧，今天把layer2和aptos的所有区别捋了一遍，从理论上解决了非以太坊公链和以太坊二链的区别。包括生态、技术、共识、交易对手、品牌等。
### 2024.09.10
### 2024.09.11
安装aptos，开始move编程。
### 2024.09.12
# 整体流程命令

## 创建项目

### 创建整体项目（可省略）

进入指定的目录

```
aptos init
```

### 再创建合约项目

在项目目录下

```
aptos move init
```

结果：

创建了move.toml等文件

## 编写合约

写代码

## 编译合约

在项目目录下

```
aptos move compile
```

```
aptos move build
```

### 这两个命令的区别

#### aptos move compile

主要用于编译 Move 源代码，并生成字节码文件（`.mv` 文件）。

只关注 Move 代码的语法和逻辑正确性，不会将模块或脚本发布到链上。

开发阶段使用：常用于开发过程中测试代码是否能通过编译，以及生成字节码供其他操作使用。

输出的是编译后的 Move 模块（例如 `.mv` 文件），这些文件不会包含包管理相关的信息。

语法格式：`aptos move compile --package-dir <package_path>`

### aptos move build

这是一个更高层次的命令，它除了编译 Move 代码外，还会对整个 Move 包进行构建。

它会处理 Move 包的依赖关系、生成构建工件（artifact），并打包输出编译好的模块或脚本。

在构建过程中，它会生成一些额外的元数据和包管理信息，方便后续的模块发布或部署。

生产阶段使用：适用于打包、准备发布 Move 项目，构建结果可以直接用于链上发布。

语法格式：`aptos move build --package-dir <package_path>`

## 部署合约前准备

### 1、生成账户

生成特定前缀的账户（部署人用于部署合约的账户，因为aptos里没有contract address的概念）

--vanity-prefix参数是自定义的账户名的前缀，在这里值是--vanity-prefix

--output-file是自定义的生成的保存账户地址的文件，在这里值是ace.key

```zsh
aptos key generate --vanity-prefix 0xace --output-file ace.key
```

结果

```json
{
  "Result": {
    "Account Address:": "0xacef1b9b7d4ab208b99fed60746d18dcd74865edb7eb3c3f1428233988e4ba46",
    "PublicKey Path": "ace.key.pub",
    "PrivateKey Path": "ace.key"
  }
}
```

### 2、为账户提供资金

#### 拷贝地址

```zsh
ace_addr=0xacef1b9b7d4ab208b99fed60746d18dcd74865edb7eb3c3f1428233988e4ba46
```

#### 给地址水

```zsh
aptos account fund-with-faucet --account $ace_addr
```

结果

```json
{
  "Result": "Added 100000000 Octas to account acef1b9b7d4ab208b99fed60746d18dcd74865edb7eb3c3f1428233988e4ba46"
}
```

## 部署合约

1、使用aptos move publish部署

2、参数--named-addresses：部署人地址

3、--private-key-file：私钥

4、--assume：不清楚

```
aptos move publish \
    --named-addresses test_account=$ace_addr \
    --private-key-file ace.key \
    --assume-yes
```

结果

```json
{
  "Result": {
    "transaction_hash": "0x1d7b074dd95724c5459a1c30fe4cb3875e7b0478cc90c87c8e3f21381625bec1",
    "gas_used": 1294,
    "gas_unit_price": 100,
    "sender": "acef1b9b7d4ab208b99fed60746d18dcd74865edb7eb3c3f1428233988e4ba46",
    "sequence_number": 0,
    "success": true,
    "timestamp_us": 1685077849297587,
    "version": 528422121,
    "vm_status": "Executed successfully"
  }
}
```



# 
### 2024.09.13
### 2024.09.14
### 2024.09.15
### 2024.09.16
### 2024.09.17
### 2024.09.18


<!-- Content_END -->
