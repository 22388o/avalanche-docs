---
description: Learn more about Avalanche's transaction fees
---

# Transaction Fees

In order to prevent spam, transactions on Avalanche require the payment of a transaction fee. The fee is paid in [AVAX](../../#avalanche-avax-token). **The transaction fee is burned \(destroyed forever\).**

When you issue a transaction through Avalanche’s API, the transaction fee is automatically deducted from one of the addresses you control.

## Fee Schedule

Different types of transactions require payment of a different transaction fee. This table shows the transaction fee schedule:

{% hint style="warning" %}
The [C-Chain](./#contract-chain-c-chain) gas price is 225 nAVAX \(225 GWei\) prior to Apricot Phase 3. The C-Chain gas limit is 8 \* 10e6 \(8,000,000\). Apricot Phase 3 introduces dynamic fees to the C-Chain which will allow the gas price to fluctuate between 75 GWei and 225 GWei (dependent on network activity). See below for more detailed information on dynamic fees in Apricot Phase 3.
{% endhint %}


```cpp
+----------+-------------------+------------------------+
| Chain    : Transaction Type  | Transaction Fee (AVAX) |
+----------+-------------------+------------------------+
| P        : Create Blockchain |                   0.01 |
+----------+-------------------+------------------------+
| P        : Add Validator     |                      0 |
+----------+-------------------+------------------------+
| P        : Add Delegator     |                      0 |
+----------+-------------------+------------------------+
| P        : Create Subnet     |                   0.01 |
+----------+-------------------+------------------------+
| P        : Import AVAX       |                  0.001 |
+----------+-------------------+------------------------+
| P        : Export AVAX       |                  0.001 |
+----------+-------------------+------------------------+
| X        : Send              |                  0.001 |
+----------+-------------------+------------------------+
| X        : Create Asset      |                   0.01 |
+----------+-------------------+------------------------+
| X        : Mint Asset        |                  0.001 |
+----------+-------------------+------------------------+
| X        : Import AVAX       |                  0.001 |
+----------+-------------------+------------------------+
| X        : Export AVAX       |                  0.001 |
+----------+-------------------+------------------------+
| C        : Simple send       |           (*) 0.004725 |
+----------+-------------------+------------------------+

(*) 21000 gas units at 225 nAVAX gas price
```

## C-Chain Dynamic Fees


Apricot Phase3 introduces dynamic fees to the C-Chain. This changes the gas price from a fixed minimum gas price of 225 GWei to
using a dynamic fee algorithm that determines a "base fee" based on network activity. The "base fee" is increased during periods
where utilization is above the target gas utilization and decreases the "base fee" when the network is operating below its target utilization.

### Base Fee

The "base fee" is bound by a minimum base fee of 75 GWei and a maximum base fee of 225 GWei. These bounds are set for the first phase
of dynamic fees to ensure that any transaction sent with the old gas price of 225 GWei will be valid in Apricot Phase 3. However, the next
phase will introduce a loosening of this constraint, so it is recommended that users switch to using the `eth_baseFee` and `eth_maxPriorityFeePerGas` endpoint to estimate what fees will be required to be included in a block.

### Dynamic Fee Transactions

Transaction fees are based on EIP-1559 style Dynamic Fee Transactions, which consists of a gas fee cap and a gas tip cap. For all legacy
transactions, which only specify a single gas price, the gas price serves as both the gas fee cap and the gas tip cap. The fee cap specifies the maximum price the transaction is willing to pay per unit of gas. The tip cap specifies the maximum amount above the base fee that the transaction is willing to pay to be included in a block (this is also called the priority fee). Therefore, the effective gas price paid by a transaction will be `min(gasFeeCap, baseFee + gasTipCap)`. Unlike in Ethereum where the priority fee is paid to the miner that produces the block, in Avalanche both the base fee and the priority fee are burned.

### MetaMask

MetaMask will automatically start using Dynamic Fee Transactions once Apricot Phase 3 goes into effect, which means that if you are using MetaMask, you will automatically start taking advantage of dynamic fees as soon as Apricot Phase 3 goes live!

### How Should You Take Advantage of Dynamic Fees?

If you want to start taking advantage of dynamic fees, you will need to start using the `DynamicFeeTx` type. This transaction type allows your transaction to specify a `gasFeeCap` and a `gasTipCap`.

- `gasFeeCap` - maximum price per unit of gas that the transaction is willing to pay
- `gasTipCap` - maximum amount above the `baseFee` of a block that the transaction is willing to pay to be included

Use `eth_baseFee` API call to estimate the base fee for the next block. If more blocks are produced in between the time that you construct your 
transaction and it is included in a block, the base fee could be different from the base fee estimated by the API call, so it is important to treat
this value as an estimate.

Next, use `eth_maxPriorityFeePerGas` API call to estimate the priority fee needed to be included in a block. This API call will look at the most 
recent blocks and see what tips have been paid by recent transactions in order to be included in the block.

Based off of this information, you can specify the `gasFeeCap` and `gasTipCap` to your liking based on how you prioritize getting your transaction included as quickly as possible vs. minimizing the price paid per unit of gas.
