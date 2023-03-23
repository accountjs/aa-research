# AANS - Account Abstraction Grant Proposal

## Project Abstract

我们的项目旨在为账户抽象提供一个安全且易于使用的去中心化身份系统。该解决方案基于EIP-4337账户抽象生成合约钱包，同时用户可以生成个性化的域名AANS来替代地址、作为自己的身份标识，并使用该身份标识进行应用登录和安全交易，从而增强用户体验同时保证安全性。

AANS(Account Abstraction Name Service) aims to provide a secure and user-friendly decentralized identity system for account abstraction. The solution is based on the EIP-4337 account abstraction generated contract wallet, while users can generate personalized domain AANS to replace addresses as their identity, and use this identity for application login and secure transactions, thus enhancing user experience while ensuring security.

## Objectives

建立一个.aa的一级AANS域名系统，是专用合约钱包的域名，该域名可以再生成钱包时候注册，也可以后续以域名注册形式注册，域名以NFT形式存在在合约账户中。

创建一个注册，购买域名的交易市场，域名专用Paymaster，接入AANS的域名服务sdk，可以使用在AA钱包，Dapp中简单显示用户域名，解析域名服务。

可以多链AA账户使用.aa域名，进行域名解析，通过子账户对域名管理和合约安全验证。


Establishing a first-level AANS domain system with the .aa extension is designed for specialized contract wallets. The domain name can be registered during the wallet generation or at a later time through domain name registration. The domain name is stored in the contract account in the form of an NFT.

A registration and purchasing domain name transaction market is established with a domain-specific Paymaster, which integrates the AANS domain name service SDK. The domain name can be easily displayed in AA wallets and Dapps, and the domain name service can be resolved.

The .aa domain name can be used by multi-chain AA accounts for domain name resolution, and sub-accounts can manage domain names and contract security verification.

## Outcome

目前问题：
AA钱包可以让用户很容易进入Web3，但是创新的新账户没有一些好的用户体验和管理系统。

解决问题：
通过AANS生成账户自带域名，会以用户可读形式进入Web3
在钱包和Dapp内部显示域名，对账户收款和传播上将会很好管理，提高用户体验
.aa是合约钱包专用域名，会对合约进行检测，对域名账户安全设置等，可以有效管理AA账户

Current issues: The AA wallet makes it easy for users to enter Web3, but innovative new accounts lack good user experience and management systems.

Solution: By generating an account with a built-in domain name through AANS, it will enter Web3 in a user-readable format. Displaying the domain name within the wallet and Dapp will make it easier to manage account receipts and promotions, improving user experience. The .aa domain name is exclusively for contract wallets and can effectively manage AA accounts by performing contract checks and setting domain account security.

## Grant Scope

4大业务：
生成方式有两种：官方钱包工厂激活钱包时生成和注册域名（类似ENS，但生成会有钱包接口检测）

AANS SDK，帮助项目接入aans体系，增加用户体验，减少用户接入门槛

AANS 注册和交易平台，购买，续费，添加子功能和Paymaster

AANS 跨链注册模块，子账号模块，增加域名进行安全管理和扩展功能

AANS 文档和接入的编写


Four Parts: There are two ways to generate the domain name: it can be generated when the wallet is activated by the official wallet factory or registered through a domain name (similar to ENS, but with wallet interface detection during generation).

AANS SDK helps projects integrate into the AANS system, enhances user experience, and reduces user access barriers.

AANS registration and trading platform allows for purchasing, renewing, adding sub-functions, and Paymasters.

AANS cross-chain registration module and sub-account module enable secure management and extended functionality for domain names.

AANS documentation and integration development.


## Project Team

Xinchen, Gali，Neal，AV，Nano，Sky

Consultant：Accountjs, PNS, 

## Background

我们有对AA的研究基础，也有对ENS的研究人员

We have a research foundation on AA, as well as researchers who have studied ENS

## Methodology

开源社区，社区启动和讨论的方式，具体会选出执行人

Open-source community, ways to initiate and discuss community activities.

## Timeline

5个月，3个节点
1-2. 搭建AA域名系统，实现合约的改动
3-4. sdk接入和交易市场
5. aa子域名和安全系统，推动Dapp接入

5 months, 3 milestones:

Milestone 1: Establish the AA domain name system and implement changes to the contract.

Milestone 2: Integrate the SDK and set up a transaction market.

Milestone 3: Develop the AA sub-domain name and security system, and promote Dapp integration.

## Budget

30K - 50K


