# Aptos 残酷共学 - Aptos / LXDAO / Alcove / Ankaa 等联合发起

### 什么是残酷共学（Intensive Co-learning）？
<details>
残酷共学是由 [Bruce Xu](https://twitter.com/brucexu_eth) 首创的一种学习模式，目前由 [LXDAO](https://lxdao.io/) 组织并运营残酷共学品牌。
共学有很多种，「残酷共学」与之不同的是「残酷」：

- 你必须每天围绕某个「共学主题」进行学习，每周只有两次请假机会，通常每天至少需要花费半个小时（最好一个小时）来学习。
- 你必须提交你的学习证明（按照共学内容设计）到这个「仓库」来证明你今天学习了。
- 如果你没有完成上面两点，你会立刻被踢掉并且标记为 ❌ 失败。
- 每期残酷共学以 4 周为一个周期，第一周为共学启动报名和熟悉共学规则，第二周到第四周将正式启动共学，为期 21 天，中途不得加入。
- 共学方向包括不限于：英语、以太坊、Web3 技术、DAO、加密思潮等，自由自主发起。共学的过程包括且不限于：观看视频、阅读书籍与文章、项目实战等。

报名方式是完全基于 GitHub 的流程，通过提交 PR 进行申请，合并 PR 之后拥有更新权限。如果你不熟悉 GitHub 和 Git 的操作，请先自行学习。通常还会有一个小型的 Telegram 交流群方便交流。

关于更多「残酷共学」的介绍请参见：https://forum.lxdao.io/t/topic/1654

关于更多正在发生的残酷共学请参见：https://intensivecolearn.ing/
</details>

## **背景与目标**

> Aptos 残酷共学由 Aptos、LXDAO、Alcove 、Ankaa 加速器联合发起，由 Aptos、Alcove、Aptos Global 联合赞助

本次活动旨在大家了解 Aptos 、学习 Aptos 、使用 Aptos
> 

📘 共学目标：

- 了解 Aptos 公链的架构和特点
- 掌握 Aptos Move 语言的基本语法和编程技巧
- 探索 Aptos 目前最新的技术发展

## **面向人群及共学特色**

无论你是开发者，还是对 DeFi 充满好奇的普通人，我们都欢迎的加入。

> 无论你是 Web2 / Web3 开发者，还是对 Aptos 充满好奇的普通人，我们都欢迎加入
> 

## **🌐 共学特色：**

- **全面开放：** 我们的大门向所有人敞开，无需特定的技术背景或经验。
- **知识共享：** 我们鼓励知识交流，相信每个人都能为这个社区带来独特的视角。
- **实践融合：** 通过每日学习后提交学习笔记或者提交部署合约 / 交易的 Hash，。
- **开源开放：** 以 GitHub 为学习平台，提供了一个开放、协作的学习环境。

## **🗓️ 共学活动：**

- **定期会议：** 每周的线上会议，解答疑惑，分享 Aptos 技术细节，了解 Aptos 特性。

## 会议安排

- 9 月 7 号：
    - 视频回放: https://youtu.be/wY0yFyYILXs 
    - 主题： Aptos & Move 简介与学习资料推荐
    - 主讲人： Logan - Aptos DevRel
- 9 月 10 号：
    - 视频回放: https://youtu.be/wY0yFyYILXs 
    - 主题：安装开发环境、创建/编译/测试/部署工程
    - 主讲人： Logan - Aptos DevRel
- 9 月 18 号
    - 视频回放: https://youtu.be/mWpfW47-pHk
    - 主题： 构建并部署 代币 faucet
    - 主讲人： Logan - Aptos DevRel
- 9 月 24 号
    - 视频回放: https://youtu.be/_hZXS3Nc1d4
    - 主题： 构建并部署 NFT LaunchPad
    - 主讲人： Logan - Aptos DevRel

> 「Aptos 残酷共学」，以 21 天为一个学习周期，实现自主、开源开放，不断共同构建和完善 Aptos 共学资料及实践案例。
> 

## **可供参考的学习内容和路线**

1. Aptos 公链机制：
    - 了解 Aptos 公链的架构、共识机制，Gas 模型、帐户模型、资源模型、交易与状态模型
    <details> 
        
    - [共识机制](https://aptos.dev/en/network/blockchain/validator-nodes#consensus) 
    - [账户模型](https://aptos.dev/en/network/blockchain/accounts)
    - [Gas 模型](https://aptos.dev/en/network/blockchain/gas-txn-fee)
    - [资源模型](https://aptos.dev/en/network/blockchain/resources)
    - [交易与状态模型](https://aptos.dev/en/network/blockchain/txns-states)
   </details>
3. Aptos Move （初级）：
    - 了解 Aptos Move 的基本语法，Aptos  Stdlib 的使用
    <details> 
        
    - [Aptos Move Book](https://aptos.dev/en/build/smart-contracts/book)
    - [Aptos Stdlib 合约源码](https://github.com/aptos-labs/aptos-core/tree/main/aptos-move/framework/aptos-stdlib/sources)
   </details>
5. Aptos Move （中级）：
    - 了解 Aptos Move Framework 和 其他官方库，并尝试部署简单的 ToDolist 合约、了解 Object 模型
    <details> 
        
    - [Aptos Move Framework 合约源码](https://github.com/aptos-labs/aptos-core/tree/main/aptos-move/framework/aptos-framework/sources)
    - [Aptos Token 合约源码](https://github.com/aptos-labs/aptos-core/tree/main/aptos-move/framework/aptos-token-objects/sources)
    - [ToDolist 合约示例](https://learn.aptoslabs.com/zh/code-example/todo-list)
    - [Object 模型](https://aptos.dev/en/build/smart-contracts/objects)
   </details>
7. Aptos Move （高级）：
    - 了解 Aptos Move 的代币标准 ，FA （同质化代币） / DA（非同质化代币），并尝试部署自己的 代币水龙头、NFT LaunchPad 
    <details> 
        
    - [NFT LaunchPad 合约 / 前端 示例](https://learn.aptoslabs.com/zh/code-example/fa-launchpad)
        - [Live Demo](https://fungible-asset-launchpad.vercel.app/)
    - [Fungible Asset（ 同质化代币 -  FT / ERC 20 ）文档](https://aptos.dev/en/build/smart-contracts/fungible-asset)
    - [Digital Asset（ 非同质化代币 -  NFT / ERC 721 ）文档](https://aptos.dev/en/build/smart-contracts/digital-asset)
   </details>
8. Dapp开发： 合约测试，React / Nextjs 与 Aptos Wallet 的链接、Ts SDK 的使用，读取链上数据、发送链上交易
9. 新功能：Keyless 无私钥登陆，Randomness 链上随机数， Dispatchable Fungible Assets

## **残酷共学特别激励**

**🏅NFT 徽章：** 完成 Aptos 残酷共学的小伙伴结业将收到一枚 Badge 徽章认证。

**🎁 特别奖励：** 我们相信，真正的学习是教会你如何获取所需，随着你的技能提升，一系列特别奖励将随之而来。
同时也为大家准备了一些奖励机制：

**总奖池 1800 U**
> 所有的奖励需要大家先完成共学才能有获奖资格

- **1.  所有完成共学的人**：平分 500 USDC
- **2. 所有完成项目的人**：平分 300 USDC
- **3. 项目额外奖金**
    - **第一名**：500 USDC
    - **第二名**：300 USDC
    - **第三名**：200 USDC

>**奖金发放可以叠加**
>
>未完成共学  = **无**  
>未完成共学  +  完成项目  = **无**  
>**完成共学** + **完成项目（未获奖）**=  **可平分 1 奖励 + 平分 2 奖励**  
>**完成共学** + **完成项目（获奖 第一名）**=  **可平分 1 奖励 + 平分 2 奖励 + 项目第一名奖金**  

**共学时间**

- 报名截止时间：2024-09-06 23:00:00（UTC+8）
- 本期共学开始时间：2024-09-07 00:00:00（UTC+8）
- 本期共学持续时间：21 天（我们默认为 21 天，21 天为养成一个新习惯的周期，可根据自己的内容和课程来制定，但不易过长或过短）

## **共学规则**

- 报名规则：请在报名截止时间前进行报名，共学一旦开始后，不得中途加入
- 打卡规则：建议你每天学习 30 ～ 60 分钟，并将学习笔记提交，我们会自动更新你的打卡状态，每周有 3 次请假的机会，超过后状态变为 ❌，视为本次共学失败

## **如何报名和打卡？**

- 报名:
    - Step01：Fork 本仓库。
    - Step02：复制 Template.md 创建你的个人笔记文件，并根据文档指引填写你的信息，并将文件重命名为你的名字：YourName.md。
    - Step03：创建一个 PR 到当前仓库，本残酷共学助教会对你的 PR 进行 review，review 通过后，你的 PR 会被 merge 到 main 分支，这个时候你会收到邀请加入这个仓库 contribution 的邮件，接受邀请后，你会自动获得 main 分支的 push 权限。
    - Step04：完成以上三个步骤，恭喜你报名成功，后续就可以将你的学习记录直接 push 到 main 分支进行更新。
    - 请加入LXDAO TG 群组保持交流：[http://t.me/LXDAO](https://t.me/LXDAO/12418)  加入群组后请在群里报到一下方便助教记录
    - 或者添加 Aptos DevRel 微信进入 Aptos 官方微信群:  logan_apt
- 打卡：
    - 报名成功后，你将拥有 main 分支的 push 权限，你需要将每天学习笔记按日期更新到你的 YourName.md 文档中，提交更新后，我们会自动更新你的打卡状态到下面的打卡记录表。
    - 如果你不在 UTC+8 时区，需要添加时区 code 到你的 YourName.md 文件的开始，错误的时区设置可能会使自动化打卡脚本错误计算打卡时间，具体请参考：https://github.com/IntensiveCoLearning/template/blob/main/Template.md?plain=1#L1
    - 当你提交笔记时，请确保以下几点，否则打卡可能会失败：
        - 在 YourName.md 文档，请将笔记内容放到以下代码块中，且 `<!-- Content_START -->` 和 `<!-- Content_END -->` 不能删除:
        
        ```
        <!-- Content_START -->
        ### 日期
        笔记内容
        <!-- Content_END -->
        
        ```
        
        - 日期格式为 `### 2024.07.11`，请不要随意更改

## {Aptos 残酷共学}打卡记录表

✅ = Done ⭕️ = Missed ❌ = Failed

<!-- START_COMMIT_TABLE -->
| Name | 9.07 | 9.08 | 9.09 | 9.10 | 9.11 | 9.12 | 9.13 | 9.14 | 9.15 | 9.16 | 9.17 | 9.18 | 9.19 | 9.20 | 9.21 | 9.22 | 9.23 | 9.24 | 9.25 | 9.26 | 9.27 |
| ------------- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| Ellen | ✅ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| simons | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| yue | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| qiaopengjun | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Punkcan | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ |   | ⭕️ | ✅ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | |
| Oscar | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ⭕️ | ✅ | ✅ | ⭕️ | ✅ | ✅ |
| MartinYeung5 | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| hahn | ⭕️ | ⭕️ | ✅ | ✅ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | |
| Gauss | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| newraina | ✅ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ⭕️ | ✅ | ✅ | ⭕️ |   | ⭕️ | ⭕️ | ❌ | | | | | |
| bofu | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| kaka | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Bob | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| Ric-Li-C | ✅ | ✅ | ⭕️ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ⭕️ |
| laios | ✅ | ✅ | ✅ | ✅ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | |
| gills | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ⭕️ |   | ❌ | | | | | | | |
| Heinlich | ✅ | ✅ | ⭕️ | ✅ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | |
| yoyo | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| ajie | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| Nicole | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ⭕️ | ✅ | ⭕️ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ✅ |
| bityoume | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |   | ⭕️ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ⭕️ |
| Jack | ✅ | ✅ | ✅ | ✅ | ⭕️ | ⭕️ | ✅ | ⭕️ | ❌ | | | | | | | | | | | | |
| Steven | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| bugmaker | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| zouyuxuan | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ |
| Qi | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ⭕️ |
| Dason | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ |   | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ |
| vegetabledogdog | ✅ | ✅ | ✅ | ✅ | ⭕️ | ⭕️ | ⭕️ | ✅ | ❌ | | | | | | | | | | | | |
| 7uppp | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| yan | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| nosalt | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| pest | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Zemmer | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ |   | ⭕️ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| SummerXJ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Alvin | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| SidWoong | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| justin | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ⭕️ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ |
| Derick | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ⭕️ |
| Risker-C | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |   | ⭕️ | ✅ | ✅ | ⭕️ | ⭕️ | ⭕️ | ❌ | |
| Tony | ✅ | ⭕️ | ✅ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | |
| fantasy00lucky | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| kizy | ✅ | ⭕️ | ⭕️ | ✅ | ✅ | ✅ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | |
| Elemen | ✅ | ⭕️ | ⭕️ | ⭕️ | ⭕️ | ❌ | | | | | | | | | | | | | | | |
| huisq | ⭕️ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⭕️ | ⭕️ | ⭕️ | ✅ | ✅ | ❌ | | | | | | |
| seele1433223 | ✅ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ⭕️ | ✅ | ✅ | ✅ | ⭕️ | ✅ | ✅ | ⭕️ | ⭕️ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
<!-- END_COMMIT_TABLE -->































































<!-- STATISTICALDATA_START -->


## 统计数据

- 总参与人数: 45
- 完成人数: 16
- 全勤用户: simons, yue, qiaopengjun, MartinYeung5, SummerXJ
- 淘汰人数: 26
- 淘汰率: 57.78%
- Fork人数: 43
<!-- STATISTICALDATA_END -->

