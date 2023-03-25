# Safe {Core} 研究笔记_[3,3,23]

## Safe Blogs Research
1. Account Abstraction is NOT coming，It’s already here with Safe

https://safe.mirror.xyz/9KmZjEbFkmI79s28d9xar6JWYrE50F5AHpa5CR12YGI

2. Launching Safe{Core} Account Abstraction Stack with Stripe, Gelato and Web3Auth

https://safe.mirror.xyz/FLvQQ5J9qXks0izRl73oC6LiFLofbwFNorwzaEj_xL8

- Signature abstraction - Allow different account contracts to use different signature validation schemes.
签名抽象——允许不同的帐户契约使用不同的签名验证方案。

- Gas abstraction - Allow different models of payment for transaction fees. For example, payment by another party/contract.
Gas抽象-允许不同的交易费用支付方式。例如，由另一方/合同支付。

- Nonce abstraction - Allow different replay protection schemes besides a singular, linear nonce for an account. Such as multiple nonces for different types of transactions.
即时抽象-允许不同的重放保护方案，除了一个奇异的，线性的一个帐户。例如，针对不同类型的事务的多个 nonce。

- Network abstraction - Smart contract accounts can be controlled by accounts on a different network via arbitrary message bridges.
网络抽象——智能合同帐户可以通过任意消息桥由不同网络上的帐户控制。

### EIP4337 support
支持 EIP4337

Our current contracts (v1.3) doesn’t permit you to use multisig with EIP4337 bundler. However, v1.4 of the core contracts solves this using Safe modules and will allow us to collect feedback as EIP4337 is implemented on mainnet.

我们当前的合同(v1.3)不允许您在 EIP4337捆绑包中使用 multisig。然而，核心契约的 v1.4使用安全模块解决了这个问题，并且允许我们收集反馈，因为 EIP4337是在 mainnet 上实现的。

### Native Account Abstraction support
本地帐户抽象支持

Safe contracts v2.0 will support native account abstraction.

安全合同2.0版将支持本地帐户抽象。

We will incorporate the feedback collected from the module based EIP-4337 support to streamline support for native account abstraction on different chains.

我们将整合从基于模块的 EIP-4337支持收集的反馈，以简化对不同链上的本地帐户抽象的支持。

2023 will be the year for Account Abstraction, and we will ensure developers are well funded for their AA efforts with Safe, be it through our grants or hackathons. To the next billion of Web3 users onboarded through AA, we say gm.

2023年将是账户抽象的一年，我们将确保开发商获得充足的资金，用于他们与安全的 AA 努力，无论是通过我们的赠款或黑客马拉松。对于通过 AA 登录的未来10亿 Web3用户，我们称之为通用汽车。


## Safe Document & Code Research

https://docs.gnosis-safe.io/

### Live Features 最新特征

[Multisig](https://help.safe.global/en/articles/3952319-signature-policies): Require multiple signing accounts to approve a transaction before executing.

Multisig: 在执行前需要多个签名帐户来批准事务。

[Spending policies](https://help.safe.global/en/articles/4667979-set-up-and-use-spending-limits): Limit the amount that a signing account can withdraw from a Safe.

支出策略: 限制签名帐户可以从保险箱中提取的金额。

Scheduled transactions: Automatically execute transactions on a schedule.

计划事务: 按照计划自动执行事务。

Roles and Permissions: Set fine grain rules on what types of actions specific accounts can perform.

角色和权限: 对特定帐户可以执行的操作类型设置细粒度规则。

Recovery mechanisms: Allow owners to recover access to their Safe if they lose a primary key.恢复机制: 允许业主在丢失主钥匙的情况下恢复对保险箱的访问。

Hierarchies: Different permission sets based on roles within an organization.

层次结构: 基于组织中的角色的不同权限集。

Transaction batching: Send multiple transactions at once.

事务批处理: 一次发送多个事务。

[Gas abstraction](https://docs.gnosis-safe.io/learn/safe-core-account-abstraction-sdk/relay-kit): Pay for transaction fees using ERC-20 tokens.

Gas抽象: 使用 ERC-20令牌支付交易费用。

Allow & deny lists

允许和拒绝列表

Fraud monitoring

监控欺诈

Automation

自动化

Post-quantum signature schemes

后量子签名方案

### Safe {Core} SDK
1.[Protocol Kit (aka Safe Core SDK)](https://docs.gnosis-safe.io/learn/safe-core-account-abstraction-sdk/protocol-kit)

协议工具包(又名安全核心 SDK)
1. 1.Create and configure customizable smart contract accounts创建和配置可自定义的智能合同帐户
2. 2.Use secure and Audited Smart Contracts使用安全和经过审核的智能合同
3. 3.Execute multiple transactions at once with Transaction Batching使用事务批处理一次执行多个事务

2.[Auth Kit](https://docs.gnosis-safe.io/learn/safe-core-account-abstraction-sdk/auth-kit)

认证Kit
1. 1.Onboard using a social media account or email使用社交媒体账户或电子邮件登陆
2. 2.Easy onboarding using Web3Auth 使用 Web3Auth 轻松登录

3.[Relay Kit](https://docs.gnosis-safe.io/learn/safe-core-account-abstraction-sdk/relay-kit)

中继Kit
1. 1.Pay gas fees in ERC-20 tokens用 ERC-20代币支付汽油费
2. 2.Sponsor transaction fees on behalf of others 代表他人担保交易费用3. 3.Gas-less experiences using Gelato 使用意大利冰淇淋的无气体体验

4.[Onramp Kit](https://docs.gnosis-safe.io/learn/safe-core-account-abstraction-sdk/onramp-kit)

入口Kit
1. 1.Buy crypto using a credit card用信用卡买密码
2. 2.Fiat on-ramping using Stripe 使用 Stripe 的出入法币

### Safe Contract

https://github.com/safe-global/safe-contracts/blob/v1.3.0/contracts/GnosisSafe.sol

### Module模块

模块实现TODO

https://github.com/safe-global/safe-modules

https://github.com/gnosis/zodiac

### Guard 守护者模块

https://github.com/gnosis/zodiac-guard-scope

https://mirror.xyz/yearn-finance-engineering.eth/9uInM_sCrogPBs5qkFSNF6qe-32-0XLN5bty5wKLVqU

### Third-party Safe Apps

https://github.com/safe-global/safe-apps-sdk

With over $90B worth of digital assets held in Safe's alone, it’s essential for the dapp ecosystem to access the untapped market of multi-signature wallets. Safe Apps introduce a completely new way for developers to build their dapps right into a Multisig interface. Turn your Dapp into an HTML iframe component that can be accessed through the Safe. We are providing extensive developer tooling to make it easy to create, test and integrate Safe Apps into the Safe. This includes an unique design system, reusable components and a Safe App SDK that facilitates the Safe App <> Safe communication. Safe就拥有价值超过900亿美元的数字资产，对于 dapp 生态系统来说，进入尚未开发的多签名钱包市场至关重要。安全应用程序为开发人员提供了一种全新的方式，可以将他们的 dapps 直接构建到 Multisig 界面中。将 Dapp 转换为 HTML iframe 组件，可以通过 Safe 访问该组件。我们正在提供广泛的开发工具，使它容易创建，测试和集成到安全应用程序的安全。这包括一个独特的设计系统、可重用的组件和一个促进安全应用程序 < > 安全通信的安全应用程序 SDK。
