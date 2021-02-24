# Harmony Unifi difi contract Documentation

## Contract function

<H1> Harmony CONTRACT API </H1>

<H2> Call API </H2> 

| Method name | Param | Return | Description | Trade related |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| `getPrice() ` | - | uint256 | get the curent pool state | Yes |
| `getMaxTransaction() ` | - | uint256 | get max amount per transaction | Yes |
| `getMinTransaction() ` | - | uint256 | get min amount per transaction | Yes |
| `getEstimatedBuyReceiveAmount(uint256 amount)` | uint256 | uint256 | Returns the amount of trading token to receive | Yes |
| `getEstimatedSellReceiveAmount(uint256 amount)` | uint256 | uint256 | Returns the amount of base token to receive | Yes |
| `pendingFeeEarn()` | - | uint256 | Return amount of UP token the user can claim | No |
| `getMaxRatio()` | - | uint256 | %Max amount per trade | Yes |
| `getSTATE()` | - | uint256 | If the pair is open for trading:[0 - close , 1 - open] | Yes |
| `getSeedBuyRate()` | - | uint256 | Rebates %[Out of 100000] | Yes |
| `getFEE()` | - | uint256 | %FEE for the pair[Out of 100000] | Yes |
| `totalSupply()` | - | uint256 | Return Total Supply of liquidity token | No |
| `balanceOf(address owner)` | address | uint256 | Return user liquidity balance | No |
| `name()` | - | string | Return Liquidity name Symbol | No |
| `symbol()` | - | string | Return Liquidity Token Symbol | No |
| `decimals()` | - | uint28 | Return Liquidity Token Decimals | No |


<H2> Send API </H2> 

| Method name | Param | Return | Payable| Description |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| `Buy` | address | uint256 | Yes |   True |When a user  buys a trading token.Example UP/ONE, a user would like to BUY UP using 1 ONE param would be user account address, call value would be 1 ONE|
| `Sell` | uint256 | uint256 | No | When a user sells a trading token.Example UP/ONE, a user would like to SELL 10 UP.The webapp *must( send an approval before executing sell function. Param would be 1e19[Up has 18 decimals we are selling 10 UP]| 
| `DepositSupply` | - | uint256 | Yes | No |  True | For Liquidity Providers to deposit their tokens approval/allowance must be given before trigerring this function | 
| `WithdrawSupply` | uint256 | bool | - | No |   False |Liquidity providers to withdraw their liquidity | 
| `ClaimFee` | - | uint256 | - | No |  False |Liquidity providers to claim the UP fees earn from the smart contract |


