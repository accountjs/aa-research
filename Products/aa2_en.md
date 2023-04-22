> To defeat EOA wallets, it's not about imitating them, but creating new stories in new areas.

In the previous article, we discussed the main technical features of AA and gave an example of PlayOnboard.

Here, we list some of the advantages of AA products:

- Users can enter Web3 seamlessly and use multiple account recovery mechanisms
- Paymaster defines a method of payment on behalf of someone else, using specific tokens or gasless payments
- Bundler batches and aggregates transactions, providing gas reduction advantages in high-frequency scenarios
- Bundler payment on behalf of someone else can also initiate transactions on a scheduled basis, triggered in specific scenarios
- Account contracts can be customized with recovery and security mechanisms
- Account factories can define hooks to generate properties when creating accounts

In this article, we'll brainstorm some more AA ideas that are not just about directly replacing EOA wallets with AA, but about leveraging the advantages of AA in new areas.

## 1. AA x Games

AA is a natural fit for Gamefi, as these types of applications are frequented by users, and AA can provide an added boost. 

Currently, most Web3 games are geared towards 2earn or gambling applications, and there is a lack of high-quality 3A-level applications. User surveys indicate that Crypto users are also high-quality game users. The low entry barrier of AA makes this possibility achievable, with the only obstacle being the developer's adoption of AA. When the infrastructure lowers this barrier, game developers can focus on gameplay and economic circulation, making these games more likely to attract new users.

By attracting users to enter the game at a low cost and experiencing happiness or a sense of experience, with value acquisition as an additional condition, there will be better positive feedback. This will transform games from Play2Earn to Play4Fun, providing users with a sense of spiritual pleasure and the ability to acquire value. With reasonable economic design, it will reduce the behavior of "wool party" brushing. When users have enough value support, they can be guided to activate their accounts and set up account recovery, allowing them to purchase items and exchange Web3 products on their personal wallets.

AA also corresponds to the full-chain game that is currently being promoted. The use of roles, props, equipment, levels, and other features in full-chain games requires a lot of chain interaction features. Using AA's batch transaction interface can bundle transactions at once, reducing the gas fees used in combining multiple transactions in games and even subsidizing gasless transactions.

At this time, Web3 games are more like web page mini-games, and mobile applications such as StepN are wallets. I believe that the trend of future wallet infrastructure will have more diverse client endpoints, and there is still a long way to go. Mobile games will come with wallets, and excellent wallet experiences can also assist games in better development. This applies more to mobile devices, VR, and other wearable devices, allowing Web3 to appear anywhere. This In-dapp wallet does not rely on web wallet plugins or WalletConnect to pop up wallet connections, which can also take up a few seconds. The mobile scenario is more extensive and lacking, and excellent product experiences can easily attract a large number of users.

After solving the client experience, interoperability of the wallet is the next challenge. Like Loot, which can be used in multiple places after purchase, games can retrieve some asset data from previous games, such as character level and purchased items, through a unified recovery interface. As long as the account is connected, it can be migrated to the next game. At the same time, users activated from the game can be imported into existing wallet applications, enabling connection and use of existing wallet functions, achieving true AA wallet interoperability.

## 2. AA x NFTs/SBTs

NFT has brought more possibilities to Web3. There are numerous standards for NFT, which can be used as role PFP in certain circles, as passes for access, or as proof of ownership. With the paradigm shift brought by smart contract wallets, what else can we do besides creating a new NFT marketplace?

Previously, EOA accounts did not have storage space for data. However, contracts can record anything or implement any function, and contract wallets can also be used as a function for NFTs. I imagine that there will be more possibilities for customization of contract wallets, and modularity and reusability will become more important trends.

### AA DID & SocialFi

When generating a contract wallet, external NFT or built-in NFT functionality can be added to the wallet through Account Factory. The contract wallet can also have identity features built-in.

For example, the previously considered AANS could come with a user-readable .aa domain name for newly generated contract wallets. This domain name could be recorded in the generated Account Factory, and users could register, renew, or transfer it through the Account Factory. Domain name resolution and other operations could also be carried out through the Factory contract.

