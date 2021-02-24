# ONT Unifi difi contract Documentation

## Contract function

<H1> ONT CONTRACT API </H1>

<H2> Call API </H2> 

| Method name | Param | Return | Description | Trade related |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| `getPrice() ` | - | int| get the curent pool state | Yes |
| `getMaxTransaction() ` | - | int| | get max amount per transaction | Yes |
| `getMinTransaction() ` | - | int| | get min amount per transaction | Yes |
| `getEstimatedBuyReceiveAmount(int)` | int| | int| | Returns the amount of trading token to receive | Yes |
| `getEstimatedSellReceiveAmount(int)` | int| | int| | Returns the amount of base token to receive | Yes |
| `pendingFeeEarn()` | address | int| | Return amount of UP token the user can claim | No |
| `getMaxRatio()` | - | int| | %Max amount per trade | Yes |
| `getSTATE()` | - | int| | If the pair is open for trading:[0 - close , 1 - open] | Yes |
| `getSeedBuyRate()` | - | int| | Rebates %[Out of 100000] | Yes |
| `getFEE()` | - | int| | %FEE for the pair[Out of 100000] | Yes |
| `totalSupply()` | - | int| | Return Total Supply of liquidity token | No |
| `balanceOf(address owner)` | address | int| | Return user liquidity balance | No |
| `name()` | - | string | Return Liquidity name Symbol | No |
| `symbol()` | - | string | Return Liquidity Token Symbol | No |
| `decimals()` | - | int| Return Liquidity Token Decimals | No |


<H2> Send API </H2> 

| Method name | Param | Return  | Trade related  | Description 
| ------------- | ------------- | ------------- | ------------- | ------------- | 
| `Buy` | address,int amount | int| Yes | When a user  buys a trading token.Example UP/ONTd, a user would like to BUY UP using 1 ONTd param would be user account address, call value would be 1 ONTd
| `Sell` | address,int amount| int| Yes | When a user sells a trading token.Example UP/ONTd, a user would like to SELL 10 UP.The webapp *must( send an approval before executing sell function. Param would be 1e19[Up has 18 decimals we are selling 10 UP]| 
| `DepositSupply` | address,int amount| int| | No | For Liquidity Providers to deposit their tokens approval/allowance must be given before trigerring this function | 
| `WithdrawSupply` | address,int amount| bool | No |Liquidity providers to withdraw their liquidity | 
| `ClaimFee` | address | int | No |Liquidity providers to claim the UP fees earn from the smart contract |


