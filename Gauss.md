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

## Notes

<!-- Content_START -->

### 2024.09.07

Aptos区块链概述
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


### 2024.07.12

<!-- Content_END -->
