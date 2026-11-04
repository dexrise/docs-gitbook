# Slippage Protection

Slippage Protection is a built-in trading safeguard on DEXRise that protects you from unexpected price changes between the moment you submit a trade and the moment it executes.

## What is slippage?

In decentralized trading, the price you see when you submit a trade and the price at which the trade actually executes are not always identical. The difference is called **slippage**. It happens because prices move continuously and liquidity pools reprice with every trade — and fast-moving markets or thin liquidity can push the executed price noticeably away from the quoted one.

Without protection, slippage can turn a planned trade into a worse deal than you intended.

## How Slippage Protection works on DEXRise

DEXRise lets you define the **maximum percentage of price change you are willing to tolerate** on a trade. From that moment, the rule is simple:

> **If the price change on the trade exceeds your set limit, the transaction fails automatically.**

Nothing executes beyond your tolerance. The trade either goes through within your accepted range, or it does not go through at all — it never silently executes at a price worse than you allowed.

## Why it matters

| Scenario | What Slippage Protection does |
| --- | --- |
| Fast price movements during a volatile market | Blocks execution if the price escapes your accepted range |
| Trades on pairs with thinner liquidity | Prevents an unexpectedly worse fill than the quoted price |
| Automated peace of mind | The check is enforced by the transaction itself — no manual monitoring required |

{% hint style="info" %}
Set your slippage tolerance before executing a trade in the [Trade Panel](trade-panel.md). A limit that is too tight may cause trades to fail in fast markets; a limit that is too loose accepts larger price swings. Choose the range that matches the trade you are making.
{% endhint %}
