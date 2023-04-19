# Problem Research: 

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

## 1. AA Wallet cannot be logged in from multiple locations simultaneously.

AA Wallet has only one owner, if used in other places and come back will overwrite the owner. We have to use recovery twice.

We want to use a owner management module to define role of users. We can set members and their security method in AA wallet, eg owner and operators.

Initial thought is owner and operator users, such as:

```
mapping (address => bool) operators

function grantOperator(
        address newOperator
    ) external override onlyOwnerOrFromEntryPoint

function revokeOperator(
        address nowOperator
    ) external override onlyOwnerOrFromEntryPoint
```

OR we can define role module contracts, TODO

Ref: 
>Infinitism 

```
contract SimpleAccount {
    address public owner;
    ...
}
```
https://github.com/accountjs/account-abstraction/blob/develop/contracts/samples/SimpleAccount.sol

> Soulwallet

owner is set when initialize

https://github.com/accountjs/soul-wallet-contract/blob/main/contracts/SoulWallet.sol

>Stackup Early

https://github.com/accountjs/stackup/blob/main/apps/contracts/contracts/wallet/Wallet.sol

## 2. AA Wallet Interoperability between projects

Soulwallet and Stackup cannot import others wallet

User wallets cannot be migrated across different wallet projects.

The most important is to define recovery module. Every project can follow the recovery interfaces.

And the assets in the wallet can be reused in every projects, like game asset or social relations.


## 3. Cross chain

AA address can be deferent in different chain, but we can deploy wallet in same factory, same salt, same paremeters (don't pass owner). We will add owner to the wallet after the contract wallet activate.

TODO: test same contract and activate

## 4. Modules

plug in security modules, recovery modules...

TODO research Safe modules:

https://github.com/safe-global/safe-contracts/blob/main/contracts/base/ModuleManager.sol

Diamond facet: 

https://eips.ethereum.org/EIPS/eip-2535

Module spec reference：
https://github.com/safe-global/safe-contracts/issues/537

## 5. Remove EOA.

EOA owner have too much power, we can use zk or 2FA to remove EOA sigs.

TODO: research authentication methods

## 6. AA NFT/SBT Standard

AA's NFT or SBT can be set from the account factory, can be used in marketing, or AANS.

AA NFT market can be redefined
