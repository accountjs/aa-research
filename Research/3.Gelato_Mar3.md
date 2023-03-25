# Gelato_研究笔记

Gelato currently offers 2 main services:

Gelato 目前提供两项主要服务:

**Automate**: Automate your smart contract executions in a reliable, developer-friendly & decentralized manner while leveraging off-chain data. 

自动化: 自动化您的智能合同执行在一个可靠的，开发人员友好和去中心化的方式，同时利用链下数据。

**Relay**: Give your users access to reliable, robust and fast gasless transactions.

中继: 让您的用户访问可靠、健壮和快速的无Gas事务。

## Key Benefits
主要优点

No need to self-host servers on AWS or other cloud providers

不需要在 AWS 或其他云提供商上自主管理服务器

RPC aggregation with multiple fallbacks

具有多个备份的 RPC 聚合

Reliable transaction relay service that always gets transactions mined fast

总是快速挖掘事务的可靠事务中继服务

Catches reorgs automatically

自动捕获重组

Multi-chain; works with the most popular EVM-compatible networks

多链; 与最流行的 EVM 兼容网络一起工作

No single point of failure; multiple Executors are operating all over the world

没有单点故障; 多个执行者在世界各地运行

No need to self-manage your private key in the cloud

不需要在云中自我管理您的私钥

Built-in consensus / coordination layer to avoid racing conditions

内置共识/协调层，以避免赛车条件

Flexible payment options; pay with a prepaid balance or have txs pay themselves

灵活的支付方式; 用预付余额支付或者让税务局自己支付

Cost effective: cheaper than building, running & maintaining custom servers

成本效益: 比建造、运行和维护定制服务器更便宜

## Core Components

核心部件

- Event Listener 事件侦听器

The Event Listener is responsible for continuously querying the chain and monitoring emitted events. 

事件监听器负责连续查询链和监视发出的事件。 

- Checker 检查器

The Checker defines arbitrary/custom logic to check if a Gelato task is executable at a given moment. It defines the conditions required for a task to become executable. It can also define other conditions that can update a task's state, such as limit order cancellations.

Checker 定义任意/自定义逻辑来检查 Gelato 任务在给定时刻是否可执行。它定义任务成为可执行任务所需的条件。它还可以定义其他可以更新任务状态的条件，例如限制订单取消。

- Executor 执行器

An Executor is responsible to reliably submit transactions on chain and making sure that they are mined as quickly as possible with the lowest cost.

执行者负责可靠地提交连锁交易，并确保尽快以最低成本挖掘这些交易。

