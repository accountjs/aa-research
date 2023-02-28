# Problem: 

## Infinitism 
```
contract SimpleAccount {
    address public owner;
    ...
}
```
https://github.com/accountjs/account-abstraction/blob/develop/contracts/samples/SimpleAccount.sol

## Soulwallet
> owner is set when initialize

https://github.com/accountjs/soul-wallet-contract/blob/main/contracts/SoulWallet.sol

## Stackup Early
https://github.com/accountjs/stackup/blob/main/apps/contracts/contracts/wallet/Wallet.sol

目前aa账户的owner只有一个，这样在恢复账户时候，是会把原来owner给覆盖。于是在新设备登录恢复时，会创建新eoa并设置owner，原来设备的eoa就不可以使用了。所以我们提出一个多账户模型来解决多设备登录的问题。

在目前owner的基础上，添加operator字段

## BaseAccount
```
interface IAccount {
    function validateUserOp(UserOperation calldata userOp, bytes32 userOpHash, uint256 missingAccountFunds)
}

abstract contract BaseAccount is IAccount {
    function nonce() public view virtual returns (uint256);
    function entryPoint() public view virtual returns (IEntryPoint);
    function validateUserOp(UserOperation calldata userOp, bytes32 userOpHash, uint256 missingAccountFunds)
    function _requireFromEntryPoint() internal virtual view
    function _validateSignature(UserOperation calldata userOp, bytes32 userOpHash)
    function _validateAndUpdateNonce(UserOperation calldata userOp) internal virtual;
    function _payPrefund(uint256 missingAccountFunds) internal virtual
}

```

并没有考虑到恢复或者子账号的问题, 所以大部分钱包都是只有一个owner

在实现中，通常有 
```
function transferOwner(
        address newOwner
    ) external override onlyOwnerOrFromEntryPoint
```

现在是想要对owner进行扩展,进行一个添加操作员

```
mapping (address => bool) operators

function grantOperator(
        address newOperator
    ) external override onlyOwnerOrFromEntryPoint

function revokeOperator(
        address nowOperator
    ) external override onlyOwnerOrFromEntryPoint
```

### 跨链

目前来看同一个EOA开始一起同时创建时候才会创建到同一个AA钱包地址，如果不同EOA创建则每条公链不同，考虑在factory里面使用相同参数，然后再通过外部EOA激活方式

### 模块化

安全模块，恢复模块
还没有头绪

