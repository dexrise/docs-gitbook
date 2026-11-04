# Floor Price Protection

**Floor Price Protection (FPP)** is an exclusive DEXRise mechanism — it does not exist on any other trading platform. It gives a trading pair an **unbreakable price floor**: a defined minimum price that selling cannot push the market below, which automatically rises every time the pair records a new all-time high.

The result is a market structure in which the price always forms higher lows and can never revisit an old floor — a continuously upward-trending asset that still keeps full freedom of movement inside its range.

## How the floor is defined

The floor price is set based on a **fixed percentage linked to the pair's highest recorded price (All-Time High, ATH)**. The floor always sits below the ATH by exactly that fixed percentage.

For example, with a Floor Price of **50%**:

| Metric | Value |
| --- | --- |
| Last recorded ATH | $1.00 |
| Floor price (50%) | $0.50 |

In other words: the floor is 50% below the last ATH — and the price can never drop below that floor.

## The floor only moves up

The mechanism is designed so that the floor rises and never falls:

1. The pair records a new ATH.
2. The floor price moves up **immediately and automatically** to the level defined by the fixed percentage below the new ATH.
3. The previous floor level becomes permanently unreachable — the price can never return to it.

This is why the price always forms **higher lows with every new ATH**. Each market cycle builds on a strictly higher base than the cycle before it.

## What happens when the price reaches the floor

The price has full freedom of movement **within the range between the ATH and the floor**. It can rise toward new highs or fall toward the floor — but at the floor itself, a hard rule applies:

> **The moment the current price equals the floor price, selling operations stop.**

Sellers cannot push the market below the floor, because selling is simply halted at that level. In practice, reaching the floor acts as a **strong buy signal** for investors: it marks the point where an **accumulation phase begins** and a **new upward cycle starts**.

## Why it matters

| Without Floor Price Protection | With Floor Price Protection |
| --- | --- |
| Price can keep falling past any "support" level | The floor is enforced — selling stops at it |
| Downtrends can erase months of gains | Maximum drawdown from the ATH is capped by the fixed percentage |
| Lows drift lower over time | Every new ATH raises the floor — lows get structurally higher |
| Recovery after a crash has to rebuild from a lower base | Recovery always starts from a floor that is higher than any previous floor |

## Where you will find FPP pairs

* **DXR itself** — the native DEXRise token trades with Floor Price Protection set at 50% max drawdown from the last ATH. See [DXR Trading Launch](../dxr-token/trading-launch.md).
* **Listed project pairs** — Floor Price Protection is supported on trading pairs listed through the zero-liquidity listing model. Projects can add FPP to their pair when listing on DEXRise; see [Trading Pair Listing](../listing/trading-listing.md).

{% hint style="info" %}
For DXR specifically, the 50% protection means that from the moment of launch, the price starts **at the floor itself** — 0.001 USDT — so the first upward cycle begins immediately. Details in [DXR Trading Launch](../dxr-token/trading-launch.md).
{% endhint %}
