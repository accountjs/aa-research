# Account-Abstraction Weekly - W4_Mar19

## Infra

基础设施

---

### 1. New standard for the adoption of account abstraction (AA). A way to verify a signature when the account is a smart contract that has not been deployed yet
AA的新签名方法，一种仍未部署合约仍可以验证合约账户签名的方案

https://twitter.com/zerodev_app/status/1636465069688229889

Inspired by: 受4337讨论的启发: 
https://github.com/eth-infinitism/account-abstraction/issues/188

ERC-6492: Signature Validation for Predeploy Contracts
https://eips.ethereum.org/EIPS/eip-6492

https://docs.zerodev.app/blog/erc-6492-and-why-its-important-for-aa


### 2. EIP-6662: AA Account Metadata for Authentication
An ERC-4337 extension to define a new authentication model

EIP4337的扩展，支持一种新的authentication model, 可以实现wallet-free的dApps用户体验。

Description: 描述：
https://medium.com/@shu_hexlink/demystifying-wallets-a-revolutionary-dapp-user-flow-b72c3656f9dd

### 3. Pimlico is developing an open source Bundler in Typescript.
Pimlico 在开发一个ts的开源的bundler

https://twitter.com/pimlicoHQ/status/1634696323378319360

### 4. Making Ethereum Accounts Recoverable - The Seedless Way
Candide在实现AA钱包社交恢复的方法

https://docs.candidewallet.com/blog/making-accounts-recoverable/

## Dapp
应用

（No new dapp） Plz contact：skyhighfeng@gmail.com 

### 1. ERC-4337 Account Abstraction Overview on Dune
Dune上的ERC-4337面板

https://twitter.com/0xKofi/status/1636392810113900545

## Research
研究

### 1. A resarcher Broke erc4337 infra that manipulating userOp calldata can make inconsistent userOpHash
一个审计研究员通过操纵userOp的calldata字段来实现生成相同userOpHash

https://twitter.com/leekt216/status/1636414866662785024

### 2. Challenges of EIP4337-bundler in Layer2 implementation
- Sequencer centralization
- Gas fee calculation complexity

描述了在2层搭建bundler的调整，包括定序器，gas费计算等

https://hackmd.io/@cejay/HJSMHwll2

### 3. Unified ERC-4337 mempool
重读ERC4337统一内存池的文章

https://notes.ethereum.org/@yoav/unified-erc-4337-mempool#How-can-we-prevent-this-mempool-fragmentation

### 4. What is up with Ethereum’s ERC-4337?
4337的解析性文章

https://medium.com/coinmonks/what-is-up-with-ethereums-erc-4337-7abe63b7c575

### 5. A Guide to the Top ERC-4337 Bundlers: Features, Performance, and More
Stackup的Bundler资料

https://www.stackup.sh/blog/a-guide-to-the-top-erc-4337-bundlers-features-performance-and-more

### 6. Account Abstraction and ERC-4337 Wallets -- Dror Tirosh

https://www.youtube.com/watch?v=-syoWCmi4Mo

### 7. EIP 4337 Materials
一些资料

https://github.com/doganalpaslan/Awesome-Account-Abstraction-Resources/blob/main/README.md

https://github.com/eth-protocol-fellows/cohort-three/blob/master/projects/4337-bundler-rust.md

https://github.com/eth-protocol-fellows/cohort-three/blob/master/projects/4337-wallet.md

### 8. How to start with erc-4337

https://ethereum.stackexchange.com/questions/146974/how-to-start-with-erc-4337

## ETH Hackathon

### 1. The Account Abstraction Grants Round is still open, but the deadline is less than 2 weeks away
ESP抽象账户的Grant申请结束时间少于2周了

https://twitter.com/EF_ESP/status/1636743919592513538


### 

```
Contact:
Wechat: skyhigh22
Twitter: @skyh20
Email: skyhighfeng@gmail.com
ENS: skyhighfeng.eth
GitHub: https://github.com/accountjs/aa-research
```


Join our group to post news: https://t.me/+Hpm2SIXGpz5hNWY1