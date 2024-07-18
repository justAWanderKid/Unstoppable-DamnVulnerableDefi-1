
# Notes i took During the Auditing Process:


all the `UnstoppableVault` does is, it offers free Flash Loans until a period of time.


`UnstoppableVault` Contract Balance = 1_000_000e18

`Attacker` Balance = 10e18



`maxFlashLoan(address _token)` function returns `0` if `_token` Address given is not equal to `asset` address. (it does not `revert()`, it just returns `0`).

`flashFee(uint256 _amount)` function returns `0` if `_amount < maxFlashLoan(address _token)` which `maxFlashLoan(address _token)` function returns the total Balance of `tDVT` token of the Contract.



`UnstoppableVualt` all functions:

```javascript
    {
    "DOMAIN_SEPARATOR()": "3644e515",
    "FEE_FACTOR()": "5afbc4a8",
    "GRACE_PERIOD()": "c1a287e2",
    "allowance(address,address)": "dd62ed3e",
    "approve(address,uint256)": "095ea7b3",
    "asset()": "38d52e0f",
    "balanceOf(address)": "70a08231",
    "convertToAssets(uint256)": "07a2d13a",
    "convertToShares(uint256)": "c6e6f592",
    "decimals()": "313ce567",
    "deposit(uint256,address)": "6e553f65",
    "end()": "efbe1c1c",
    "execute(address,bytes)": "1cff79cd",
    "feeRecipient()": "46904840",
    "flashFee(address,uint256)": "d9d98ce4",
    "flashLoan(address,address,uint256,bytes)": "5cffe9de",
    "maxDeposit(address)": "402d267d",
    "maxFlashLoan(address)": "613255ab",
    "maxMint(address)": "c63d75b6",
    "maxRedeem(address)": "d905777e",
    "maxWithdraw(address)": "ce96cb77",
    "mint(uint256,address)": "94bf804d",
    "name()": "06fdde03",
    "nonces(address)": "7ecebe00",
    "owner()": "8da5cb5b",
    "paused()": "5c975abb",
    "permit(address,address,uint256,uint256,uint8,bytes32,bytes32)": "d505accf",
    "previewDeposit(uint256)": "ef8b30f7",
    "previewMint(uint256)": "b3d7f6b9",
    "previewRedeem(uint256)": "4cdad506",
    "previewWithdraw(uint256)": "0a28a477",
    "redeem(uint256,address,address)": "ba087652",
    "setFeeRecipient(address)": "e74b981b",
    "setPause(bool)": "bedb86fb",
    "symbol()": "95d89b41",
    "totalAssets()": "01e1d114",
    "totalSupply()": "18160ddd",
    "transfer(address,uint256)": "a9059cbb",
    "transferFrom(address,address,uint256)": "23b872dd",
    "transferOwnership(address)": "f2fde38b",
    "withdraw(uint256,address,address)": "b460af94"
    }
```