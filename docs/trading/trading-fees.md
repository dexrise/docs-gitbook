# Trading Fees

Trading fees on DEXRise are transparent and predictable: the rate depends only on **the type of pair you are trading**, and the fee is always applied to **the currency you are paying with** — nothing else.

## The fee schedule

| Pair type | Fee rate |
| --- | --- |
| **DEXRise pairs** — pairs belonging to the DEXRise platform | **0.3%** |
| **External pairs** — pairs belonging to other platforms (e.g. PancakeSwap, Uniswap, SushiSwap) | **0.4%** |

## How the fee is applied

The fee percentage is applied **on the paid currency only**. When you swap currency A for currency B:

1. The fee percentage is calculated on the amount of **currency A** (the currency you are paying with).
2. The fee is deducted from that amount.
3. The remainder is converted into currency B at the pair's live price.

The fee is charged once — on the paid side of the trade — never on both sides.

## Examples

**Example 1 — DEXRise pair (0.3%)**

You swap **1,000 USDT** for DXR on a DEXRise pair:

* Fee: 1,000 × 0.3% = **3 USDT**
* Amount converted: 997 USDT

**Example 2 — External pair (0.4%)**

You swap **1,000 USDT** for a token on an external pair (a pair belonging to another platform):

* Fee: 1,000 × 0.4% = **4 USDT**
* Amount converted: 996 USDT

{% hint style="info" %}
You always see the fee value of a transaction **before executing it** — it is part of the [Trade Panel](trade-panel.md) pre-execution cost calculation.
{% endhint %}

## How to know which rate applies

The rate is determined by **which platform the pair belongs to**:

* Trading a pair that belongs to **DEXRise** (its own liquidity pools, including DXR pairs) → **0.3%**.
* Trading a pair that belongs to **another platform** → **0.4%**.

{% hint style="info" %}
Trading fees are separate from listing fees. If you are a project looking to list a trading pair on DEXRise, the listing fees and requirements are covered in [Trading Pair Listing](../listing/trading-listing.md).
{% endhint %}
