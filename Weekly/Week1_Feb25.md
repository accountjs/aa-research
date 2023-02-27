# Account-Abstraction Weekly - W1_Feb27

## Infra

基础设施

---

###  1. Alchemy Smart Contract Wallet Infrastructure Registration
可注册 alchemy 智能合约钱包公测版，链接地址:

Alchemy Website: https://www.alchemy.com/account-abstraction

Alchemy Doc: https://www.alchemy.com//blog/account-abstraction

Including following services:
- Bundler services：enable dapps and wallets to submit batched transactions rather than hundreds of separate requests - this means cost efficiencies and scalability
- Paymaster services：making it easy to sponsor and subsidize transaction costs for users on your dapps - this means tools to foster brand loyalty
(from mail)

提供Bundler和Paymaster的服务，可使用批量服务，代付交易

### 2. Co-author of ERC-4337 founded Pimlico Infrastructure
[账户抽象提案 EIP-4337 联合发起人 Kristof Gazso 创立 Web3 基础设施项目 Pimlico](https://www.chaincatcher.com/article/2088110)

Official Website: https://www.pimlico.io/

Official Github: https://github.com/pimlicolabs


Pimlico's vision is to be the underlying infrastructure layer that will power Ethereum's transition to smart contract wallets through mass ERC-4337 adoption.

We will initially be focusing on providing comprehensive infrastructure for two of the above-mentioned entities: Bundlers and Paymasters, two of the most critical pieces of the puzzle that are missing for wallets building on top of ERC-4337.
(from doc)

Pimlico 的愿景是成为基础设施层，通过采用 ERC-4337，为以太坊向智能合同钱包大规模过渡提供动力。最初将集中精力为以下两个实体提供具体的基础设施: Bundlers 和 Paymaster 

### 3. ZeroDev have been included in YCW23
[8个Web3新项目，Y Combinator最新孵化计划w23项目一览](https://www.theblockbeats.info/news/34980)

[Account abstraction wallets as a service](https://www.ycombinator.com/companies/zerodev)

Official WebSite: https://zerodev.app/


Use ZeroDev to create self-custody wallets for your users, powered by account abstraction. These wallets are truly non-custodial, while being easier to use and way more powerful than even custodial wallets, enabling features such as:

- Gas-free transactions
- Transaction bundling
- Programmable security policies

ZeroDev is perfect for anyone who wants to create wallets for users, including Web 2.5 apps, wallet apps, onramps, marketplaces, and more!
(from web)

ZeroDev 是建立在EIP4337层的SDK接入层，能为项目用户建立智能合约钱包，为web2.5应用，钱包, 应用入口提供了以下功能：无gas费交易，批量交易，可编程安全策略。


## Dapps
AA应用
### 1. Alchemy Smart Contract Wallets
Alchemy列出的合约钱包大全

https://www.alchemy.com/best/smart-contract-wallets

### 2. Paymaster as a Service
一个paymaster的PAAS仓库

https://github.com/plusminushalf/paas/blob/main/apps/contracts/contracts/DappPaymaster.sol

### 4. Stackup 4337 Examples
Stackup 基于4337SDK的调用案例

https://docs.stackup.sh/docs/guides/quickstart

### 5. ERC4337 MEV
4337的Mev机器人

https://github.com/kristofgazso/erc4337-mev-searcher-bot


## Research
研究

### 0. Layer 2 Community Grants Winners

https://blog.ethereum.org/2023/02/14/layer-2-grants-roundup

[以太坊基金会2022年Layer2社区捐赠计划获奖项目一览](https://www.odaily.news/post/5185168)

About Account-Abstraction

- Candidelabs - ERC-4337 Public Infrastructure
An open source bundler and a paymaster service as public good infrastructure for ERC-4337 smart contracts wallets, layer 2 focused.

Candidelabs - ERC-4337 公共基础设施。这是一个作为 ERC-4337 智能合约钱包公共物品基础设施的开源捆绑器（bundler）和支付（paymaster）服务，专注于 Layer 2 。

- Spiro - zkWallet
Multi-party wallets (e.g. Gnosis safe multisigs) are a proven way for a group of users to share control over an account’s digital assets and behaviors. Unfortunately, current implementations of multi-party wallets expose the privacy of their total number of operators and their associated externally owned accounts. The goal of this project is to build a private multi-party wallet that shields end users by employing account abstraction (EIP-4337) and zero-knowledge proofs.

Spiro - zkWallet。多方安全钱包（如 Gnosis 安全多签）是一个行之有效的方法，可以让多个用户共享一个账户的数字资产和行为的控制权。不幸的是，目前多方钱包的实现暴露了多签地址总数及其相关的外部账户（EOA）隐私。Spiro 钱包旨在建立一个私有的多方钱包，通过采用账户抽象（EIP-4337 ）和零知识证明来屏蔽终端用户。

- Kristof Gazso - Typescript ERC-4337 Bundler
The project will include the development of an ERC-4337 bundler in Typescript and the relevant modifications to a Geth node for simulation purposes so that the bundler can run on any directly Geth-compatible chain (which includes most L2s) with little modifications. The bundler will also expose the RPC calls defined in the specification, and maintain an internal mempool to be future-proof when P2P propagation will be developed.

Kristof Gazso - 该项目将包括在 Typescript 中开发一个 ERC-4337 捆绑器（bundler），并为模拟目的对 Geth 节点进行相关修改，以便捆绑器只需进行少量修改便可以在任何直接与 Geth 兼容的链（包括大多数 L2）上运行。该捆绑器还将公开规范中定义的 RPC 调用，并维护一个内部的 mempool，以便在开发 P2P 广播时能够面向未来。

- Soul Wallet - Open-source ERC-4337 wallet
Easy-to-use browser wallet implementation powered by ERC-4337.

Soul Wallet - 开源 ERC-4337 钱包。由 ERC-4337 驱动的易于使用的浏览器钱包实现。

### 1. Infinitism contract and bundler bump to v0.5
Infinitism 官方4337合约和bundler服务升级到v0.5

https://github.com/eth-infinitism/bundler/commit/22166ee14b7ea4d017a365fe36cf9d4a49520e6b

### 2. Unpacking ERC-4337

https://frontier.tech/unpacking-erc-4337

### 3.  Account Abstraction Using Alt Mempool 

https://twitter.com/poojaranjan19/status/1627688634416611329

[Join Discussion](https://ethereum-magicians.org/t/erc-4337-account-abstraction-via-entry-point-contract-specification/7160)

#ERC4337 talk includes: 
会议内容包括：
- Key Challenges
- UserOperation
- Submit UserOperation to bundler with factory
- Submit UserOperation to bundler with PayMaster
- Creating HandleOps Transaction
- #AccountAPI
- #MinimalAccount
- #PayMaster
- Custom Factory
- Protection Rule Principles.
- Code Validation Rules.
- Storage Validation rules.
- RPC APIs
- BundlerSpecTest, Q&A and more

### 4. 智能合约钱包知识库

https://h0m83hhc6r.feishu.cn/docx/doxcnWoAPjXPXXpoJ9HtRNxJSFb

### 5. Dapplearning账户抽象实操Part101 by  Arc

p1 https://youtu.be/1m9QmyDCpFc

p2 https://youtu.be/RgLkyUGPufk


document: https://www.notion.so/1-9d99463f25ca4c32a5776f6f2cb57edf



## ETH Hackathon

### 1. The zkSync Era∎ Hack Series

https://twitter.com/zksync/status/1626710343044198400

```
Contact:
Wechat: skyhigh22
Twitter: @skyh20
Email: skyhighfeng@gmail.com
ENS: skyhighfeng.eth
GitHub: https://github.com/accountjs/aa-research
```

Thanks to Plancker^
Join our group to post news: https://t.me/+Hpm2SIXGpz5hNWY1