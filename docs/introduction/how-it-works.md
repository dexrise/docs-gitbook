# How DEXRise Works

DEXRise brings together three building blocks: a unified trading interface over multiple decentralized exchanges, its own native liquidity pools, and fully on-chain execution for every service it offers. Understanding these three layers makes it easy to see how each feature fits into the platform.

## Trading across multiple platforms

DEXRise connects to several major decentralized exchanges, including **PancakeSwap**, **Uniswap**, **SushiSwap** and others. Through the DEXRise interface, you can trade on liquidity pools that belong to these external platforms — while benefiting from a simple, easy-to-use experience and rich detail about each trading pair.

In practice, this means you keep the depth of established DEX liquidity, but with a cleaner interface, protective settings such as [Slippage Protection](../trading/slippage-protection.md), and transparent [trading fees](../trading/trading-fees.md) that depend on the pair type you are trading.

## Native and shared liquidity

DEXRise also operates **its own liquidity pools**. These native pools power the platform's own trading pairs — including [DXR](../dxr-token/overview.md) pairs — and they are not closed off: any other platform can use DEXRise's pools to share liquidity.

This makes DEXRise liquidity a two-way resource: traders on DEXRise benefit from pools connected to the wider ecosystem, and external platforms can plug into the same liquidity.

## On-chain by design

Every core operation on DEXRise settles directly on the blockchain:

| Operation | How it executes |
| --- | --- |
| Staking deposits, withdrawals and reward claims | Directly on-chain |
| Presale purchases | Directly on-chain |
| Airdrop claims | Directly on-chain |

This on-chain execution model means the platform's operations are transparent and verifiable, with no black-box processing between the user's action and the blockchain result.

## How a trade flows through the platform

| Step | What happens |
| --- | --- |
| 1 | You open a trading pair on the [DEXRise Trade Panel](../trading/trade-panel.md) |
| 2 | The pair is connected to a liquidity pool — either a [DEXRise native pool](#native-and-shared-liquidity) or a pool belonging to an external platform |
| 3 | The swap executes on-chain against that pool's live price |
| 4 | Your protective settings (e.g. the [slippage limit](../trading/slippage-protection.md)) and the pair's [fee](../trading/trading-fees.md) apply according to the pair's profile |

{% hint style="info" %}
The type of pair you trade determines its features and fee rate. See [Trading on DEXRise](../trading/overview.md) for the two pair categories available on the platform.
{% endhint %}
