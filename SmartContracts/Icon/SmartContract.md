# ICON Unifi difi contract Documentation

## Contract function

<H1> ICON CONTRACT API </H1>

<H2> Call API </H2> 

| Method name | Param | Return | Description | Trade related |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| `getPrice() ` | - | int | get the curent pool state | Yes |
| `getMaxTransaction() ` | - | int | get max amount per transaction | Yes |
| `getEstimatedBuyReceiveAmount(int  amount)` | int | int | Returns the amount of trading token to receive | Yes |
| `getEstimatedSellReceiveAmount(int  amount)` | int | int | Returns the amount of base token to receive | Yes |
| `pendingFeeEarn(address owner)` | address  | int | Return amount of UP token the user can claim | No |
| `getMaxRatio()` | - | int | %Max amount per trade | Yes |
| `getSTATE()` | - | int | If the pair is open for trading:[0 - close , 1 - open] | Yes |
| `getSeedBuyRate()` | - | uint256 | Rebates %[Out of 100000] | Yes |
| `getFEE()` | - | int | %FEE for the pair[Out of 100000] | Yes |
| `totalSupply()` | - | int | Return Total Supply of liquidity token | No |
| `balanceOf(address owner)` | address | int | Return user liquidity balance | No |
| `creditOf(address owner)` | address | int | Return user ICX deposited into contract to add liquidity | No |
| `name()` | - | string | Return Liquidity name Symbol | No |
| `symbol()` | - | string | Return Liquidity Token Symbol | No |
| `decimals()` | - | int | Return Liquidity Token Decimals | No |


<H2> Write API </H2> 

| Method name | Param | Return | Payable | Description 
| ------------- | ------------- | ------------- | ------------- | ------------- | 
| `Buy` | address | int | Yes |When a user  buys a trading token.Example UP/ICX, a user would like to BUY UP using 1 ICX param would be user account address, call value would be 1 ICX |
| `addCredit` | int | - | Yes |Deposit ICX in order to add liquidity |
| `withdrawCredit` | -| -| No |Contract will return users all of ICX user credit |
| `WithdrawSupply` | int | - | No  |Liquidity providers to withdraw their liquidity | 
| `ClaimFee` | - | int | - | No  |Liquidity providers to claim the UP fees earn from the smart contract |

Transfer trading token through token fall back function.Pack bytes in _data field.
| _data | Method name | Purpose | Param | Return | Payable | Description 
| ------------ | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | 
|b'1'| `transfer` | `Trigger a sell` | int | - | - | When a user sells a trading token.Example UP/ICX, a user would like to SELL 10 UP.The webapp *must( send an approval before executing sell function. Param would be 1e19[Up has 18 decimals we are selling 10 UP]| 
|b'4'| `transfer` | `Trigger a Deposit supply`  | int | - | - | For Liquidity Providers to deposit their tokens approval/allowance must be given before trigerring this function | 