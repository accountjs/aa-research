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

AA's advantage lies in onboarding. Under the complex and obscure operation threshold of existing wallets, you first need to remember your private key/mnemonic (which may also be at risk of theft if not saved properly), enter your password, then deposit ETH, and only then can you operate the contract. Web3 is already used to this, but it is difficult for novice users, and even internet users face the saving your mnemonic warnings, they tremblingly write down their private keys, and double check the phrases.

AA can be just like a guest login in a game. Users can come in and play the game without any barriers, and after experiencing it, they can either pay to continue or leave. Apart from time, there are no other barriers.

You can eliminate barriers and allow users to enter and play by directly paying the gas fee, which can be an easy way to attract new users.

Similar to Web2 email, you can enable OAuth login and map it to a contract wallet, maintaining a consistent Web2 experience.

After using the wallet for some time and accumulating some value, you can guide users to activate their wallet, upload recovery information, and then initiate Web3 transactions.

The advantage of using AA wallets is that they can attract new users more efficiently, not just traditional Web3 users. Traditional Web3 users are more motivated by profit, which is why you see the same group of users participating in airdrops and yield farming across various public chains, ultimately leading to internal competition. Applications that use AA wallets can allow users to enter more gently (rather than cliff-like), and with more friendly applications and experiences, you can increase the number of Web3 users several times over. The Defi Summer attracted new users, activated old users, and the NFT celebrity effect brought in new users to Web3. AA's user experience could also be the engine that drives the next bull market.

EOA private keys have too much power, and the threshold and security issues of private keys are not uncommon. For user experience, some projects choose to use custodial and MPC wallets, which have good experiences but are centralized and therefore have structural risks. However, AA can use modular, decentralized methods, and a unified transaction format that can be accessed by decentralized nodes, balancing personal sovereignty wallets and avoiding single points of failure. This is the new form of the wallet of the future.

Before wallets become mainstream, the first wallet that new users enter is like seeing a newly born duckling, and it will have more stickiness to the product. Now, projects are pursuing new users solely through high profits, but they also need to retain users through necessity, fun, and other attributes. Sustainability is the driving force behind industry development. Therefore, users are the moat of the product, and facing users, only killer applications have an advantage. AA has a lower threshold and a greater advantage. As users enter, they can explore more of the new Web3 world, and strengthen the flow of Crypto and the real world.

Does AA have commercial properties? First of all, AA has good support for new tokens (which I can explain in detail below), and the complex mechanism has detailed records of allocation rules. Through bundlers and paymasters' customizable payment rules, it also has good commercialization scenarios.

There are still many things to say about applications and scenarios, and what EOAs can do now, AA can re-implement or do better, and what EOAs cannot do now, AA can do well. I will list them one by one in the next article. Writing about AA products is about opening up ideas and welcoming project discussions or joining the team to develop and jointly research technology implementations, building new scenarios and creating new trends in this new world.

Now let me give an example of a scenario that was initially conceived.

## PlayOnboard
At first, Free2Play was a new concept, but I always felt that the term "free" was not appropriate. Nothing is truly free, as people's time and attention are valuable and limited. Therefore, I proposed the PlayOnboard mechanism to incorporate gamification into AA products.

As I mentioned earlier, the Token mechanism is naturally friendly to AA. Tokens are a mechanism for storing project value and represent the practical value of a project. Here, I will give an example of using Tokens directly in the AA scenario.

In Web2, user traffic is virtual value, and the valuation of various Internet companies is based on the number of daily active users (DAUs). The value of a product can be estimated based on the number of daily active users and product attributes. Some even earn money by boosting their daily active users. By lowering the user entry barrier, AA allows users to use traffic economy without any cost, which eliminates the need for recording private keys and provides core scenarios to activate users.

This can be well combined with gamified products.

Imagine the StepN scenario of Run2earn. Previously, users needed to create a wallet and collect native tokens before they could start running and earning. With AA, users can start running immediately without any cost and earn rewards. Some may come in just for fun, while others may activate a new AA wallet to use it, and the activation fee will not be associated with their previous wallet. Users can pay with any token, even project tokens, and batch transactions can save you gas fees even with high user activities.

Since the user's wallet can be determined in advance, the user can receive assets and tokens without having to activate the wallet. If the wallet needs to be activated in advance or assets and acceleration need to be purchased, You can also purchase tokens on Uniswap and activate account in advance.

Thus, when the project goes live, its tokens can be used immediately. Users can activate their accounts by spending cryptocurrency or come in without any cost. Once they have accumulated assets (e.g. by running for more than 15 days), they can be guided to activate their wallets and upload their information for recovery methods. New users will have their first Web3 wallet, which can be used to operate more Web3 applications, while the project will gain its first group of users, they can be anyone either he is Web2 or Web3.

Using AA's contract wallet can lower the barrier to entry into Web3 and offer more room for imagination, such as on-chain identity, asset interoperability, and more scenarios for using Tokens. These will be listed in more detail in the next article.

PlayOnboard is a scenario in which traffic is converted into value. There are still more modules within the AA mechanism that can be hacked to generate new forms of products. The second article will list more scenarios, and if you are interested in collaborating, please contact the author.

Contact:
Wechat: skyhigh22
Twitter: @skyh20
Email: skyhighfeng@gmail.com
ENS: skyhighfeng.eth
GitHub: https://github.com/accountjs/aa-research