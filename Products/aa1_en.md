## AA Introduction：

Account Abstraction (AA) is a new paradigm for contract wallets based on ERC-4337, implemented at the application layer. AA enables on-chain interactions to mimic the operations of current external accounts (such as Metamask's accounts) without modifying the ETH nodes, using on-chain contract accounts.

AA uses a bundler to activate and operate the contract wallet, and employs various recovery mechanisms (such as social recovery, biometric recovery, MPC recovery, etc.) to enable contract transactions without recording private keys or pre-purchasing Ethereum. This eliminates the need for complex key management and Ethereum integration, making it easier for users to access Web3 and enabling mass adoption of Web3 applications. Moreover, the security features of the contract can eliminate the risk of private key theft for the wallet.

## AA Technical Features:

AA is a combination of multiple modules:

UserOp (OP) is the unified transaction format of ERC-4337. It records the sender's wallet address, nonce value, the content of the calldata transaction, and will add an initcode to generate a contract wallet if it is not initialized. Paymaster is optional but can be used to determine which paymaster mechanism will pay for gas. There are several fields that calculate gas fees, and the most important signature field, which can sign the entire data hash. The wallet will determine if this signature belongs to the owner or if there are other ways to expand the signature.

EntryPoint (EP) is the transaction entry point for all UserOps. It is universal and can be used for only one EP contract in a network. It forwards transactions based on the sender of the OP. The handleOps can initiate batch transactions or aggregated Ops, and a single transaction packaged to the EP will be more than EOA. However, batch transactions can reduce gas fees. It also provides some simulateValidation methods for Bundlers to simulate transactions.

Bundler is a backend server that is like ETH's geth or more like Mev's Proposer and is the core module of AA payment. It helps collect UserOp transactions, pack them into transactions at a certain time, and can batch them for packaging to EP. It also simulates, audits, restricts or sorts transactions. A general Bundler may restrict some OPCODES to prevent batch failure and perform some load balancing and auditing of transaction validity operations. Bundler is currently the focus of ERC4337 research, such as how to decentralize, userop mempool parallel to ETH mempool, how to sort transactions and prevent Mev, etc. Currently, the official support for multiple Bundler implementations, such as the official and Pimlico's js-Bundler, Stackup's go-Bundler, etc.

Paymaster is an optional module, which, in my opinion, is the most commercially valuable module. Through Paymaster, you can use any payment method other than ETH, such as common tokens (WETH, USDT), or support custom tokens, pay gas fees through oracles or custom prices, and even project parties can add commissions or DEX directly exchange for USD. The official also provides a VerifyingPaymaster without Gas, which adds a verified account signature to the userop's paymaster field (why add a signature, gasless without cost will increase welfare harvesting), which is returned by the Biconomy or many project gasless transaction APIs signature for you to pay on behalf of. This can be used for fiat payments, other members paying on your behalf, and more possible combinations.

Account wallet contract, in my opinion, is the most customizable module. The wallet contract has its own owner (an external EOA that can be rotated at any time without ETH and can be removed in the future for use with zk). After authentication by the owner's signature, it is a direct call-through transaction. Owner rotation is done through a recovery mechanism, and social recovery, biological recovery, and common third-party MPC recovery (currently a UX compromise solution) can be defined by contract to improve the experience. Through the customization of the Account contract, we can customize multi-signature, different signature mechanisms, different recovery mechanisms, and some special security functions.

The client-side SDK is a front-end access module that mainly assembles and initiates UserOps in an SDK layer. Currently, there are still not many developer tools, and wallets still find it difficult to access most DApps. However, most of the efforts are focused on improving the access layer and bundler/paymaster services in infrastructure development. In addition to the official SDK, early efforts include Unipass, which has a set of multi-functional access mechanisms that support email login, and ZeroDev, which encapsulates the official Infinitism SDK's upper layer and deploys bundler and other services. Accountjs's vision is also to encapsulate and integrate existing mechanisms in an open-source public layer, unify access formats, and establish Account standards.

Currently, ERC-4337 is still in the draft stage, and many modules are still not stable, requiring community collaboration. ERC-4337 still adheres to the principles of individual sovereignty and decentralization, and does not have the drawbacks of MPC single-point failure. Although it requires bundler payment, all bundlers, paymasters, and accounts can achieve decentralization, and the owner's initiative remains in their hands, allowing them to choose their preferred service providers. Moreover, the existing modules already support transactions without private keys and gas, batch and aggregate transactions, but still lack interoperability standards and universality.

## AA Product Attributes:

For teams that have been researching ERC4337 for a long time, the scenario was the topic I first conceived. We have talked a lot about the features of ERC4337, but we should focus on what AA can do in terms of product development. Currently, many wallets built on ERC-4337 have taken the lead and attracted users who are willing to try new things. However, they have not been able to establish their own advantages and moats, and without a thriving ecosystem and incentive measures, it is difficult to enlarge the amount of funds entering contract wallets under unstable psychological expectations.

Technology is only a means, contract payments, batch transactions, and recovery mechanisms can easily enable users to use them well, but what really forms a product moat is to meet real needs, enable users to use them spontaneously, and make users stay for a long time, with only user-oriented thresholds.

Why do I see great potential in AA? Because AA has great potential as a product, there is no particularly obscure technology, and it is also the strength of product managers.

AA has become a part of the ETH roadmap, and although it is still being upgraded and verified for security, it can occupy at least a fraction of the current ETH ecosystem. Of course, this does not consider the possibility that the zk technology route may change completely in the future, or that the Solidity language may become outdated, or that new paradigms may emerge.

Why use AA? Because it can change the current situation dominated by EOA, and it is definitely not a product that EOA is good at. The combination of Defi is already unbreakable, but the learning and use cost is still high. AA should take a different approach and create products that are more suitable for the general public.

AA's advantage lies in onboarding. Under the complex and obscure operation threshold of existing wallets, you first need to remember your private key/mnemonic (which may also be at risk of theft if not saved properly), enter your password, then deposit ETH, and only then can you operate the contract. Web3 is already used to this, but it is difficult for novice users, and even new internet users face prompts, tremblingly protect their private keys, and check them twice.

AA can be just like a guest login in a game. Users can come in and play the game without any barriers, and after experiencing it, they can either pay to continue or leave. Apart from time, there are no other barriers.

You can eliminate barriers and allow users to enter and play by directly paying the gas fee, which can be an easy way to attract new users.

Similar to Web2 email, you can enable Oauth login and map it to a contract wallet, maintaining a consistent Web2 experience.

After using the wallet for some time and accumulating some value, you can guide users to activate their wallet, upload recovery information, and then initiate Web3 transactions.

The advantage of using AA wallets is that they can attract new users more efficiently, not just traditional Web3 users. Traditional Web3 users are more motivated by profit, which is why you see the same group of users participating in airdrops and yield farming across various public chains, ultimately leading to internal competition. Applications that use AA wallets can allow users to enter more gently (rather than cliff-like), and with more friendly applications and experiences, you can increase the number of Web3 users several times over. The Defi Summer attracted new users, activated old users, and the NFT celebrity effect brought in new users. AA's user experience could also be the engine that drives the next bull market.

EOA private keys have too much power, and the threshold and security issues of private keys are not uncommon. For user experience, some projects choose to use custodial and MPC wallets, which have good experiences but are centralized and therefore have structural risks. However, AA can use modular, decentralized methods, and a unified transaction format that can be accessed by decentralized nodes, balancing personal sovereignty wallets and avoiding single points of failure. This is the new form of the wallet of the future.

Before wallets become mainstream, the first wallet that new users enter is like seeing a newly born duckling, and it will have more stickiness to the product. Now, projects are pursuing new users solely through high profits, but they also need to retain users through necessity, fun, and other attributes. Sustainability is the driving force behind industry development. Therefore, users are the moat of the product, and facing users, only killer applications have an advantage. AA has a lower threshold and a greater advantage. As users enter, they can explore more of the new Web3 world, and strengthen the flow of Crypto and the real world.

Does AA have commercial properties? First of all, AA has good support for new tokens (which I can explain in detail below), and the complex mechanism has detailed records of allocation rules. Through bundlers and paymasters' customizable payment rules, it also has good commercialization scenarios.

There are still many things to say about applications and scenarios, and what EOAs can do now, AA can re-implement or do better, and what EOAs cannot do now, AA can do well. I will list them one by one in the next article. Writing about AA products is about opening up ideas and welcoming project discussions or joining the team to develop and jointly research technology implementations, building new scenarios and creating new trends in this new world.

Now let me give an example of a scenario that was initially conceived.

## PlayOnboard

最开始是Free2Play的新概念，但我总是觉得free表述不当，没有任何东西是free的，人的时间也是价值，注意力是有限的。所以我提出PlayOnboard的机制，让游戏化进入AA产品。

刚才说过AA对Token机制天然是友好的，Token是项目储备价值的机制，是实用性在价值的体现。我这里就举一个Token直接使用在AA的场景。

Web2中，用户流量就是虚拟价值，各种互联网公司估值是评判标准用户DAU，产品可通过日活量估算广告价值，用户价值和产品属性，有些甚至为了提高日活甚至有刷量赚钱，类似抖音快速版。AA把用户入门门槛变低，用户无成本进入可使用流量这种新的玩法，就是免去记录私钥步奏，先提供核心场景，促活用户。

这可以很好跟游戏化产品结合。

设想是Run2earn的Stepn场景，之前还需要先创建钱包并收取原生代币，但使用AA之后，用户进来直接就可以开始跑了，跑步生息。有人会无成本为了好玩进来，有人只为了使用并激活AA新钱包，代付帮你激活钱包并不会跟之前钱包产生关联。你可以使用任何代币甚至项目方代币支付，就算用户量活跃度很高，批量交易也能为你节省gas费用

由于用户的钱包可以提前确定，用户无需激活钱包也能收到资产和代币。如果需要提前激活钱包或者购买资产和加速，可以提前在Uniswap购买资产并激活。

这样，项目上线时代币直接可以就有使用场景了。用户进来，可以氪金立刻激活账户，也可以无成本进来，当钱包有资产（比如跑步15天以上）可以引导激活钱包并上传资料进行恢复，可用时间流量换取价值。新用户会拥有第一个Web3钱包，也能通过钱包去操作更多Web3应用，而项目则收获第一批用户，用户群可以是任何人。

使用AA的合约钱包，能让用户进入Web3门槛降低，可以有更多想象空间，比如链上身份，资产互通，Token也有更多场景进行使用，这个会在下篇文章具体再列举场景使用。

PlayOnboard是一种流量转换成价值的场景，在AA的机制里面还有更多模块，可以hack进去生成新的产品形式，第二篇会列举更多场景，如果感兴趣共建可以联系作者。。

```
Contact:
Wechat: skyhigh22
Twitter: @skyh20
Email: skyhighfeng@gmail.com
ENS: skyhighfeng.eth
GitHub: https://github.com/accountjs/aa-research
```