Additionally, by defining a new Profile interface within the Account, personal information such as profile picture, name, and other details can be directly recorded within the Account contract, making the wallet a self-sovereign identity (SSI) hub. Personal data can be accessed simply by reading the contract wallet, and modular social relationship information can also be added. The AA functions as a personal information repository.

### AA fan economy

Since AA can come with NFT/SBT upon creation, it's possible to record upper-level information during the generation process. You can come with SBT from certain merchants or referral sources, so you can perform some secure operations when using the wallet, or enjoy some benefits when reading the contract wallet. This will make it easier for it to spread in a viral manner.

## AA x DeFis

To be honest, AA is not very compatible with DeFi for now. First of all, DeFi is a professional product with a high barrier to entry. Second, DeFi focuses on composability, and calling through AA may cause mutual calls that affect the world state and lead to contract errors. However, for some DeFi protocols, reducing the user's usage threshold is indeed a good customer acquisition opportunity.

### Special Loan/Stablecoin/Dex

For the traditional DeFi three pillars, new DeFi is a new channel to attract users.

For traditional lending, gasless transactions can be conducted through some external asset proof, making it easier for users to obtain funds. And it is possible to make borrowing or repaying operations within the scheduled time, better avoiding liquidation.

For stablecoins, better exchange and pricing through Onramp, and can serve as the fee support for Paymaster. After fiat deposit, anonymous wallets can be created without tracking.

For decentralized exchanges, the threshold is relatively high. For proxy payments, using project tokens to pay gas or directly allowing users to trade can directly activate and convert funds in the contract. Efficiency can be higher than cex registration process. Anonymous accounts can also be used in the AA contract.

### Yield Aggregator/Strategy Platform

An AA contract wallet can serve as a yield aggregator wallet, automatically collecting profits from yield platforms and reinvesting them through scheduled tasks. In bundler, it is also possible to perform strategy trades against price fluctuations of on-chain oracle.

### Safe Vault

AA contracts can be used as cold or hot wallet vaults for large funds. AA contract wallets can customize security policies, such as daily limits based on roles, operator permissions, multi-signature, and 2FA policies, which can be customized through a security module to determine their security behavior.

## AA x RWA

As AA contract addresses can be fixed before use and have composability and interoperability, they can achieve some functionalities that traditional EOA cannot. This includes the tokenization of traditional RWA assets on-chain.

### AA Marketing

In the marketing planning of my Web3 gifting culture creative brand 1to3.io, we assumed a scenario where users can make payments through crypto or PayPal. We will generate a contract wallet address for the user, and the wallet can be generated based on the hash of a referral code, allowing the user to have the first contract wallet. Sending wallet can be another approach for creative marketing using NFTs.

### Scheduled tasks

In the company or DAO, when outsourcing tasks, we need to schedule tasks based on certain conditions. For example, we can set a specific time period each month, and initiate scheduled payments through third-party payment systems after a certain time period has elapsed. This can be used for salary payments, stream payments, and other external trigger-based scenarios. For instance, in the first PlayOnboard daily airdrop task, we can schedule a batch of tasks to be initiated at midnight every day.

### Inheritance of Legacy

When we don't use a wallet for a long time, sometimes assets can be forgotten. To avoid this, one can use a place to record the wallet and sign in advance. After a certain period of time, the assets will be transferred to another wallet address. This is a derivative application of AA wallet's scheduled tasks. AA can be used to store and clean up assets safely, as well as do more signature authentication.

In summary, Customization of accounts will inevitably become a major trend in the AA ecosystem. Through AA, more products and more forms of contract accounts can be derived, and the creation of accounts will be the most. However, as mentioned in the first article, users are the only threshold for application in all scenarios. In an interconnected ecosystem, obtaining and retaining users is the key to maximizing the advantages of AA applications. Therefore, in the next article, we will discuss how to enter the largest user scenarios and use the advantages of AA to import users.

This article aims to spark ideas, and interested developers can also contact the author to build new scenarios in the AA ecosystem. Every idea can do a lot of things.